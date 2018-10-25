# Deploying BOSH Director on OpenStack

## Example

```
bosh create-env /opt/spacex/workspaces/bosh-deployment/bosh.yml \
    --state=/opt/spacex/state.json \
    --vars-store=/opt/spacex/creds.yml \
    -o /opt/spacex/workspaces/bosh-deployment/openstack/cpi.yml \
    -o /opt/spacex/workspaces/bosh-deployment/uaa.yml \
    -o /opt/spacex/workspaces/bosh-deployment/openstack/custom/add-bosh-uaa-clients.yml \
    -o /opt/spacex/workspaces/bosh-deployment/openstack/custom/set-dns.yml \
    -o /opt/spacex/workspaces/bosh-deployment/openstack/custom/set-ntp.yml \
    -o /opt/spacex/workspaces/bosh-deployment/jumpbox-user.yml \
    -o /opt/spacex/workspaces/bosh-deployment/credhub.yml \
    -v director_name=x-bosh \
    -v internal_cidr=10.0.0.0/20 \
    -v internal_gw=10.0.0.1 \
    -v internal_ip=10.0.0.100 \
    -v auth_url=http://<IDENTITY_IP>:5000/v3 \
    -v az=<AZ> \
    -v default_key_name=bosh \
    -v default_security_groups=[bosh,WISE-PaaS-nsg] \
    -v net_id=<NET_ID_MGMT> \
    -v openstack_password=P@ssw0rd \
    -v openstack_username=admin \
    -v openstack_domain=default \
    -v openstack_project=WISE-PaaS \
    -v private_key=/opt/spacex/tf/bosh-init/bosh.pem \
    -v region=RegionOne \
    -v dns=[<DNS>] \
    -v ntp=[<NTP>]
```
