# aws-cdk-playground-python

El objetivo es preparar el entorno para trabajar con AWS CDK con Python.

## Instalación y preparación de AWS CDK

1. Crear y activar un entorno virtual:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # En Windows: .venv\Scripts\activate
   ```

2. Instalar AWS CDK CLI globalmente:
   ```bash
   npm install -g aws-cdk
   ```

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

6. Instalar dependencias del proyecto:
   ```bash
   pip install -r requirements.txt
   ```

# Laboratorio 3.6.1
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
   cdk synth
   ```

3. Desplegar la infraestructura:
   ```bash
   cdk deploy
   ```

4. Capturar los outputs del despliegue con las credenciales del usuario.

5. Enviar un email al profesor con:
   - Captura del despliegue correcto
   - Evidencia de la creación del usuario y grupo en la consola de AWS
   - URL al repositorio con el código

Referencias:
- [AWS CDK Python Reference](https://docs.aws.amazon.com/cdk/api/v2/python/)
- [CDK Workshop for Python](https://cdkworkshop.com/30-python.html)

