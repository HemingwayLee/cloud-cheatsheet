# TODO: restructure them

# Note
## Azure
* show secret in azure devops
```
echo $(acr.secret)
```

* deployment
```
az container create --resource-group lee-testing --name lee-tesseract-$(Release.AttemptNumber) --registry-username leeTestingRegistry --registry-password $(acr.secret) --image leetestingresigtry.azurecr.io/finetuning_tesseract:4150 --command-line "/bin/sh -c '/root/src/traintest.sh $(param.path) $(param.lang)'" --cpu $(acr.cpu) --memory $(acr.memory) --restart-policy Never
```

* parse json
```
az container show --name lee-tesseract-15 --resource-group lee-testing | python -c "import sys, json; print(json.load(sys.stdin)['containers'][0]['instanceView'])"
```

* Important things for deployment
  * log files
  * budget for cloud, memory, cpu
  * checker for bash script
  * fake training/testing data in local
  * name-based parameters in bash script
  * put secret into variable


