4 - Instalación Sistema Completo en VPS Propio
🎯 Objetivo de este Tutorial
Este tutorial te guiará para instalar el sistema COMPLETO de inventario con IA en tu propio servidor VPS - la opción más económica y con control total.
⏱️ Tiempo estimado: 1-2 horas (primera vez)
 💰 Costo mensual: ~$6-7/mes
 🎓 Nivel técnico: Medio-Alto

📋 Índice
Elige tu Método
Opción A: Hostinger + Easypanel (Recomendado)
Opción B: VPS Tradicional con Docker
Configuración Común (Todas las opciones)
Solución de Problemas

🤔 Elige tu Método
Tienes 2 formas de instalar n8n en tu VPS:
📱 Opción A: Hostinger + Easypanel (MÁS FÁCIL)
👤 Para quién: Personas con conocimientos técnicos básicos-medios
✅ Ventajas:
Interfaz visual (similar a cPanel)
Instalación con 1 clic
Más fácil de mantener
No necesitas saber Docker
❌ Desventajas:
Limitado a lo que Easypanel ofrece
Capa adicional de software
🎓 Dificultad: ⭐⭐ Media
 ⏱️ Tiempo: 45 minutos
 💰 Costo: $4.99/mes (Hostinger VPS)

🔧 Opción B: VPS Tradicional con Docker
👤 Para quién: Desarrolladores o personas muy técnicas
✅ Ventajas:
Control total del sistema
Más flexible y personalizable
Aprenderás mucho
Curso gratuito disponible
❌ Desventajas:
Más complejo de configurar
Requiere conocimientos de Linux
Más tiempo de setup
🎓 Dificultad: ⭐⭐⭐⭐ Alta
 ⏱️ Tiempo: 1.5-2 horas
 💰 Costo: $4.99/mes (cualquier VPS)
📚 Curso recomendado: Curso de automatizaciones con N8N e Inteligencia Artificial - Raiola Networks (Gratis)
👉 Ir a Opción B

📊 Comparativa de Opciones
Característica
Opción A<br>Easypanel
Opción B<br>Docker Manual
Dificultad
⭐⭐ Media
⭐⭐⭐⭐ Alta
Interfaz visual
✅ Sí
❌ Solo terminal
Tiempo setup
45 min
1.5-2 horas
Mantenimiento
Fácil (clicks)
Manual (comandos)
Actualizaciones
Automáticas
Manuales
Flexibilidad
Media
Total
Curva aprendizaje
Baja
Alta
Costo
$4.99/mes
$4.99/mes
Recomendado para
No muy técnicos
Desarrolladores


Opción A: Hostinger + Easypanel
📋 Prerrequisitos
✅ Cuenta de Hostinger (o cualquier VPS)
✅ Tarjeta de crédito
✅ Archivo 2 completado (Baserow configurado)

Parte A1: Contratar VPS en Hostinger
Paso A1.1: Contratar el servicio
Ve a hostinger.com
Haz clic en "VPS Hosting"
Selecciona el plan KVM 1 (el más básico):
1 vCPU Core
4 GB RAM
50 GB SSD
$4.99/mes (o $3.99 si pagas anual)
Sistema operativo: Selecciona Ubuntu 22.04
Respaldo: NO lo necesitas (ahorra dinero)
Completa la compra
Paso A1.2: Acceder al panel de Hostinger
Inicia sesión en tu panel de Hostinger
Ve a "VPS" en el menú lateral
Haz clic en tu servidor VPS
Verás:
IP del servidor (ej: 123.45.67.89)
Usuario SSH: root
Contraseña SSH: (botón para ver/copiar)
Anota tu IP - la necesitarás constantemente.

Parte A2: Instalar Easypanel
Paso A2.1: Conectar por SSH
En Windows:
Abre PowerShell (búscalo en el menú inicio)
Escribe (reemplaza con tu IP):
 ssh root@123.45.67.89


