🚀 Archivo 3 - Instalación Sistema Completo con n8n Cloud
🎯 Objetivo de este Tutorial
Este tutorial te guiará para instalar el sistema COMPLETO de inventario con IA usando n8n Cloud - la forma MÁS RÁPIDA y FÁCIL sin necesidad de conocimientos técnicos.
⏱️ Tiempo estimado: 30-40 minutos
 💰 Costo mensual: ~$22/mes ($20 n8n + ~$2 OpenAI)
 🎓 Nivel técnico: Básico - No necesitas programar

📋 Índice
Prerrequisitos
Parte 1: Configurar Baserow
Parte 2: Configurar OpenAI
Parte 3: Crear Bot de Telegram
Parte 4: Crear Cuenta n8n Cloud
Parte 5: Importar el Flujo
Parte 6: Configurar Credenciales
Parte 7: Configurar el Flujo
Parte 8: Probar el Sistema
Solución de Problemas

✅ Prerrequisitos
Antes de empezar, necesitas tener:
☑️ Archivo 2 completado - Tu base de datos Baserow configurada
☑️ Tarjeta de crédito - Para n8n Cloud y OpenAI
☑️ Cuenta de Telegram - En tu teléfono
☑️ 1 hora de tiempo - Para completar todo sin prisa

Parte 1: Configurar Baserow
Si ya completaste el Archivo 2:
✅ Ya tienes todo listo. Solo necesitas tener a mano:
API Token de Baserow
Database ID
Table ID
Si NO has completado el Archivo 2:
🔙 Ve al Archivo 2 y completa la configuración de Baserow primero. Es necesario para continuar.

Parte 2: Configurar OpenAI
Paso 2.1: Crear cuenta en OpenAI
Ve a platform.openai.com
Haz clic en "Sign up"
Regístrate con:
Tu email y contraseña, O
Tu cuenta de Google/Microsoft
Verifica tu email (revisa tu bandeja)
Verifica tu teléfono (recibirás un SMS)
Paso 2.2: Agregar método de pago
⚠️ Importante: OpenAI requiere método de pago antes de usar la API.
Haz clic en tu perfil (esquina superior derecha)
Ve a "Settings" → "Billing"
Haz clic en "Add payment method"
Ingresa tu tarjeta de crédito/débito
Haz clic en "Add payment method"
Paso 2.3: Configurar límite de gasto
Para evitar sorpresas en tu factura:
En "Billing" → "Limits"
Configura "Hard limit": $10.00 (o lo que prefieras)
Configura "Soft limit": $5.00
Haz clic en "Save"
Esto limitará tu gasto mensual. Para un inventario típico, gastarás menos de $2/mes.
Paso 2.4: Agregar saldo inicial (opcional)
En "Billing" → "Overview"
Haz clic en "Add to credit balance"
Agrega $5 para empezar (opcional - también puedes usar auto-recharge)
Paso 2.5: Generar API Key
Ve a "API keys" en el menú lateral
Haz clic en "Create new secret key"
Configura:
Name: n8n-inventario
Permissions: All (puede dejarse por defecto)
Haz clic en "Create secret key"
¡MUY IMPORTANTE! Copia la clave y guárdala:
Se ve así: sk-proj-abc123xyz789...
Solo se muestra UNA vez
Guárdala en un archivo de texto seguro
✅ OpenAI configurado

Parte 3: Crear Bot de Telegram
Paso 3.1: Abrir BotFather
Abre Telegram en tu teléfono
En el buscador, escribe: @BotFather
Haz clic en el usuario verificado (tiene ✅)
Haz clic en "START"
Paso 3.2: Crear el bot
Escribe: /newbot
BotFather te preguntará el nombre:
Escribe: Mi Inventario Bot (o el nombre que quieras)
Luego te pedirá el username:
Debe terminar en _bot o Bot
Ejemplo: miinventario_bot
Debe ser único en Telegram
Si está tomado, prueba con: inventario_[tunombre]_bot
Paso 3.3: Guardar el Token
BotFather te enviará un mensaje con:
Confirmación de creación
El token de tu bot (línea larga como: 1234567890:ABCdef...)
Copia este token y guárdalo - lo necesitarás para n8n.
Paso 3.4: Obtener tu Chat ID
En Telegram, busca: @userinfobot
Haz clic en "START"
Envíale cualquier mensaje
Te responderá con tu información, incluyendo tu ID (un número como: 7316640681)
Guarda este número - es tu Chat ID personal
Paso 3.5: Iniciar tu bot (importante)
Busca tu bot recién creado en Telegram
Haz clic en "START"
Esto es necesario para que el bot pueda enviarte mensajes
✅ Bot de Telegram creado

