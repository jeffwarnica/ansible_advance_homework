# TL;dr quick start

* `export TOWER_GUID=d587; export MYUSER=jwarnica-redhat.com;export OSP_GUID=6267`
* `ansible-playbook site-setup-workstation.yml -e OSP_GUID=${OSP_GUID} --private-key=/root/.ssh/mykey.pem -u jwarnica-redhat.com`
* `ansible-playbook site-install-isolated-node.yml -e OSP_GUID=${OSP_GUID} --private-key=/root/.ssh/mykey.pem -u jwarnica-redhat.com`
* `mkdir /etc/openstack`
*  .
	```workstation# cat << EOF > /etc/openstack/clouds.yaml
	clouds:
	  ospcloud:
		auth:
		  auth_url: http://192.168.0.20:5000/
		  password: r3dh4t1!
		  project_name: admin
		  username: admin
		identity_api_version: '3.0'
		region_name: RegionOne
	ansible:
	  use_hostnames: True
	  expand_hostvars: False
	  fail_on_errors: True
	EOF```
* 