Te pedirá la contraseña
Pega la contraseña de Hostinger (clic derecho)
Presiona Enter
En Mac/Linux:
Abre Terminal
Ejecuta el mismo comando SSH
Ingresa la contraseña
Alternativa - Browser SSH de Hostinger:
En el panel de Hostinger VPS
Haz clic en "Browser SSH" o "Abrir consola"
Se abrirá una terminal en el navegador
Paso A2.2: Instalar Easypanel
Una vez conectado al VPS, ejecuta este comando:
curl -sSL https://get.easypanel.io | sh

¿Qué hace este comando?
Descarga el instalador de Easypanel
Instala Docker automáticamente
Configura Easypanel
Toma 2-3 minutos
Verás texto scrolling - es normal. Espera hasta que termine.
Cuando termine, verás un mensaje como:
✅ Easypanel installed successfully!
Access it at: http://TU_IP:3000

Paso A2.3: Abrir puerto 3000 (importante)
En Hostinger, algunos puertos están bloqueados por defecto:
En el terminal SSH, ejecuta:

 ufw allow 3000/tcp
ufw allow 5678/tcp


Si UFW no está activo, actívalo:

 ufw enable


Verifica:

 ufw status



Parte A3: Configurar Easypanel
Paso A3.1: Acceder a Easypanel
Abre tu navegador
Ve a: http://TU_IP:3000 (reemplaza TU_IP con tu IP real)
Ejemplo: http://123.45.67.89:3000
Paso A3.2: Crear cuenta en Easypanel
Primera vez que entras:
Te pedirá crear una cuenta
Completa:
Email: Tu correo
Password: Una contraseña segura
Haz clic en "Create Account"
Ya estás dentro de Easypanel! 🎉

Parte A4: Instalar n8n en Easypanel
Paso A4.1: Crear proyecto
En Easypanel, haz clic en "Projects" (menú lateral izquierdo)
Haz clic en "+ Create"
Dale un nombre: inventario
Haz clic en "Create"
Paso A4.2: Crear servicio n8n
Dentro del proyecto, haz clic en "Create Service"
Selecciona "App"
En la lista de templates, busca: "n8n"
Haz clic en el template de n8n
Paso A4.3: Configurar n8n
Easypanel te mostrará un formulario de configuración:
Service Name: n8n (déjalo así)


Domain: Por ahora déjalo vacío (configuraremos después)


Environment Variables:


Easypanel ya incluye las básicas
Agrega estas adicionales:
 N8N_BASIC_AUTH_ACTIVE=trueN8N_BASIC_AUTH_USER=adminN8N_BASIC_AUTH_PASSWORD=TuPasswordSegura123GENERIC_TIMEZONE=America/Mexico_City
(Cambia la contraseña y zona horaria)
Haz clic en "Deploy"


Paso A4.4: Esperar deployment
Easypanel descargará e instalará n8n
Toma 2-3 minutos
Verás el estado cambiar a "Running" (verde)
Paso A4.5: Acceder a n8n
En el servicio n8n, ve a la pestaña "Domains"
Haz clic en "Add Domain"
Selecciona "Expose port"
Puerto: 5678
Haz clic en "Add"
Ahora puedes acceder a n8n en:
http://TU_IP:5678
Abre tu navegador y ve a esa URL
Te pedirá usuario y contraseña:
Usuario: admin
Contraseña: La que configuraste arriba
✅ ¡n8n instalado y funcionando!

Parte A5: Configurar n8n
Ahora salta a la sección Configuración Común más abajo para:
Importar el flujo
Configurar credenciales
Conectar con Baserow, OpenAI y Telegram

Opción B: VPS Tradicional con Docker
📋 Prerrequisitos
✅ VPS con Ubuntu 22.04 (Hostinger, DigitalOcean, Linode, etc.)
✅ Conocimientos básicos de Linux
✅ Conocimientos básicos de Docker
✅ Paciencia y ganas de aprender

