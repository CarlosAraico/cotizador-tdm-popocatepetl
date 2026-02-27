# 🌮 Cotizador de Eventos - Tacos Don Manolito Popocatepetl

**Sistema profesional de cotización en línea para catering y eventos**

---

## 📋 Resumen del Proyecto

**Cotizador TDM** es una aplicación web de una sola página (SPA) que permite a los clientes de Tacos Don Manolito Popocatepetl cotizar servicios de catering y eventos de forma rápida, intuitiva y profesional.

### ✨ Características Principales

- ✅ **Interfaz Responsiva**: Funciona perfectamente en desktop, tablet y móvil
- ✅ **Validaciones Inteligentes**: Validaciones en tempo real con feedback visual
- ✅ **Gestión de Clientes**: Selección rápida de clientes recurrentes
- ✅ **Catálogo Dinámico**: Productos personalizados por tipo de evento
- ✅ **Cálculos Automáticos**: Totales en tiempo real con precio por persona
- ✅ **Exportación PDF Premium**: Cotizaciones profesionales en PDF con formato TDM
- ✅ **Animaciones Suaves**: Transiciones y efectos visuales (AOS, Swiper)
- ✅ **Galería Interactiva**: Lightbox para visualizar trabajos anteriores
- ✅ **Newsletter**: Formulario de suscripción integrado

---

## 🏗️ Arquitectura Técnica

### **Stack Tecnológico**

| Componente | Tecnología | Versión |
|-----------|-----------|---------|
| **React** | UMD CDN | 18.x |
| **CSS Framework** | Bootstrap | 5.3.3 |
| **Babel** | Standalone | Última |
| **PDF Export** | jsPDF + AutoTable | 2.5.1 / 3.5.31 |
| **Animaciones** | AOS | 2.3.4 |
| **Carousel** | Swiper | 11.x |
| **Lightbox** | Magnific Popup | 1.1.0 |
| **Iconos** | Font Awesome | 6.5.0 |
| **Fuentes** | Google Fonts | Marcellus, Inter |

### **Estructura del Proyecto**

```
cotizador-tdm-popocatepetl/
├── index.html              # Archivo principal (SPA completo)
├── index.backup.html       # Respaldo (ignorado en git)
├── README.md              # Este archivo
└── .gitignore             # Archivo de exclusión git
```

---

## 🎨 Design Tokens (Color Palette)

```css
--tdm-primary: #864119   /* Marrón principal TDM */
--tdm-secondary: #9D5F32  /* Marrón secundario */
--tdm-accent: #DDB257     /* Dorado */
--tdm-background: #F1F0EE /* Fondo crema */
--tdm-surface: #FFFFFF    /* Blanco (superficies) */
--tdm-text: #151515       /* Gris oscuro (texto) */
--tdm-muted: #6B6B6B      /* Gris medio */
--tdm-border: #E6E0D8     /* Gris borde */
```

---

## 📱 Características por Sección

### **1. Navbar + Topbar**
- Navegación fija con logo TDM
- Contacto rápido (teléfono + email)
- Botón "Ir al cotizador"

### **2. Hero Section**
- Carrusel de imágenes (Swiper)
- Call-to-action principal
- Tarjetas de funcionalidades

### **3. Galería de Eventos**
- Grid responsiva de imágenes
- Lightbox interactivo (Magnific Popup)
- Lazy loading

### **4. Aplicación Cotizador (React)**

#### **Sección 1: Inicio**
- ¿Nuevo o cliente recurrente?
- Selección de tipo de evento (Catering/Evento)
- Carga automática de datos si es cliente registrado

#### **Sección 2: Datos del Evento**
- Cliente: nombre, teléfono, email, dirección
- Evento: fecha, número de personas (total/adultos/niños)
- Horarios: montaje, servicio, duración
- Google Maps link

#### **Sección 3: Productos**
- Selección dinámica por grupo (Tacos, Bebidas, Postres, etc.)
- Platillos filtrados por tipo de evento
- Agregar productos con cantidad
- Ordenamiento: A-Z, Z-A, Menor precio, Mayor precio
- Tabla con desglose de ítems

#### **Panel Resumen (Sticky)**
- Datos del cliente resumidos
- Total general y por persona
- Estado de validación
- Botón de exportación PDF

---

## 🔄 Flujo de Uso

