# k3s-ha

Automated k3s deployments using external etcd back-end in docker

# Install with k3s-ha

1. setup inventory:

	Look at the [example_inventory.yml](example_inventory.yml) to see how you could set your cluster up.

2. run playbook to install:
	```
	time ansible-playbook -i ./inventory.yml -u root ./k3s_with_external_etcd.yml
	```

You might tweak what runs by using `--tags` and/or `--skip-tags`. For example, if you want to stand up a single node cluster and add something on later, you might `-l k3s_managers --skip-tags ha` for the first run, then `-l k3s_workers --tags docker,k3s,workers` for the second.

Look through and decide how you want to build your cluster.
