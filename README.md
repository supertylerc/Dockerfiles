# Dockerfiles

This repository consists of Dockerfiles for AMD64 and ARMHF for a variety of
containers I personally use.  Since I have a cluster of Raspberry Pi 3s and
my own personal x86_64 laptops/desktops/servers, I need a way to use the same
container images across different architectures.

This repository exists to build these images.

# Versioning

There is a goal to maintain a minimum of versions `n` and `n-1` for a given
package.  This refers to the minor version, not the major version.  However,
some packages may only have one version released.  This might be for the
following reasons:

* Versions are released infrequently, and the `n-1` version is 12 months old
* Patch revisions are not maintained for the `n-1` version
* New versions are no longer released

In some cases, where a package increments minor versions quickly _and_ the
minor versions still receive patch revisions (such as Ansible), the goal is to
provide `n`, `n-1`, and `n-2` versions.

# Building

All images are pushed to Docker Hub via Travis-CI for both the AMD64 and ARMHF
architectures.  For some images, the first image build can take a considerable
amount of time on the ARMHF architecture.  These have historically been in the
ballpark of ~20 minutes.  Usually, this only happens if the image needs to
compile some software from source.

Currently, the images are refreshed on every build from the master branch.  In
the future, an internal versioning mechanism will be applied to a metadata file
in each subdirectory.  This will not be built into the container, and it will
not be used as a tag.  This will be used strictly for building, such that if a
version for an image hasn't been updated from its previous version, a build
won't run.  That's a little ways off, though.

Finally, failed builds are not pushed to Docker Hub.  This can be frustrating,
but ideally a failed build can be replicated on your local laptop.

# Contributing

Please do.  Anything you want, really.  Improvements, new containers, tests...
Just be aware that because of the way the CI is written, any contributions are
built under my username in Docker Hub.

# Code of Conduct

Contributor Covenant.  See [the Code of Conduct](CODE_OF_CONDUCT).

# LICENSE

Apache 2.0.  See [the License](LICENSE).