Parte 4: Crear Cuenta n8n Cloud
Paso 4.1: Registrarse en n8n Cloud
Ve a n8n.cloud
Haz clic en "Start free trial"
Completa el registro:
Email: Tu correo electrónico
Password: Una contraseña segura
First name: Tu nombre
Last name: Tu apellido
Acepta términos y condiciones
Haz clic en "Create account"
Paso 4.2: Verificar email
Revisa tu bandeja de entrada
Abre el email de n8n
Haz clic en "Verify email"
Paso 4.3: Crear tu instancia
Una vez verificado, n8n te pedirá crear una instancia
Configura:
Instance name: inventario-production
Region: Elige la más cercana a ti
América: US East o US West
Europa: EU Central
Haz clic en "Create instance"
Espera 2-3 minutos mientras se crea
Paso 4.4: Acceder a tu n8n
Cuando esté lista, haz clic en "Open instance"
Se abrirá una nueva pestaña con tu n8n
¡Ya estás dentro!
Paso 4.5: Información sobre el trial
Tienes 14 días gratis para probar
Incluye 5,000 ejecuciones
No necesitas tarjeta de crédito para el trial
Después del trial:
Starter: $20/mes (5,000 ejecuciones/mes)
Pro: $50/mes (50,000 ejecuciones/mes)
Para un inventario típico, el plan Starter es suficiente.
✅ n8n Cloud configurado

Parte 5: Importar el Flujo
Paso 5.1: Obtener el archivo JSON del flujo
[AQUÍ SE INCLUIRÁ EL ARCHIVO JSON DEL FLUJO]
Copia todo el contenido del archivo Sistema de Inventario - Baserow.json
Paso 5.2: Importar en n8n
En n8n, haz clic en el menú hamburguesa (☰) arriba a la izquierda
Selecciona "Workflows"
Haz clic en "Import workflow"
Selecciona "Import from File" o "Import from URL"
Si usas "Import from File":
Haz clic en "Select file"
Sube el archivo JSON
Si usas "Import from Text":
Pega todo el contenido JSON
Haz clic en "Import"
Paso 5.3: Abrir el flujo
El flujo aparecerá en tu lista de workflows
Se llamará "Sistema de Inventario"
Haz clic para abrirlo
Verás todos los nodos conectados
✅ Flujo importado

Parte 6: Configurar Credenciales
Ahora vamos a conectar todas las cuentas que creamos.
Paso 6.1: Agregar credencial de OpenAI
En el menú lateral izquierdo, haz clic en "Credentials"
Haz clic en "Add credential"
Busca y selecciona "OpenAI"
Completa:
Credential name: OpenAI account
API Key: Pega tu API Key (sk-proj-...)
Haz clic en "Save"
Paso 6.2: Agregar credencial de Telegram
Haz clic en "Add credential" nuevamente
Busca y selecciona "Telegram API"
Completa:
Credential name: Telegram account
Access Token: Pega el token de BotFather
Haz clic en "Save"
Paso 6.3: Agregar credencial de Baserow
Haz clic en "Add credential"
Busca y selecciona "Baserow API"
Completa:
Credential name: Baserow account
Host: https://api.baserow.io (déjalo por defecto)
API Token: Pega tu token de Baserow (del Archivo 2)
Haz clic en "Save"
✅ Todas las credenciales agregadas

