### Enabling Nested Virtualization for VM Instances
```
gcloud compute images create ubuntu-vmx \
  --source-image ubuntu-1604-xenial-v20181204 \
  --source-image-project ubuntu-os-cloud \
  --licenses "https://www.googleapis.com/compute/v1/projects/vm-options/global/licenses/enable-vmx"

gcloud compute instances create minikube \
  --zone us-central1-b \
  --image ubuntu-vmx
```
### Get member roles
```
gcloud projects get-iam-policy ${PROJECT}  \
  --flatten="bindings[].members" \
  --format='table(bindings.role)' \
  --filter="bindings.members:${MEMBER}"
```
