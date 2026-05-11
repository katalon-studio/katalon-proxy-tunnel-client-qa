# katalon-proxy-tunnel-client-dev

### Prerequisites                                                        
  - Helm 3.x                                                               
  - Kubernetes cluster                                                     
                                                                           
### 1. Add the Helm repository                                           
                                                                         
```sh                                                           
helm repo add katalon-tunnel https://raw.githubusercontent.com/katalon-studio/katalon-proxy-tunnel-client-qa/refs/heads/gh-pages
helm repo update                                                         
```
 
### 2. Install the chart                                                     
```                                                                
helm install tunnel-client katalon/tunnel-client \
  --set tunnel.username="<your-email>" \
  --set tunnel.apiKey="<your-api-key>" \
  --set tunnel.accountId="<your-account-uuid>" \                           
  --set tunnel.organizationId=<your-org-id>
```                                                                      

### 3. Or install with a values file                                
                                                                         
Create a values.yaml:                                           
```
tunnel:
  username: "<your-email>"
  apiKey: "<your-api-key>"                                               
  accountId: "<your-account-uuid>"
  organizationId: <your-org-id>                                          
  group: "<optional-tunnel-group>"                              
```                                                                          

Then install:
```                                                                           
  helm install -n <namespace> tunnel-client katalon/tunnel-client -f values.yaml 
```                                                                           
Upgrade
```                                                                           
  helm upgrade -n <namespace> tunnel-client katalon/tunnel-client -f values.yaml 
```
Uninstall
```
  helm uninstall -n <namespace> tunnel-client
```
