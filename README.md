## Deploy single-app Docker app to server via Ansible

### Recommended use case

Use this repo to deploy a singleapp Docker host to a LXC server on Proxmox. 

### Examples

Two examples are included. See example for deploying Grafana or Wordpress in the ```apps``` directory.

### Supported features via Ansible variables

| Variable Name | Type | Description | Example|
|-|-|-|-|
|```root_folder``` | String | The directory for the given app. |  ```/opt/appname``` |
| ```traefik_cf```  | Bool | Make Traefik get certificates via Cloudflare DNS-01. Requires a CertAPI token via env var ```APP_CF_TOKEN```. ||
| ```traefik_certapi``` | Bool | Make Traefik get certificates via CertAPI. Requires a CertAPI token via env var ```CERTAPI_TOKEN```. ||
| ```use_custom_traefik_config``` | Bool | Use a custom Traefik config router config. Skips automatic traefik router config. ||
| ```domains``` | List | Domains for which to request a certificate or (if applicable) set up the traefik router for. | ```yaml list``` |


### Example Usage
```ansible-playbook -i apps/grafana/inventory.ini apps/grafana/playbook.yml```