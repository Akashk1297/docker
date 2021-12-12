# Docker behaves differnetly on SELinux configured platforms. Also docker versions effect systemd running inside docker containers.
# Below are few use-cases.

# SELinux disabled
$ docker run -ti -v /sys/fs/cgroup:/sys/fs/cgroup:ro -p 80:80 local/c7-systemd-httpd

# SELinux enforcing mode (Docker Version: 19.03.6)
$ docker run -v /tmp/$(mktemp -d):/run -d --name sysd-test -v /sys/fs/cgroup:/sys/fs/cgroup:ro local/c7-systemd-httpd

# setenforce Permissive mode (Docker Version: 1.13.1)
$ docker run -d --name sysd-test -v /sys/fs/cgroup:/sys/fs/cgroup:ro local/c7-systemd-httpd
