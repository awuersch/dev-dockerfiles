Container definitions for multi-language Linux
developer environments. Main one: OCaml. Other languages:
C (default), fsharp, python, go, and ruby. Fsharp support
includes a Microsoft Visual Studio Code IDE.

Each branch has a Dockerfile.
The Dockerfile starts with a base OS image drawn from
[ocaml/ocaml](https://hub.docker.com/ocaml/ocaml).

Naming conventions from [ocaml/opam-dev-dockerfiles](https://github.com/ocaml/opam-dev-dockerfiles)
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

Krb5 user packages are included.
A default Kerberos config is supplied. The user should
replace this if s/he wants to use Kerberos.
To repair the configuration, a user might supply a bind volume
when invoking Docker run. The volume might contain a Kerberos
config and some client certs or other credentals.

Users wishing to use the Visual Studio Code IDE should use --net=host
and -e DISPLAY in the Docker run command, to unblock and set up X11
to the host.

Contributing
==========

To discuss these containers,
e-mail Tony Wuersch <tony wuersch at gmail dot com>.
The containers are built and hosted on the
[awuersch user](https://hub.docker.com/u/awuersch)
space on the Docker hub.