Parte 7: Configurar el Flujo
Ahora vamos a personalizar el flujo con tus datos.
Paso 7.1: Configurar filtro de usuarios (nodo "If1")
Este nodo permite que solo tú y personas autorizadas usen el bot.
Haz clic en el nodo "If1"
Verás una condición:
{{$json.message.from.id}} equal to 7316640681
Reemplaza 7316640681 con TU Chat ID (el que obtuviste de @userinfobot)
Si quieres agregar más usuarios:
Haz clic en "Add condition"
Agrega sus Chat IDs uno por uno
Paso 7.2: Configurar nodos de OpenAI
Hay 3 nodos de OpenAI que necesitan tus credenciales:
Para cada nodo (OpenAI Chat Model, OpenAI Chat Model1, OpenAI Chat Model2):
Haz clic en el nodo
En "Credential to connect with", selecciona: OpenAI account
Verifica que el modelo sea: gpt-4o-mini
Haz clic fuera del nodo para guardar
Paso 7.3: Configurar nodos de Telegram
Hay 3 nodos de Telegram:
Para cada nodo (Telegram Trigger, Send a text message, Send a text message1):
Haz clic en el nodo
En "Credential to connect with", selecciona: Telegram account
Haz clic fuera del nodo
Paso 7.4: Configurar nodo de Baserow
Haz clic en el nodo "Baserow" (donde dice "Agregar Artículo")
En "Credential to connect with", selecciona: Baserow account
En "Database ID", ingresa tu Database ID de Baserow
En "Table ID", ingresa tu Table ID de Baserow
Verifica que el mapeo de campos sea correcto:
Código → {{ $json.output.codigo }}
Nombre → {{ $json.output.nombre }}
Cantidad → {{ $json.output.cantidad }}
etc.
Paso 7.5: Configurar Chat Memory (opcional)
Haz clic en el nodo "Chat Memory"
En "Session Key", cambia el valor fijo por:
 {{ $json.message.from.id }}
Esto permite que cada usuario tenga su propia memoria de conversación.
Paso 7.6: Guardar el flujo
Haz clic en "Save" (esquina superior derecha)
Confirma que se guardó correctamente
✅ Flujo configurado

Parte 8: Probar el Sistema
Paso 8.1: Activar el flujo
En la parte superior del flujo, verás un switch "Inactive/Active"
Haz clic para activarlo
Debe cambiar a "Active" en color verde
Esto hace que el bot esté escuchando mensajes 24/7
Paso 8.2: Hacer prueba inicial
Abre Telegram en tu teléfono
Busca tu bot (el que creaste)
Envía un mensaje simple: Hola
El bot debería responder con algo como:
"¡Hola! Soy tu asistente de inventario. ¿En qué puedo ayudarte?"
Paso 8.3: Probar registro completo
Ahora vamos a registrar un artículo de prueba:
Tú: Quiero agregar un artículo
Bot: Te preguntará por todos los campos:
"Perfecto, te ayudaré a registrar el artículo. Por favor proporcióname: • Código (ej: PRUEBA-001) • Nombre del artículo • Cantidad • Categoría • ..."
Tú: Responde con algo como:
Código PRUEBA-001
Nombre Artículo de prueba
Cantidad 5
Categoría Otros
Condición Bueno
Ubicación Oficina

Bot: Debería responder:
"✅ ¡Artículo registrado exitosamente en el inventario! 📦 Código: PRUEBA-001 📝 Nombre: Artículo de prueba ..."
Paso 8.4: Verificar en Baserow
Ve a tu Baserow
Abre tu tabla "Artículos"
Deberías ver una nueva fila con el artículo que acabas de registrar
¡Todos los datos están ahí!
✅ ¡Sistema funcionando perfectamente!

🎉 ¡Felicidades!
Ya tienes tu sistema completo funcionando:
✅ Bot de Telegram activo
✅ IA conversacional en español
✅ Registro automático en Baserow
✅ Todo funcionando 24/7

🔧 Personalización Adicional
Agregar más usuarios autorizados:
Pide a la persona que obtenga su Chat ID de @userinfobot
En n8n, edita el nodo "If1"
Agrega una nueva condición con su Chat ID
Modificar las preguntas del bot:
Haz clic en el nodo "Agente de Inventario"
Edita el "System Message"
Modifica las preguntas según tus necesidades
Agregar campos nuevos:
Agrega el campo en Baserow primero
Actualiza el prompt del agente
Actualiza el mapeo en el nodo de Baserow
Cambiar idioma:
Edita los prompts en los nodos de OpenAI
Cambia todas las instrucciones al idioma deseado

💰 Gestión de Costos
Monitorear uso de n8n:
En n8n Cloud, ve a "Settings" → "Usage"
Verás cuántas ejecuciones has usado
Cada mensaje en Telegram = 1 ejecución
Monitorear uso de OpenAI:
Ve a platform.openai.com/usage
Verás tu consumo diario
Típicamente: $0.05-0.10 por día de uso normal
Reducir costos:
Usa gpt-4o-mini (ya configurado) - más barato que GPT-4
Desactiva el flujo cuando no lo necesites
Configura límites en OpenAI

