# VMware Workstation Provider

*https://registry.terraform.io/providers/elsudano/vmworkstation/latest/docs#useful-commands-in-order-to-obtain-the-sourceid-or-parentid*


## Useful commands in order to obtain the SourceID or ParentID
```bash
curl -k 'https://localhost:8697/api/vms' -u '<User>:<Password>' -X GET --header 'Accept: application/vnd.vmware.vmw.rest-v1+json'
```

## Useful commands to handle the infrastructure:
```bash
export VMWS_USER="xxxx"; \
export VMWS_PASSWORD="xxxx"; \
export VMWS_URL="https://localhost:8697/api"; \
terraform plan 
```

## Debugging Option
```bash
watch -t -n 5 "cat <log file> | grep -e VMWS -e WSAPICLI -e $(date +%Y-%m-%d) | tail -15"
```