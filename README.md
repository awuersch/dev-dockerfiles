This repository holds container definitions for multi-language Linux
developer environments. The main one is OCaml. Other languages included
are C (default), fsharp, python, go, and ruby. Fsharp language support
includes a Microsoft Visual Studio Code IDE.

Each branch has a Dockerfile.
The Dockerfile starts with a base OS image drawn from the ocaml/ocaml
repository [here](https://hub.docker.com/ocaml/ocaml).

Naming conventions from [here](https://github.com/ocaml/opam-dev-dockerfiles)
are followed. Branches are named for a combination of the OS and the
installed OCaml compiler release.

Vim is included, with plugins (
[syntastic](https://github.com/vim-syntastic/syntastic),
[deoplete](https://github.com/Shougo/deoplete.nvim),
[supertab](https://github.com/ervandew/supertab), and
[ctrlp](https://github.com/ctrlpvim/ctrip.vim)
) that work well with OCaml's
[merlin](https://github.com/ocaml/merlin).

The user defined (here 'tony') is set up with sudo privileges.

Krb5 user packages are included, to connect to a Kerberos realm. A
default Kerberos configuration is supplied, which the user should
replace of s/he wants to use Kerberos. To repair the configuration,
a user might supply a bind volume when invoking the Docker run
command. The volume might contain a Kerberos config, and attached
client certs or other credentals.

Users wishing to use the Visual Studio Code IDE should use --net=host
and -e DISPLAY in the Docker run command, so X11 will go out to their
environment.

Contributing
==========

To discuss these containers,
please e-mail Tony Wuersch <tony wuersch at gmail dot com>.
The containers are built and hosted on the Docker Hub
[awuersch user](https://hub.docker.com/u/awuersch).
