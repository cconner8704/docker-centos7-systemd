# docker-centos7-systemd
This is a systemd enabled centos7 image:

https://hub.docker.com/_/centos/
# docker-centos7-systemd

To run for testing:

#If /sys/fs/cgroup/systemd exists:
docker run -it --cap-add SYS_ADMIN --security-opt seccomp:unconfined  -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v /tmp/$(mktemp -d):/run --name docker-centos7-systemd cmconner156/docker-centos7-systemd /usr/sbin/init

#If it does not exist
docker run -it --cap-add SYS_ADMIN --security-opt seccomp:unconfined  -v /tmp/$(mktemp -d):/run --name docker-centos7-systemd cmconner156/docker-centos7-systemd /usr/sbin/init
