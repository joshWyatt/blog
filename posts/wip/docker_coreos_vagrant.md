[Vagrant to launch CoreOS](https://coreos.com/docs/running-coreos/platforms/vagrant/)

- install vagrant
- [clone coreos vagrant repo](https://github.com/coreos/coreos-vagrant)
- cloud config in `user-data`
  - machine parameters
  - launch systemd units on startup
  - use etcd discovery url (explain etcd)
  - [CoreOS Cluster Discovery](https://coreos.com/docs/cluster-management/setup/cluster-discovery/)
  - `curl -w "\n" https://discovery.etcd.io/new`
    - just uncomment lines in `config.rb`
- number of machines in `config.rb`
- `$num_instances=3`
- `$update_channel='stable'`
- in `Vagrantfile` if on local machine, enable NFS
- `ssh-add ~/.vagrant.d/insecure_private_key`
- `vagrant ssh core-01 -- -A`

[CoreOs gives you 3 major tools](https://coreos.com/docs/quickstart/)

- service discovery
- container management
- process management

[etcd](https://coreos.com/docs/distributed-configuration/getting-started-with-etcd/) (service discovery)

- "etcd is an open-source distributed key value store that provides shared configuration and service discovery for CoreOS clusters."
-  Data stored in etcd is distributed across all of your machines running CoreOS
- Containers on the cluster can read and write to etcd
  - (from inside coreOS machine) etcdctl set /message hi
  - etcdctl get /message
  - curl -L -X PUT http://127.0.0.1:4001/v2/keys/message -d value="Hi"

docker(container management)

  - `docker run -i -t busybox /bin/sh`

fleet(process management)

  - fleet is a distributed init system for the cluster
  - fleet receives systemd unit files and schedules them onto containers in your fleet based on conflicts and other things declared in the unit file
  - `fleetctl` is used to access information about the units
  - two types of units can be run in your cluster - standard and global units
  - standard units are long running units that run on a single machine and will migrate and be run on a different machine should the machine it runs on go down
  - global units run on every machine in the cluster


[systemd](https://coreos.com/docs/launching-containers/launching/getting-started-with-systemd/) is an init system used for starting stopping and managing processes. There are two main components to systemd: unit  and target.

  - systemd is the first process that runs on CoreOS, reading all the targets and starting the specified processes
  - targets are actually a collection of symlinks to our unit files
  - unit is a config file that describes the properties of the process you are going to run
  - target is a grouping mechanism that allows you to run multiple processes at the same time


[docker0](https://docs.docker.com/articles/networking/)

  - ethernet bridge
