# Important

The yamls in this folder used to generate the production cluster, please be careful before you trying change any word.

All important files are store at: 
```
https://storage.huaweicloud.com/obs/?agencyId=867bf353519742aab5037d1ba0af1d4e&region=cn-north-1&locale=zh-cn#/obs/manage/mindspore-internal/object/list
```


## Jenkins System
1. **Persistentvolumeclaim**: `cce-efs-import-k3paa03e-auh7` is created on Huaweicloud manually. 

## Repo System
1. **Persistentvolumeclaim**: `cce-efs-import-k410ji5h-hinm` is created on Huaweicloud manually.

## Bot system
None

## Mail system
1. the **configmap**: `mail/dkim-config` is created manually via command:
```
curl -o mindspore.key <file_from_remote_obs> 
kubectl create configmap dkim-config --from-file=mindspore.key --namespace mail
``` 
2. the **configmap**: `mail/mailcert` is created manually via command:
```
curl -o server.crt <file_from_remote_obs> 
curl -o server.key <file_from_remote_obs>
kubectl create configmap mailcert --from-file=server.crt --from-file=server.key --namespace mail
```