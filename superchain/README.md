# Superchain

An [`amazonlinux:2`][al2]-based Docker image bundling all the SDKs and tools
required in order to package [jsii] projects in all supported languages.

[al2]: https://hub.docker.com/_/amazonlinux
[jsii]: https://github.com/aws/jsii

## Included Language SDKs

SDK             | Version
----------------|-------------------------------------------
`OpenJDK 8`     | Amazon Corretto `>= 8.242.08.1`
`.NET SDK`      | `>= 3.1.101`
`mono`          | `>= 6.8.0.105`
`Javascript`    | `node >= 10.19.0` OR `node >= 14.16.0` with `npm >= 6.14.11` (see [NodeJS and NPM](#nodejs-and-npm))
`PowerShell`    | `pwsh >= 6.2.3`
`Python 3`      | `python3 >= 3.7.4` with `pip3 >= 20.0.2`
`Go`            | `go >= 1.16`

## NodeJS and NPM

We build multiple versions of this image, for different versions of Node. They are available as:

* `jsii/superchain:node10[-nightly]`
* `jsii/superchain:node14[-nightly]`

The following labels are also available, and are aliases for the Node 10 images:

* `jsii/superchain:nightly`
* `jsii/superchain:latest`

If you are building this image from source, you can control the Node version with the
`NODE_MAJOR_VERSION` build argument:

```
docker build [...] --build-arg NODE_MAJOR_VERSION=14 .
```

## Included Tools & Utilities

Tool / Utility | Version
---------------|--------------------------------------------
`aws`          | `>= 1.16.300`
`bundler`      | `>= 1.17.3` and `>= 2.1.4`
`docker`       | `>= 18.09.9-ce`
`git`          | `>= 2.23.1`
`make`         | `>= 3.82`
`maven`        | `>= 3.6.3`
`openssl`      | `>= 1.0.2k-fips`
`rsync`        | `>= 3.1.2`
`yarn`         | `>= 1.21.1`
`zip` & `unzip`| `>= 6.0-19`

## License

Amazon Linux is available under the [GNU General Public License, version
2.0][gpl2.0]. Individual software packages are available under their own
licenses; `run rpm -qi [package name]` or check
`/usr/share/doc/[package name]-*` and `/usr/share/licenses/[package name]-*` for
details.

As with all Docker images, these likely also contain other software which may be
under other licenses (such as Bash, etc from the base distribution, along with
any direct or indirect dependencies of the primary software being contained).

Some additional license information which was able to be auto-detected might be
found in [the repo-info repository's `amazonlinux/` directory][repo-info-al2].

As for any pre-built image usage, it is the image user's responsibility to
ensure that any use of this image complies with any relevant licenses for all
software contained within.

[gpl2.0]: https://github.com/aws/amazon-linux-docker-images/blob/master/LICENSE
[repo-info-al2]: https://github.com/docker-library/repo-info/tree/master/repos/amazonlinux
