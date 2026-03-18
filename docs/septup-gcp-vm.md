Infraestructura en la nube - Despliegue de n8n en GCP

Descripción
Se Implementó una infraestructura en Google Cloud Platform para ejecutar workflows automatizados utilizando n8n, asegurando disponibilidad, acceso seguro mediante HTTPS y escalabilidad.

Configuración del entorno GCP
- Creación y configuración de proyecto en GCP
- Selección de región: southamerica-west1
- Creación de máquina virtual (Compute Engine).
IP Estática
Se reservó una IP externa estática para la máquina virtual.
Motivo:
Evitar cambios de IP tras reinicios, asegurando estabilidad en la resolución del dominio.
Configuración del Firewall
Se habilitaron las siguientes reglas de ingreso:
- TCP 80 (HTTP)
- TCP 443 (HTTPS)
- TCP 22 (SSH)
Motivo:
Permitir acceso web seguro y administración remota del servidor.
Contenerización con Docker
Se instaló Docker y Docker Compose para ejecutar n8n en un entorno aislado.
Beneficios:

- Portabilidad del sistema
- Facilidad de despliegue
- Escalabilidad

sudo apt update && sudo apt -y upgrade
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin

Despliegue de n8n
Se desplegó n8n dentro de un contenedor Docker con las siguientes características:
Ejecución en entorno local
Uso de variables de entorno para configuración segura
Persistencia de datos mediante volúmenes
docker compose up -d
docker ps

Configuración de dominio y DNS
Se configuraron registros tipo A apuntando a la IP estática de la VM.

Resultado:
 Acceso al sistema mediante un dominio personalizado.

Implementación de HTTPS
Se utilizó Caddy como reverse proxy para:
Generar certificados SSL automáticamente (Let's Encrypt)
Redirigir tráfico HTTPS (puerto 443) hacia n8n

Validación del sistema
Se realizaron las siguientes verificaciones:
-Resolución de DNS correcta
-Acceso mediante HTTPS
-Funcionamiento de n8n desde el dominio

Resultados
Infraestructura productiva capaz de:
Ejecutar workflows automatizados de forma continua
Proveer acceso seguro mediante HTTPS
Integrarse con pipelines de datos y servicios de IA

Tecnologías Utilizadas

-Google Cloud Platform (Compute Engine)
-Docker
-N8N
-Caddy (Reverse Proxy)
-DNS Management




Por razones de confidencialidad, los detalles específicos del desarrollo están protegidos. Este documento presenta una visión general de la metodología y los logros alcanzados sin comprometer información sensible de la organización.
