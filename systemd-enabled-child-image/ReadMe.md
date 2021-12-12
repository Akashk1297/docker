# Docker - 19.03.6, SELinux enabled(enforcing), OS - RHEL-Linux

# Build image
$ docker build -t local/c7-systemd-nginx .

# Run nginx container
docker run -v /tmp/$(mktemp -d):/run -d --name sysd-nginx-test -v /sys/fs/cgroup:/sys/fs/cgroup:ro local/c7-systemd-nginx