📚 Curso Recomendado: Raiola Networks
Antes de empezar, altamente recomendado ver este curso GRATUITO:
🎓 Curso: "Automatizaciones con N8N e Inteligencia Artificial"
 👨‍🏫 Por: Raiola Networks
 🔗 Link: [Buscar en YouTube: "Raiola N8N curso"]
 ⏱️ Duración: ~2-3 horas
 💰 Costo: Gratis
Este curso cubre:
Instalación de n8n en VPS
Configuración con Docker
Uso de n8n con IA
Proyectos prácticos
Si ves el curso, tendrás una base sólida para seguir este tutorial.

Parte B1: Preparar el VPS
Paso B1.1: Conectar por SSH
ssh root@TU_IP_DEL_SERVIDOR

Ingresa tu contraseña cuando te la pida.
Paso B1.2: Actualizar el sistema
apt update && apt upgrade -y

Esto toma 5-10 minutos.
Paso B1.3: Instalar Docker
# Instalar Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh

# Verificar instalación
docker --version

Deberías ver algo como: Docker version 24.0.7
Paso B1.4: Instalar Docker Compose
apt install docker-compose -y

# Verificar instalación
docker-compose --version


Parte B2: Instalar n8n con Docker
Paso B2.1: Crear directorio
mkdir -p /root/n8n
cd /root/n8n

Paso B2.2: Crear archivo docker-compose.yml
nano docker-compose.yml

Pega este contenido (ajusta los valores):
version: '3.8'

services:
  n8n:
    image: n8nio/n8n:latest
    container_name: n8n
    restart: always
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=TuPasswordSegura123
      - N8N_HOST=TU_IP_DEL_SERVIDOR
      - N8N_PORT=5678
      - N8N_PROTOCOL=http
      - GENERIC_TIMEZONE=America/Mexico_City
      - WEBHOOK_URL=http://TU_IP_DEL_SERVIDOR:5678/
    volumes:
      - /root/n8n/data:/home/node/.n8n

¡IMPORTANTE! Cambia:
TuPasswordSegura123 → Tu contraseña
TU_IP_DEL_SERVIDOR → Tu IP real
America/Mexico_City → Tu zona horaria
Para guardar:
Presiona Ctrl + X
Presiona Y
Presiona Enter
Paso B2.3: Iniciar n8n
docker-compose up -d

Este comando:
Descarga la imagen de n8n (primera vez)
Crea y arranca el contenedor
Lo deja corriendo en background
Paso B2.4: Verificar que está corriendo
docker ps

Deberías ver:
CONTAINER ID   IMAGE            STATUS         PORTS                    NAMES
abc123def456   n8nio/n8n:latest   Up 2 minutes   0.0.0.0:5678->5678/tcp   n8n

Paso B2.5: Ver logs (si hay problemas)
docker logs n8n


Parte B3: Configurar Firewall
Paso B3.1: Permitir puertos necesarios
# Instalar UFW si no está instalado
apt install ufw -y

# Permitir SSH (¡IMPORTANTE! No te bloquees)
ufw allow 22/tcp

# Permitir n8n
ufw allow 5678/tcp

# Habilitar firewall
ufw enable

# Verificar
ufw status


Parte B4: Acceder a n8n
Abre tu navegador
Ve a: http://TU_IP:5678
Ingresa credenciales:
Usuario: admin
Contraseña: La que configuraste
✅ ¡n8n instalado!

Parte B5: Comandos útiles de Docker
Ver contenedores corriendo:
docker ps

Ver logs de n8n:
docker logs n8n
docker logs -f n8n  # Modo "follow" (live)

Reiniciar n8n:
docker restart n8n

Detener n8n:
docker stop n8n

Iniciar n8n:
docker start n8n

Actualizar n8n:
cd /root/n8n
docker-compose pull
docker-compose up -d

