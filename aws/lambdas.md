# Lambdas

Push lambda code from local

```
zip -r muses.zip
aws lambda update-function-code --function-name scout --zip-file fileb://muses.zip
```
