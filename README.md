Perfecto, aquí tienes un **taller avanzado** para tus alumnos que pondrá a prueba sus habilidades con **CSS Grid**, **Flexbox** y **pseudoclases**. La idea es que **replican una interfaz responsiva** tipo *dashboard* con un menú lateral, una cabecera, tarjetas de contenido, y un sistema de "hover/focus interacciones".

---

### 💡 Taller: Clon de Panel Administrativo Interactivo

**Objetivo:** replicar una maqueta con:

* Grid layout para el esqueleto principal
* Flexbox para distribuir elementos dentro de componentes
* Uso de pseudoclases como `:hover`, `:focus`, `:nth-child`, `:not`, etc.
* Responsivo: que se adapte a diferentes anchos

---

## 🧩 Código que deben replicar (HTML + CSS)

### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Admin Dashboard Clone</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="layout">
    <aside class="sidebar">
      <h2>Admin</h2>
      <nav>
        <a href="#" class="active">Inicio</a>
        <a href="#">Usuarios</a>
        <a href="#">Reportes</a>
        <a href="#">Configuración</a>
      </nav>
    </aside>

    <header class="header">
      <input type="text" placeholder="Buscar..." />
      <button>🔔</button>
    </header>

    <main class="main-content">
      <section class="card">Resumen 1</section>
      <section class="card">Resumen 2</section>
      <section class="card">Resumen 3</section>
      <section class="card highlight">Resumen 4</section>
    </main>
  </div>
</body>
</html>
```

---

### `styles.css`

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: sans-serif;
}

body {
  height: 100vh;
  display: grid;
  place-items: center;
  background: #f5f5f5;
}

.layout {
  display: grid;
  grid-template-columns: 240px 1fr;
  grid-template-rows: 60px 1fr;
  grid-template-areas:
    "sidebar header"
    "sidebar main";
  height: 90vh;
  width: 90vw;
  background: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.sidebar {
  grid-area: sidebar;
  background: #2f3e46;
  color: white;
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.sidebar h2 {
  font-size: 1.5em;
}

.sidebar nav {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.sidebar a {
  color: #cbd5e1;
  text-decoration: none;
  padding: 8px 12px;
  border-radius: 6px;
  transition: background 0.2s;
}

.sidebar a:hover,
.sidebar a:focus {
  background: #4e5d64;
  outline: none;
}

.sidebar a.active {
  background: #64748b;
  color: white;
}

.header {
  grid-area: header;
  background: #f1f5f9;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}

.header input {
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 6px;
}

.header input:focus {
  border-color: #3b82f6;
  outline: none;
}

.header button {
  background: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
}

.main-content {
  grid-area: main;
  padding: 20px;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
  gap: 20px;
}

.card {
  background: #e2e8f0;
  padding: 20px;
  border-radius: 8px;
  transition: transform 0.3s, background 0.3s;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card:hover {
  background: #cbd5e1;
  transform: translateY(-4px);
}

.card:nth-child(odd) {
  background: #dbeafe;
}

.card.highlight {
  border: 2px dashed #3b82f6;
  background: #bfdbfe;
}
```

---

### 📌 Instrucciones para los alumnos

1. Replica el código anterior **desde cero** (no solo copiar y pegar).
2. Cambia colores o textos si quieres, pero **mantén estructura, diseño y comportamiento.**
3. Asegúrate de que el diseño sea responsivo (deben notarlo al achicar el navegador).
4. Deben **identificar y explicar**:

   * ¿Qué parte usa Grid?
   * ¿Qué parte usa Flex?
   * ¿Dónde se aplican pseudoclases? (mínimo `:hover`, `:focus`, `:nth-child`, `:not()`)

---

¿Quieres que prepare una versión *starter* (base vacía) para que solo vean la referencia final?