Eliminar n8n (cuidado):
docker-compose down


Configuración Común
Esta sección aplica para AMBAS opciones (A y B).
Una vez que tienes n8n corriendo, los siguientes pasos son iguales.

Parte C1: Configurar Baserow
Si ya completaste el Archivo 2:
✅ Ya tienes todo listo. Solo necesitas:
API Token de Baserow
Database ID
Table ID
Si NO has completado el Archivo 2:
🔙 Ve al Archivo 2 y completa la configuración primero.

Parte C2: Configurar OpenAI
Sigue exactamente los mismos pasos del Archivo 3 - Parte 2.
Resumen:
Crear cuenta en platform.openai.com
Agregar método de pago
Configurar límite de gasto ($10)
Generar API Key
Guardar la clave

Parte C3: Crear Bot de Telegram
Sigue exactamente los mismos pasos del Archivo 3 - Parte 3.
Resumen:
Buscar @BotFather en Telegram
Crear nuevo bot con /newbot
Guardar el token
Obtener tu Chat ID de @userinfobot
Iniciar el bot (presionar START)

Parte C4: Importar el Flujo en n8n
Paso C4.1: Acceder a n8n
Ve a tu n8n:
Opción A (Easypanel): http://TU_IP:5678
Opción B (Docker): http://TU_IP:5678
Paso C4.2: Importar el workflow
Haz clic en el menú hamburguesa (☰)
Selecciona "Workflows"
Haz clic en "Import"
Pega el JSON del flujo: [INCLUIR JSON AQUÍ]
Haz clic en "Import"

Parte C5: Configurar Credenciales
Paso C5.1: OpenAI
En n8n, ve a "Credentials"
Haz clic en "Add credential"
Busca "OpenAI"
Completa:
Name: OpenAI account
API Key: Tu clave de OpenAI
Haz clic en "Save"
Paso C5.2: Telegram
"Add credential" → "Telegram API"
Completa:
Name: Telegram account
Access Token: Token de BotFather
"Save"
Paso C5.3: Baserow
"Add credential" → "Baserow API"
Completa:
Name: Baserow account
Host: https://api.baserow.io
Username: Tu email de Baserow
Password: Tu contraseña de Baserow
O mejor:
API Token: Tu token de Baserow
"Save"

Parte C6: Configurar el Flujo
Paso C6.1: Configurar filtro de usuarios
Abre el workflow importado
Haz clic en el nodo "If1"
Cambia 7316640681 por TU Chat ID
Paso C6.2: Configurar nodos de OpenAI
Para cada nodo de OpenAI (3 en total):
Haz clic en el nodo
Selecciona credencial: OpenAI account
Modelo: gpt-4o-mini
Paso C6.3: Configurar nodos de Telegram
Para cada nodo de Telegram (3 en total):
Haz clic en el nodo
Selecciona credencial: Telegram account
Paso C6.4: Configurar nodo de Baserow
Haz clic en el nodo de Baserow
Selecciona credencial: Baserow account
Database ID: Tu ID de Baserow
Table ID: Tu ID de tabla
Verifica mapeo de campos
Paso C6.5: Guardar y activar
Haz clic en "Save"
Activa el flujo (switch en verde)

Parte C7: Probar el Sistema
Prueba básica:
Abre Telegram
Busca tu bot
Envía: Hola
Debería responder.
Prueba completa:
Envía: Quiero agregar un artículo
Responde con datos de prueba
Verifica en Baserow que se guardó
✅ ¡Sistema funcionando!

🔧 Mantenimiento
Actualizar n8n (Opción A - Easypanel):
En Easypanel, ve al servicio n8n
Haz clic en "Deploy"
Selecciona "Pull latest image"
Easypanel actualizará automáticamente
Actualizar n8n (Opción B - Docker):
cd /root/n8n
docker-compose pull
docker-compose up -d

