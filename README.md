# Terraform Template para VM en Azure.

Este repositorio contiene un template de Terraform que crea una infraestructura en Azure compuesta por:

- **Grupo de Recursos**: Se crea con el nombre `rg-<nombre>`.
- **Virtual Network**: Llamada `vn-<nombre>`, con una subnet definida en `192.168.100.0/24`.
- **Network Security Group (NSG)**: Configurado para permitir tráfico entrante en el puerto 22.
- **IP Pública y NIC**: Asociadas a la máquina virtual.
- **Máquina Virtual**: Se despliega una VM con Ubuntu 22.04, nombrada `vm-<nombre>`, utilizando el usuario y la contraseña que se ingresan al momento de ejecutar el script.

## Cómo Implementarlo

1. **Instala Terraform y CLI de Azure**  
   Asegúrate de tener instalada la última versión de [Terraform](https://www.terraform.io/downloads).
   Instala la CLI de Azure [CLI de Azure](https://learn.microsoft.com/es-es/cli/azure/install-azure-cli)

3. **Configura las variables**  
   El template utiliza las variables `name`, `admin_username` y `admin_password`. Puedes definirlas directamente o pasarlas como parámetros en la línea de comandos.

4. **Incia sesión en Azure e inicializa Terraform**  
   Ejecuta el siguiente comando en el directorio del template:
   ```bash
   az login
   terraform init
   
5. **Planifica la infraestructura**  
   Ejecuta el siguiente comando en el directorio del template:
   ```bash
   terraform plan

 6. **Aplica la configuración en Azure**  
   Ejecuta el siguiente comando en el directorio del template:
   ```bash
   terraform apply
