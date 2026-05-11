# 🃏 Planning Poker

**Planning Poker en línea para estimación ágil — Sin anclar votos, sin distorsiones.**

Una herramienta web moderna para que equipos de desarrollo estimen historias de forma colaborativa y transparente. Basada en la metodología Agile/Scrum, permite que los miembros del equipo voten sin conocer las estimaciones de los demás hasta que se revelen.

---

## 🌟 Características

✅ **Salas en tiempo real** — Múltiples personas pueden conectarse a la misma sesión simultáneamente  
✅ **Votos anónimos** — Nadie ve los votos hasta que el moderador pulsa "Revelar"  
✅ **Historial de rondas** — Panel lateral con todas las estimaciones previas  
✅ **Cartas animadas** — Animación flip 3D al revelar votos  
✅ **Compartir por enlace** — Solo necesitas un link para invitar  
✅ **Responsive** — Funciona perfectamente en móvil, tablet y desktop  
✅ **Cero instalación** — Todo ocurre en el navegador, sin login  
✅ **Identidad visual Planasa** — Diseño limpio con colores corporativos  

---

## 🚀 Cómo usar

### Crear una sala
1. Escribe el **nombre de la sala** (Ej: "Sprint Planning")
2. Clic **"Crear sala"**
3. Se genera un enlace automáticamente
4. Copia el enlace y comparte con tu equipo
5. Todos entran por el mismo enlace y ponen su nombre

### Participar en la estimación
1. Cada persona **elige su carta** (1, 2, 3, 5, 8, 13, 21, 40, ?, ☕)
2. Los votos permanecen ocultos mientras votan
3. Cuando todos han votado → **"Revelar votos"**
4. Se muestran las estimaciones y se calcula la media/mín/máx
5. **"Nueva ronda"** para la siguiente historia

---

## 🛠️ Stack Tecnológico

- **Frontend:** HTML5, CSS3, JavaScript vanilla (sin dependencias)
- **Real-time:** Firebase Realtime Database
- **Hosting:** GitHub Pages
- **Animaciones:** CSS 3D Transforms
- **Responsive:** Media queries CSS

---

## 📦 Instalación

### En GitHub Pages

La app ya está lista en:
```
https://TU_USUARIO.github.io/planning-poker/
```

### Clonar y ejecutar localmente

```bash
# Clonar el repositorio
git clone https://github.com/TU_USUARIO/planning-poker.git
cd planning-poker

# Abrir en navegador
# Opción 1: Abre index.html directamente en el navegador
open index.html

# Opción 2: Sirve con un servidor local (Python)
python -m http.server 8000
# Luego visita http://localhost:8000
```

---

## 🔧 Configuración Firebase (Importante)

Para que funcione el sincronismo en tiempo real, necesitas:

1. **Crear un proyecto en Firebase** (gratuito)
   - Ve a [firebase.google.com](https://firebase.google.com)
   - Crea un nuevo proyecto
   - Habilita **Realtime Database** en modo de prueba

2. **Configurar las reglas de seguridad**
   - Ve a Realtime Database → Reglas
   - Reemplaza con esto:
   ```json
   {
     "rules": {
       "sessions": {
         "$sessionId": {
           ".read": true,
           ".write": true
         }
       }
     }
   }
   ```
   - Clic "Publicar"

3. **Actualizar la configuración en index.html**
   - Abre `index.html`
   - Busca `const firebaseConfig = {`
   - Reemplaza con tus credenciales de Firebase

---

## 📊 Cartas disponibles

- **Números:** 1, 2, 3, 5, 8, 13, 21, 40 (Fibonacci)
- **Especiales:**
  - **?** — Inseguridad, necesita aclaración
  - **☕** — Pausa, necesitamos café

---

## 🎨 Identidad Visual

Diseño basado en la identidad corporativa **Planasa**:
- Color primario: Verde `#3F9C35` (Pantone 362)
- Tema claro profesional
- Tipografía sans-serif moderna
- Interfaz intuitiva y limpia

---

## 💾 Almacenamiento

- **Sesiones:** Se guardan en Firebase Realtime Database
- **Historial:** Se mantiene en memoria durante la sesión
- **Auto-cleanup:** Las sesiones se limpian automáticamente cuando el último participante se desconecta

---

## 📱 Responsive Design

| Dispositivo | Ancho | Comportamiento |
|---|---|---|
| **Móvil** | < 500px | Historial oculto, cartas compactas |
| **Tablet** | 500-1024px | Historial visible, interfaz adaptada |
| **Desktop** | > 1024px | Diseño completo con sidebar |

---

## 🔒 Privacidad y Seguridad

- ✅ No requiere login ni registro
- ✅ Solo quién tenga el enlace puede acceder
- ✅ Los datos se guardan en Firebase (cumple GDPR)
- ✅ Las sesiones se borran automáticamente tras inactividad
- ✅ Sin cookies, sin tracking

---

## 📖 Cómo funciona la estimación

**Planning Poker** es una técnica de estimación basada en consenso:

1. Se presenta una historia de usuario
2. Cada miembro estima en secreto
3. Se revelan los votos
4. Si hay diferencias grandes, se discute
5. Se re-estima si es necesario

**Beneficios:**
- Evita el "anclaje" (primer voto influencia los demás)
- Todos participan equitativamente
- Discusión fundamentada en estimaciones
- Más precisión en el consenso

---

## 🐛 Troubleshooting

### La app no sincroniza
- Verifica que Firebase esté configurado correctamente
- Comprueba que tienes internet
- Abre la consola (F12) para ver errores

### El enlace no funciona
- Asegúrate de copiar el enlace completo
- Intenta desde otra pestaña/navegador
- Recarga la página

### Los votos no aparecen
- Verifica que todos están en la misma sala
- Intenta refrescar la página
- Comprueba que la sala no ha sido borrada (30+ min inactiva)

---

## 📚 Recursos

- [Planning Poker en Wikipedia](https://en.wikipedia.org/wiki/Planning_poker)
- [Agile Estimation Techniques](https://www.mountaingoatsoftware.com/blog/planning-poker)
- [Firebase Documentation](https://firebase.google.com/docs)

---

## 📄 Licencia

MIT License — Libre para usar, modificar y distribuir.

---

## 👨‍💻 Autor

Creado con ❤️ por **Javier Sánchez Tirados**  
Para equipos que estiman mejor.

---

**¿Necesitas ayuda?** Abre un issue en el repositorio o contacta al equipo.