Backups (Opción A):
En Easypanel, ve a tu servicio
Haz clic en "Volumes"
Descarga el volumen de datos
Backups (Opción B):
# Backup de datos de n8n
tar -czf n8n-backup-$(date +%Y%m%d).tar.gz /root/n8n/data

# Mover a un lugar seguro (ej: tu computadora)
# Usa SFTP o SCP

Monitoreo:
# Ver uso de recursos
docker stats

# Ver logs en tiempo real
docker logs -f n8n


Solución de Problemas
Problema 1: No puedo acceder a n8n
Opción A (Easypanel):
Verifica que el servicio esté "Running" en Easypanel
Verifica que el puerto 5678 esté expuesto
Revisa firewall: ufw status
Opción B (Docker):
# Ver si el contenedor está corriendo
docker ps

# Si no está, iniciarlo
docker start n8n

# Ver logs para errores
docker logs n8n

Problema 2: El bot no responde
Igual que en Archivo 3:
Flujo debe estar activo (verde)
Verifica credenciales
Revisa logs en n8n: Menu → Executions
Problema 3: Error "Cannot connect to Docker"
Opción B:
# Reiniciar servicio de Docker
systemctl restart docker

# Verificar estado
systemctl status docker

Problema 4: n8n se reinicia solo
Causa: Falta de memoria RAM
Solución:
Verifica uso: free -h
Si tienes < 500MB libre, upgrade tu VPS
O cierra servicios innecesarios
Problema 5: "Port 5678 already in use"
# Ver qué está usando el puerto
lsof -i :5678

# Matar el proceso
kill -9 [PID]

# Reiniciar n8n
docker restart n8n


🔒 Seguridad Adicional
Cambiar puerto por defecto:
En docker-compose.yml:
ports:
  - "8080:5678"  # Accederás por puerto 8080

Configurar HTTPS (avanzado):
Requiere:
Dominio propio
Certificado SSL (Let's Encrypt)
Nginx como reverse proxy
Recomendación: Usa el curso de Raiola que explica esto.
Limitar acceso por IP:
ufw delete allow 5678/tcp
ufw allow from TU_IP_CASA to any port 5678


💰 Optimización de Costos
Reducir uso de OpenAI:
Ya usas gpt-4o-mini (correcto)
Configura límites estrictos
Monitorea uso semanalmente
Reducir uso de VPS:
Apaga servicios innecesarios
Usa el plan más básico
Considera shared VPS si tu tráfico es bajo
Uso combinado:
Empieza con Opción A (Easypanel) - más fácil
Cuando domines, migra a Opción B - más control

📚 Recursos Adicionales
Para Opción A (Easypanel):
Documentación Easypanel
Video tutoriales
Para Opción B (Docker):
Documentación n8n Docker
Curso Raiola Networks
Docker Documentation
Comunidad:
n8n Community Forum
n8n Discord

🎓 Siguientes Pasos
Domina lo básico: Usa el sistema por 1-2 semanas
Personaliza: Ajusta prompts, campos, categorías
Expande: Agrega más funcionalidades
Automatiza más: Crea workflows adicionales
Ideas para expandir:
Búsqueda de artículos por Telegram
Alertas de stock bajo automáticas
Reportes semanales por email
Integración con códigos QR
Fotos de artículos (requiere modificación)

💡 Consejos Finales
Opción A (Easypanel):
✅ Ideal si valoras facilidad sobre control total
✅ Perfecto para aprender n8n sin complejidad
✅ Fácil de mantener y actualizar
Opción B (Docker):
✅ Ideal si quieres aprender Docker y Linux
✅ Más control y flexibilidad
✅ Mejor para proyectos más avanzados
Ambas opciones son válidas - elige según tu nivel de comodidad técnica.

¡Felicidades por completar la instalación! 🎉
Ahora tienes tu propio sistema de inventario profesional por solo $6-7/mes.
Última actualización: Enero 2025
 Versión: 2.0 (con Baserow)

