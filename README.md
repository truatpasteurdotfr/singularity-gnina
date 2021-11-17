# building a gnina-1.0.1 singularity image

Tru <tru@pasteur.fr>

## Why ?
- https://github.com/gnina/gnina/issues/122
- Host running CentOS-7, but gnina requires a newer glibc...
- Provide a drop-in replacement for gnina (assuming singularity is installed)
- Should work with either https://github.com/hpcng/singularity or https://github.com/sylabs/singularity

## Caveat
- playground, use at your own risk!
- `:latest` tagged singularity image
- check gnina licenses at https://github.com/gnina/gnina when you are using it, these were copied verbatim here for convenience.
```
gnina is dual licensed under GPL and Apache. The GPL license is necessitated by
the use of OpenBabel (which is GPL licensed). In order to use gnina under the
Apache license only, all references to OpenBabel must be removed from the
source code.
```

## Usage

- Singularity [![Singularity build](https://github.com/truatpasteurdotfr/singularity-gnina/actions/workflows/singularity-publish.yml/badge.svg)](https://github.com/truatpasteurdotfr/singularity-gnina/actions/workflows/singularity-publish.yml)
```
singularity build gnina oras://ghcr.io/truatpasteurdotfr/singularity-gnina:latest
./gnina --version
```
for GPU access you need to use the `--nv` flag:
```
singularity run --nv ./gnina <.. your gnina options ...>
```

## Thanks
- https://github.com/singularityhub/github-ci for the github action
