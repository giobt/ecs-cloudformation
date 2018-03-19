# Demo AWS ECS
## Instrucciones:
1. clonar repositorio:
  `git clone git@github.com:giobt/ecs-cloudformation.git`
2. subir archivos a s3
3. copiar url del archivo _ecs-ec2.yml_
4. ejecutar en CloudFormation

Ejemplo de lanzamiento desde terminal:
```
aws cloudformation create-stack \
  --stack-name ecs-demo \
  --capabilities CAPABILITY_IAM \
  --template-url https://s3.amazonaws.com/gabalconi/ecs-ec2.yml \
  --parameters \
    ParameterKey=KeyName,ParameterValue=demo-keypair \
    ParameterKey=VpcCIDR,ParameterValue=10.32.0.0/16 \
    ParameterKey=DesiredCapacity,ParameterValue=1 \
    ParameterKey=MaxSize,ParameterValue=1 \
    ParameterKey=InstanceType,ParameterValue=t2.micro
```