```
1. Cliente ingresa: ¿Nuevo o recurrente?
   ├─ Si recurrente → Carga datos guardados
   └─ Si nuevo → Ingresa manualmente

2. Selecciona tipo: Catering o Evento
   → Filtra productos disponibles

3. Completa datos del evento
   → Validaciones en tiempo real
   → Warnings si no coincide tipo/personas

4. Agrega productos
   → Cantidad y precio calculados
   → Totales actualizados

5. Exportar PDF profesional
   → Con folio único
   → Términos y contacto
   → Múltiples páginas si es necesario
```

---

## 💾 Datos Establecidos

### **Clientes de Ejemplo**

```javascript
{ cliente: "Cliente Ejemplo 1", ... }
{ cliente: "Cliente Ejemplo 2", ... }
```

### **Catálogo de Productos**

| Tipo Evento | Grupo | Platillo | Precio |
|-----------|-------|----------|--------|
| Catering | Tacos | Pastor | $25 |
| Catering | Tacos | Suadero | $25 |
| Catering | Tacos | Bistec | $28 |
| Evento | Entradas | Guacamole | $150 |
| Evento | Platos Fuertes | Barbacoa | $200 |
| Evento/Catering | Bebidas | Agua Fresca | $40 |
| Evento/Catering | Postres | Pastel Tres Leches | $80 |
| ... | ... | ... | ... |

---

## 🚀 Instrucciones de Uso

### **Acceso**

Abre `index.html` en tu navegador:

```bash
# Opción 1: Archivo local
file:///ruta/a/cotizador-tdm-popocatepetl/index.html

# Opción 2: Servidor HTTP
python -m http.server 8000
# Luego: http://localhost:8000
```

### **Personalización**

1. **Editar contacto**: Busca `CONFIG.contact` en el script
2. **Cambiar paleta**: Modifica `:root` en `<style>`
3. **Agregar clientes**: Edita `DATA_CLIENTS`
4. **Agregar productos**: Edita `DATA_PRODUCTS`
5. **Cambiar logo**: Actualiza `CONFIG.logoUrl`

---

## ✅ Checklist de Validaciones

- [x] Cliente (nombre) - Requerido
- [x] Teléfono - Requerido
- [x] Email - Validación de formato
- [x] Dirección - Requerido
- [x] Google Maps URL - Validación de URL
- [x] Fecha de evento - Requerido
- [x] Número de personas - Requerido (>0)
- [x] Niños - Validación: no puede exceder total
- [x] Horarios - Requeridos
- [x] Duración - Cálculo automático de fin
- [x] Productos - Mínimo debe haber 1
- [x] Warnings: Catering (<40) vs Evento (≥40)

---

## 🐛 Mejoras Implementadas

### **v1.0 - Actual**
- ✅ Integración Crafto UI + React
- ✅ Validaciones robustas
- ✅ PDF con múltiples páginas
- ✅ Animaciones suaves
- ✅ Mobile-first responsive
- ✅ Accesibilidad mejorada
- ✅ Design tokens centralizados
- ✅ Comentarios en código

### **Próximas Mejoras**
- [ ] Backend para guardar cotizaciones
- [ ] Sistema de autenticación
- [ ] Historial de cotizaciones
- [ ] Integración Stripe/PayPal
- [ ] SMS de confirmación
- [ ] Email de cotización automático
- [ ] Análisis de ventas dashboard
- [ ] App móvil nativa

---

## 📞 Contacto

**Tacos Don Manolito Popocatepetl**

- 📱 Teléfono: 5645 960 445
- 📧 Email: popocatepetl@tacosdonmanolito.com
- 📍 Dirección: Av. Popocatépetl 415, CDMX

---

## 📄 Notas Técnicas

### **Performance**
- Carga: ~2-3 segundos (CDN)
- Renderizado: React optimizado con useMemo
- PDF: Generado en cliente (sin servidor)

### **Compatibilidad**
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile (iOS/Android)

### **Seguridad**
- ✅ Sin datos sensibles en cliente
- ✅ Validaciones en frontend y backend (si aplica)
- ✅ URLs sanitizadas

---

## 📦 Licencia

Proyecto privado para Tacos Don Manolito Popocatepetl © 2026

---

**Última actualización**: 27 de Febrero de 2026
