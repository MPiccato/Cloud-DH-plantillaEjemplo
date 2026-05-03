Creamos la estructura base para una plantilla en CloudFormation

##Comandos para el despliegue de plantillas

aws cloudformation create-stack --stack-name mibucket --template-body file://bucket.yml --region us-east-1

###ChangeSet

aws cloudformation create-change-set --stack-name MyBucket --template-body file://bucket.yml --change-set-name versionado-etiqueta --region us-east-1

para que ejecute los cambios debo indicarle

aws cloudformation execute-change-set --stack-name MyBucket --change-set-name versionado-etiqueta --region us-east-1

aws cloudformation describe-stacks --stack-name MyBucket --region us-east-1

aws cloudformation describe-stack-events --stack-name MyBucket --region us-east-1

aws cloudformation describe-stack-resource --stack-name MyBucket --region us-east-1

##Actualizar parámetro

aws cloudformation update-stack --stack-name MyBucket --template-body file://bucket.yml --parameters ParameterKey=BucketName,ParameterValue=cloudformation-dh-bucket --region us-east-1

##Condicionales

aws cloudformation create-stack --stack-name miBucket --template-body file://bucket.yml --parameters ParameterKey=BucketName,ParameterValue=cloudformation-dh-bucket --region us-east-1

## Creacion VPC

aws cloudformation create-stack --stack-name rickandmorty-webapp --region us-east-1 --template-body file://ecs.yml
