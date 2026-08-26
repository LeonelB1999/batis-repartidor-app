# 🐟 Cevichería Batis — App del Sistema de Negocios

**La cevichería de Leonel, ahora en tu bolsillo.** 📱

Esta app es la versión Android del sistema **Mis Negocios**: el punto de venta (POS) y el panel de administración (Dashboard) de la Cevichería Batis, listos para usar desde el celular o la tablet en cualquier lugar.

---

## ✨ ¿Cómo funciona?

La app es una **ventana directa a tu sistema en vivo**: al abrirla, carga el POS desde tu servidor y **siempre muestra la versión más reciente** — cualquier actualización que se haga en el sistema (nuevos productos, reportes, correcciones) llega sola a la app. No necesitas instalar nada nuevo.

> 🔗 Página del sistema: **http://129.159.90.187**
> 🧪 Versión de pruebas (QA): **http://129.159.90.187:8080**

---

## 🛒 POS — Punto de Venta (para el mostrador)

El POS es la pantalla principal para atender clientes:

- **Ventas rápidas** — busca productos, arma combos y cobra en segundos
- **💳 Múltiples métodos de pago** — efectivo, Yappy, tarjeta (Visa/MasterCard), clave y transferencia, todo en una sola venta
- **🎟️ Tickets (cuentas de clientes)** — abre una cuenta, agrega productos durante el día y cobra cuando el cliente pague (mismo día o después)
- **🔀 Combos** — prepara combos con ingredientes personalizados (ej: Ceviche Especial)
- **👨‍🍳 Turnos de trabajo** — abre/cierra turno por empleado, con cuadre de caja **exacto por método de pago**: la app compara lo que se vendió vs. lo que hay en caja y muestra **dónde está cada diferencia**
- **📉 Control de stock** — descuenta inventario automáticamente al vender y avisa cuando algo se agota
- **📲 WhatsApp integrado** — recibe el resumen del turno (ventas, métodos, cuadre) directo al WhatsApp del dueño

## 📊 Dashboard — Panel de Administración (para el dueño y socios)

Todo el control de negocio en un solo lugar:

- **🏠 Inicio** — estadísticas del día: ventas, tickets pendientes, productos, ganancias
- **💰 Caja** — historial de turnos con ventas por método, tickets abiertos pendientes y detalle completo de cada cierre
- **📈 Reportes** — ventas por día, por artículo, por categoría, por empleado y por método de pago, con filtros de fecha
- **🔮 Proyecciones** — pronóstico de ventas de la próxima semana basado en tu historial real
- **📦 Inventario** — productos, categorías, proveedores, **órdenes de compra**, ajustes de stock y valoración del inventario
- **💸 Gastos y Compras** — registra gastos del negocio y órdenes de compra a proveedores
- **⚖️ Balance** — ganancia real (ventas − gastos), desgloses por método, flujo de dinero y **exportar a PDF**
- **👥 Usuarios y roles** — dueño (todo), socio (gestión de su tienda) y empleado (limitado al POS)
- **🏪 Multi-tienda** — Cevichería 🐟 y Perfumería 🧴 en el mismo sistema

---

## 📥 Instalar la app

1. **Descarga el APK** desde GitHub Actions → Artifacts → `CevicheriaBatis-APK`
   - O desde la sección **Releases** del repositorio (cuando se publique una versión)
2. Ábrelo en tu celular Android y acepta "Instalar aplicaciones desconocidas" (es normal, la app no está en Play Store)
3. Abre **Cevichería Batis** e inicia sesión con tu usuario y contraseña del sistema
4. ¡Listo! 🎉 El POS carga al instante con tus productos reales

> ⚠️ **Importante:** la app necesita conexión a internet para funcionar (carga el sistema desde tu servidor). Mientras el celular y el servidor estén en línea, todo funciona normal.

---

## 🛠️ Para desarrolladores

**Stack:** [Capacitor](https://capacitorjs.com) + Android nativo — la app es un WebView que apunta a `http://129.159.90.187/pos.html`.

```bash
npm install          # instala dependencias
npx cap sync android # sincroniza el proyecto Android
cd android && ./gradlew assembleRelease  # compila el APK
```

El APK se compila automáticamente con **GitHub Actions** cada vez que se sube código a `main` (o manualmente desde Actions → Build APK → Run workflow).

**Estructura:**
- `dist/index.html` — pantalla de carga que redirige al POS
- `android/` — proyecto Android generado por Capacitor
- `.github/workflows/build-apk.yml` — compilación automática del APK

---

## 📦 Releases

| Versión | Fecha | Contenido |
|---|---|---|
| **1.1** | Ago 2026 | Compilación release optimizada + README |
| **1.0** | Jul 2026 | Primera versión: app POS directo al servidor |

---

Hecho con 💚 para la Cevichería Batis — sistema **Mis Negocios** de Leonel Batista.
