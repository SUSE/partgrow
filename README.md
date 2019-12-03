# partgrow

A simple systemd service for growing a partition and its file system, using
growpart and systemd-growfs.

With a given mount point, use
```
mountpoint=<Path of your mountpoint>

servicename=$(systemd-escape --path --template=partgrow@.service "${mountpoint}")"
ln -s /usr/lib/systemd/system/partgrow\@.service "/etc/systemd/system/local-fs.target.wants/${servicename}"
```
to install the service and get the partition and file system resized to the
largest possible value.
