Docker Build and Push
~~~~~~~~~~~~~~~~~~~~~

Provides a ``make docker_build`` target that builds your image locally.

Provides a ``make dockerhub_push`` target that pushes your final image to Dockerhub.

The Dockerhub image will tagged ``<REPOSITORY>:<GIT COMMIT SHA>``

If git head has a git tag, the Dockerhub image will also be tagged ``<IMAGE>:<GIT_TAG>``.

**To Enable:**

Add ``lyft/docker_build`` to your ``boilerplate/update.cfg`` file.

Your Dockerfile **must** use docker's `multi-stage builds <https://docs.docker.com/develop/develop-images/multistage-build/>`_ and name the builder stage 'builder'.

Add ``include boilerplate/lyft/docker_build/Makefile`` in your main ``Makefile`` _after_ your REPOSITORY environment variable

::

    REPOSITORY=<myreponame>
    include boilerplate/lyft/docker_build/Makefile

(this ensures the extra Make targets get included in your main Makefile)
