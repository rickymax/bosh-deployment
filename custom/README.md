# Deploying BOSH Director on OpenStack

## Example

```
bosh create-env /opt/spacex/workspaces/bosh-deployment/bosh.yml \
    --state=/opt/spacex/state.json \
    --vars-store=/opt/spacex/creds.yml \
    -o /opt/spacex/workspaces/bosh-deployment/openstack/cpi.yml \
    -o /opt/spacex/workspaces/bosh-deployment/uaa.yml \
    -o /opt/spacex/workspaces/bosh-deployment/openstack/keystone-v2.yml \
    -o /opt/spacex/workspaces/bosh-deployment/custom/add-bosh-uaa-clients.yml \
    -o /opt/spacex/workspaces/bosh-deployment/custom/ignore-server-availability-zone.yml \
    -v director_name=x-bosh \
    -v internal_cidr=10.0.0.0/20 \
    -v internal_gw=10.0.0.1 \
    -v internal_ip=10.0.0.100 \
    -v auth_url=http://<IDENTITY_IP>:5000/v2.0 \
    -v az=<AZ> \
    -v default_key_name=bosh \
    -v default_security_groups=[WISE-PaaS-nsg] \
    -v net_id=<NET_ID> \
    -v openstack_password=P@ssw0rd \
    -v openstack_username=admin \
    -v openstack_domain=default \
    -v openstack_project=WISE-PaaS \
    -v private_key=bosh.pem \
    -v region=RegionOne
```
