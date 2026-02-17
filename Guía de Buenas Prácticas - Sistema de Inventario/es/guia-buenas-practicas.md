# 📦 Guía de Buenas Prácticas - Sistema de Inventario

## 🎯 Objetivo

Este documento te ayudará a mantener un inventario organizado, consistente y fácil de consultar utilizando el bot de Telegram.

---

## ✅ Campos Obligatorios

Cada artículo DEBE tener estos 3 campos:

1. **Código** - Identificador único del artículo
2. **Nombre** - Descripción del artículo
3. **Cantidad** - Número de unidades

Los demás campos (Categoría, Condición, Donador, Fecha-Recibido, Ubicación, Notas) son opcionales pero muy recomendados.

---

## 📝 Buenas Prácticas por Campo

### 1. CÓDIGO

**✅ Correcto:**
- `SILLA-001`, `MESA-045`, `COMP-023`
- `LAP-2024-001`, `DON-MARIA-15`

**❌ Evitar:**
- `silla1` (usar mayúsculas)
- `Mesa 01` (evitar espacios, usar guión)
- Códigos duplicados

**Reglas:**
- Siempre en MAYÚSCULAS
- Usar formato: `CATEGORÍA-NÚMERO` o `CATEGORÍA-AÑO-NÚMERO`
- Sin espacios (usar guiones `-`)
- Cada código debe ser único
- **Sugerencia:** Define prefijos para cada categoría (ej: SILLA, MESA, COMP para computadoras)

---

### 2. NOMBRE

**✅ Correcto:**
- `Silla de oficina ergonómica`
- `Mesa de conferencia rectangular`
- `Laptop HP Pavilion 15"`

**❌ Evitar:**
- `silla` (muy vago)
- `SILLA DE OFICINA` (no usar todo mayúsculas)
- `silla d ofinina` (errores ortográficos)

**Reglas:**
- Primera letra en mayúscula, resto en minúscula
- Ser específico y descriptivo
- Usar tildes correctamente (silla, lámpara, teléfono)
- Incluir marca/modelo si es relevante
- Evitar abreviaturas confusas

---

### 3. CATEGORÍA

**✅ Correcto:**
- `Mobiliario`, `Electrónica`, `Papelería`
- `Herramientas`, `Equipos médicos`, `Libros`

**❌ Evitar:**
- `mobiliario` (sin mayúscula inicial)
- `Mob` (abreviaturas)
- Usar diferentes nombres para lo mismo: `Muebles` y `Mobiliario`

**Reglas:**
- Definir un catálogo fijo de categorías
- Primera letra en mayúscula
- Ser consistente (siempre usar el mismo nombre)
- Mantener una lista de categorías válidas

**Categorías sugeridas:**
- Mobiliario
- Electrónica
- Computadoras
- Herramientas
- Papelería
- Material médico
- Deportes
- Libros
- Cocina
- Limpieza

---

### 4. CANTIDAD

**✅ Correcto:**
- `1`, `5`, `25`, `100`

**❌ Evitar:**
- `cinco` (usar números)
- `5 unidades` (solo el número)
- Dejar vacío

**Reglas:**
- Siempre usar números
- Sin unidades de medida en este campo (ej: no poner "5 kg")
- Este campo es OBLIGATORIO

---

### 5. CONDICIÓN

**✅ Correcto (usar solo estas opciones):**
- `Nuevo`
- `Excelente`
- `Bueno`
- `Regular`
- `Malo`
- `Para reparar`

**❌ Evitar:**
- `mas o menos` (usar opciones estándar)
- `bueno` (sin mayúscula inicial)
- Inventar nuevos estados

**Reglas:**
- Usar SOLO las opciones listadas arriba
- Primera letra en mayúscula
- Ser objetivo en la evaluación

---

### 6. DONADOR

**✅ Correcto:**
- `María González`
- `Empresa XYZ S.A.`
- `Fundación Ayuda`
- `Anónimo` (si no se conoce)

**❌ Evitar:**
- `maria` (sin mayúsculas en nombres propios)
- `Ma` (abreviaturas)

**Reglas:**
- Nombres propios con mayúscula inicial
- Usar nombre completo cuando sea posible
- Si no aplica, dejar vacío o poner "N/A"

---

### 7. FECHA-RECIBIDO

**✅ Correcto:**
- `15/01/2025`
- `03/12/2024`

**❌ Evitar:**
- `15-01-2025` (usar `/` no `-`)
- `enero 15` (usar formato DD/MM/AAAA)
- `2025-01-15` (no formato ISO)

**Reglas:**
- Formato OBLIGATORIO: **DD/MM/AAAA**
- Siempre con 2 dígitos para día y mes
- 4 dígitos para año
- Usar `/` como separador

---

### 8. UBICACIÓN

