These examples are from a talk on building container images.

## Environment

The environment used to run these examples was openSUSE Leap 15.2, though others should be compatible. To prepare a similar environment run these commands:

    sudo zypper install docker python3-docker-compose git
    sudo systemctl enable --now docker
    sudo usermod -a -G docker $USER

To test, log out and log back in (for the group membership to update) and run:

    docker run hello-world

## References

* https://en.opensuse.org/Docker
* https://rancher.com/learning-paths/how-to-build-and-run-your-own-container-images/
* https://github.com/docker-library/hello-world
* https://documentation.suse.com/sles/15-SP2/single-html/SLES-container/#book-container
* https://docs.docker.com/develop/dev-best-practices/
* https://cloud.google.com/architecture/best-practices-for-building-containers
