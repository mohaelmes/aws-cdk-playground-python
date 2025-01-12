# aws-cdk-playground-python

El objetivo es preparar el entorno para trabajar con AWS CDK con Python.

## Instalación y preparación de AWS CDK

1. En caso de no tener nodejs, instalar con asdf:
```bash
   asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
   asdf install nodejs 22.11.0
```
![image](https://github.com/user-attachments/assets/94ef6006-22cc-4adc-a34b-a33632b2b391)


3. Verificar la instalación:
   ```bash
   cdk --version
   ```

4. Preparar el directorio del proyecto:
   ```bash
   mkdir cdk-iam-lab
   cd cdk-iam-lab
   ```

5. Inicializar proyecto CDK con Python:
   ```bash
   cdk init app --language python
   ```

6. Inicializad el entorno de CDK en vuestra cuenta de AWS:
   ```bash
   cdk bootstrap
   ```
![image](https://github.com/user-attachments/assets/330699d3-316d-4149-a795-745d50ae1e8f)

7. Instalar dependencias del proyecto:
   ```bash
   pip install -r requirements.txt
   ```
![image](https://github.com/user-attachments/assets/5ce5b35e-9ef3-425a-a106-2a1908a3d6f9)

## Creación de Usuario IAM y Grupo con AWS CDK

El objetivo es crear un usuario IAM con permisos de PowerUserAccess usando CDK con Python.

1. Reemplazar el contenido de `cdk_iam_lab/cdk_iam_lab_stack.py` con el fichero de este repositorio


   ```python
   from aws_cdk import (
       Stack,
       CfnOutput,
       aws_iam as iam
   )
   from constructs import Construct

   class CdkIamLabStack(Stack):
       def __init__(self, scope: Construct, construct_id: str, **kwargs) -> None:
           ...

   ```

2. Sintetizar el template CloudFormation:
   ```bash
   cd ..
   cdk synth > cf.yaml
   ```
![image](https://github.com/user-attachments/assets/754ef174-4992-4cd8-a925-c8b587342f53)

3. Desplegar la infraestructura:
   ```bash
   cdk deploy
   ```
![image](https://github.com/user-attachments/assets/0b9fcdaa-bd36-4ad0-8720-37f6ee4d4400)

![image](https://github.com/user-attachments/assets/8989cad5-0268-4a65-ba58-683dce5da124)

4. Descomentad el output y volved a desplegar para ver un update.

5. Capturar los outputs del despliegue con los detalles del usuario
![image](https://github.com/user-attachments/assets/33fa7641-4645-4e81-90a1-de2e307d25a0)

6. Enviar un email al profesor con:
   - Captura del despliegue correcto
   - Evidencia de la creación del usuario y grupo en la consola de AWS
   - URL al repositorio con el código en github
![image](https://github.com/user-attachments/assets/0e2402cd-4aa2-408c-add1-5548bc73870c)

Referencias:
- [AWS CDK Python Reference](https://docs.aws.amazon.com/cdk/api/v2/python/)
- [CDK Workshop for Python](https://cdkworkshop.com/30-python.html)