**✅ Correcto:**
- `Bodega A - Estante 3`
- `Oficina principal - Escritorio 5`
- `Almacén 2 - Sección norte`

**❌ Evitar:**
- `bodega` (ser más específico)
- `por ahí` (vago)
- Ubicaciones inconsistentes

**Reglas:**
- Ser específico
- Usar formato: `Área principal - Detalle específico`
- Mantener nombres de áreas consistentes
- Ayuda a encontrar artículos rápidamente

**Ubicaciones sugeridas (adaptar a tu espacio):**
- Bodega A, Bodega B, Bodega C
- Oficina 1, Oficina 2
- Almacén general
- Sala de reuniones
- Recepción
- Área de mantenimiento

---

### 9. NOTAS

**✅ Correcto:**
- `Requiere cable de poder adicional`
- `Donado por campaña navideña 2024`
- `Una silla tiene rueda rota`

**❌ Evitar:**
- Información que debería ir en otros campos
- Notas excesivamente largas

**Reglas:**
- Información adicional relevante
- Usar tildes y ortografía correcta
- Ser conciso pero claro
- No repetir información de otros campos

---

## 🤖 Usando el Bot de Telegram

### Ejemplo de conversación CORRECTA:

**Usuario:**
```
Quiero agregar sillas
```

**Bot:**
```
Perfecto, te ayudaré a registrar las sillas. Por favor proporcióname la 
siguiente información (solo Código, Nombre y Cantidad son obligatorios):

• Código (ej: SILLA-001)
• Nombre del artículo
• Cantidad
• Categoría
• Condición (nuevo/usado/bueno/regular/malo)
• Donador
• Fecha recibido (DD/MM/AAAA)
• Ubicación
• Notas adicionales
```

**Usuario:**
```
Código SILLA-025
Nombre Sillas de oficina ergonómicas
Cantidad 8
Categoría Mobiliario
Condición Bueno
Donador Empresa ABC
Fecha 14/01/2025
Ubicación Bodega B - Estante 5
Notas Dos tienen brazos ajustables
```

**Bot:**
```
✅ ¡Artículo registrado exitosamente en el inventario!

📦 Código: SILLA-025
📝 Nombre: Sillas de oficina ergonómicas
📋 Categoría: Mobiliario
📊 Cantidad: 8
🏷️ Condición: Bueno
📍 Ubicación: Bodega B - Estante 5
```

---

## 📋 Lista de Verificación Antes de Registrar

Antes de agregar cada artículo, verifica:

- [ ] El código es único (no existe ya)
- [ ] El código está en MAYÚSCULAS
- [ ] El nombre es descriptivo
- [ ] La cantidad es un número
- [ ] La categoría está en la lista aprobada
- [ ] La condición usa las opciones estándar
- [ ] La fecha usa formato DD/MM/AAAA
- [ ] La ubicación es específica
- [ ] Revisé la ortografía y tildes

---

## 🚫 Errores Comunes a Evitar

1. **Códigos duplicados** - Cada artículo debe tener un código único
2. **Inconsistencia en categorías** - Usa siempre el mismo nombre
3. **Fechas en formato incorrecto** - Siempre DD/MM/AAAA
4. **Faltas de ortografía** - Revisa antes de enviar
5. **Información vaga** - Ser específico ayuda después
6. **Mezclar mayúsculas/minúsculas** - Seguir las reglas del documento

---

## 💡 Consejos Finales

1. **Consistencia es clave** - Usa siempre el mismo formato
2. **Sé específico** - Más información es mejor que menos
3. **Revisa antes de enviar** - El bot no corrige errores
4. **Mantén un catálogo** - Ten a mano la lista de categorías y ubicaciones
5. **Actualiza regularmente** - Revisa el inventario periódicamente

---

## 📊 Datos de Ejemplo

### Opción 1: Descargar CSV
Puedes descargar el archivo CSV con ejemplos:
- [📥 Descargar datos-ejemplo.csv](../../ejemplos/datos-ejemplo.csv)

### Opción 2: Ver en Google Sheets (Solo lectura)
Para una mejor visualización interactiva:
- [📊 Ver ejemplos en Google Sheets](#) *(https://docs.google.com/spreadsheets/d/1Ixam3gdp1Vk6bJ26bK2ITr550PXL1J0FdPOL1LwkV9Y/edit?usp=sharing)*

⚠️ **Nota:** La hoja de Google Sheets es de solo lectura para referencia.

---

## 📞 Soporte y Recursos

**Hoja de ejemplos (solo visualización):**  
Puedes consultar en cualquier momento nuestra hoja con ejemplos de referencia.

⚠️ **No modifiques esta hoja** - es solo para consulta. Todos los artículos se agregan mediante el bot de Telegram.

Si tienes dudas sobre cómo registrar un artículo específico, consulta con el administrador del sistema.

---

**Última actualización:** Enero 2025