📊 Reportes y Análisis
Exportar datos de Baserow:
En Baserow, haz clic en "..." (tres puntos)
Selecciona "Export"
Elige formato: CSV, JSON o XML
Úsalo en Excel para análisis
Crear reportes automáticos (avanzado):
Puedes crear workflows adicionales en n8n para:
Enviar resumen semanal por email
Alertas cuando el stock está bajo
Reportes mensuales automáticos

🔒 Seguridad y Privacidad
Protege tus credenciales:
✅ Nunca compartas tu API Key de OpenAI
✅ Nunca compartas tu token de Telegram
✅ Nunca compartas tu token de Baserow
✅ Usa contraseñas seguras en todas las cuentas
Backups:
Baserow: Exporta tu base de datos semanalmente
n8n: El flujo se guarda automáticamente en n8n Cloud
Exporta el JSON del flujo mensualmente como backup
Usuarios autorizados:
Solo agrega Chat IDs de personas de confianza
Revisa periódicamente la lista de usuarios autorizados
Elimina usuarios que ya no necesiten acceso

Solución de Problemas
Problema 1: El bot no responde
Posibles causas:
Flujo no está activo
Token de Telegram incorrecto
No presionaste START en el bot
Solución:
Verifica que el flujo esté Active (verde)
Revisa la credencial de Telegram
Asegúrate de haber presionado START en el bot
Ve a "Executions" en n8n para ver errores
Problema 2: Error de OpenAI
Posibles causas:
API Key inválida
Sin saldo en la cuenta
Límite de gasto alcanzado
Solución:
Verifica tu API Key en OpenAI
Revisa tu saldo en Billing
Aumenta tu límite si es necesario
Agrega saldo si está en $0
Problema 3: No se guarda en Baserow
Posibles causas:
Token de Baserow incorrecto
Database ID o Table ID incorrectos
Permisos insuficientes
Solución:
Re-genera el token en Baserow
Verifica los IDs en la URL de Baserow
Asegúrate de usar el token correcto
Problema 4: El bot dice "undefined"
Causa: Error en el mapeo de datos
Solución:
Verifica que todos los nodos tengan credenciales
Revisa el nodo "Set" después de "Agregar Artículo"
Asegúrate de que el mapeo en Chat ID use la expresión correcta
Problema 5: "Rate limit exceeded"
Causa: Demasiadas peticiones a OpenAI
Solución:
Espera 1 minuto e intenta de nuevo
Si persiste, verifica tu cuenta de OpenAI
Puede necesitar upgrade de plan (muy raro)

📈 Después del Trial
Cuando se acaben los 14 días:
n8n te enviará un email recordatorio
Tendrás que agregar método de pago
Se cobrará automáticamente $20/mes (plan Starter)
Si decides no continuar:
Exporta tus datos de Baserow (CSV)
Exporta el flujo de n8n (JSON)
Cancela la suscripción en n8n Cloud
Puedes migrar a VPS después (Archivo 4)
Si quieres cambiar de plan:
Ve a "Settings" → "Billing" en n8n Cloud
Selecciona el plan que necesites
El cambio es inmediato

🚀 Siguientes Pasos
Mejoras sugeridas:
Personaliza las categorías en Baserow según tu inventario
Agrega más usuarios al filtro del bot
Crea vistas personalizadas en Baserow
Configura alertas para stock bajo
Entrena a tu equipo en el uso del bot
Funcionalidades avanzadas:
Agregar búsqueda de artículos por Telegram
Reportes automáticos por email
Integración con hojas de cálculo
Fotos de artículos (requiere modificación del flujo)

📞 Recursos y Soporte
Documentación oficial:
n8n Documentation
Baserow Documentation
OpenAI Documentation
Telegram Bot API
Comunidades:
n8n Community Forum
Baserow Discord
n8n Discord
Videos tutoriales:
Busca "n8n tutorial" en YouTube
Canal oficial de n8n
Tutoriales en español disponibles

💡 Consejos Finales
Empieza despacio: Prueba con artículos de ejemplo primero
Documenta cambios: Si modificas el flujo, anota qué cambiaste
Haz backups regulares: Exporta Baserow y el flujo mensualmente
Monitorea costos: Revisa tu uso de OpenAI semanalmente
Capacita a tu equipo: Muéstrales cómo usar el bot correctamente

¡Felicidades por completar la instalación! 🎉
Ahora tienes un sistema de inventario profesional con IA que funciona 24/7 desde tu teléfono.
Última actualización: Enero 2025
 Versión: 2.0 (con Baserow)

