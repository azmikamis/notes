### Get member roles
```
gcloud projects get-iam-policy ${PROJECT}  \
  --flatten="bindings[].members" \
  --format='table(bindings.role)' \
  --filter="bindings.members:${MEMBER}"
```
