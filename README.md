[CloudFactory](http://www.cloudfactory.com) development is heavily invested in jruby based micro/nano/macro/... services hence it makes sense to have base docker image at that ground.

[Phusion base-image](https://github.com/phusion/baseimage-docker) is already a powerful docker base image. It sparked some discussion within container/docker pundits by allowing the capability of running multiple processes within a container. README from official website/repository is filled with very thorough information but just in case you are skimming over, here's the highlights

-  `INIT` process `/sbin/my_init` which read from centralized environment variables directory `/etc/container_environment`. It also passes `env` vars correctly to forked processes.
- `logrotate` that compresses and rotates log files
- `CRON` for scheduled task inside containers
- `RUNIT` as a process supervisor.

# How is it different than [official jruby](https://hub.docker.com/_/jruby/) docker image?
- It is based on phusion-base image so all above features comes with it
- `jruby` is installed and managed via [ruby-install](https://github.com/postmodern/ruby-install). `ruby-install` dynamically decides the required dependencies for jruby being installed.

All the Dockerfiles follow [best practices](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/Â) too.
