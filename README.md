# Sancta Lumina: Ecosistema Transmedia de Arte Sacro ⛪✨

> **Proyecto Museográfico · Santa Fe de Antioquia · Colombia · 2025**  
> *Arte sacro en diálogo con la era digital.*

**Sancta Lumina** es un macroproyecto tecnológico y museográfico desarrollado para el **Museo de Arte Religioso Monseñor Francisco Cristóbal Toro**. Nace con el propósito de transformar la contemplación pasiva del acervo cultural y religioso en un descubrimiento activo, accesible y participativo, sin perder la dignidad y solemnidad de su legado.

Aunque este repositorio aloja específicamente el código y los **prototipos en Realidad Virtual (Unity)** de la Sala 360°, es fundamental comprender el ecosistema íntegro compuesto por tres productos complementarios que conforman un relato transmedia unificado.

---

## 🌍 1. El Desafío: Patrimonio Vivo, No Estático

Santa Fe de Antioquia, siendo un municipio emblemático y patrimonial, custodia siglos de devoción. Sus instituciones culturales enfrentaban un reto estructural:
* **Accesibilidad:** Información profunda y extensa, pero inaccesible o densa para públicos no especializados.
* **Participación:** Recorridos unidireccionales (el museo transmite, el visitante recibe) sin dinámicas de interacción activa.
* **Relevancia:** Los formatos tradicionales generaban distancia con jóvenes y turistas internacionales. Se necesitaban nuevos lenguajes.

---

## 🌌 2. Los Productos: Un Ecosistema de Experiencias

El macroproyecto logró ramificarse en tres formatos adaptados a sus audiencias, documentados a continuación:

### Ⅰ. Videomapping Arquitectónico (Fachadas que cobran vida)
Las 3 iglesias principales de Santa Fe de Antioquia abandonaron lo estático y se convirtieron en lienzos lumínicos. Todo con profundo respeto arquitectónico, usando los arcos y campanarios no como obstáculos, sino como recursos narrativos.
* **Prototipado en VR (Presente en el Repo):** Gran parte de la innovación de este ecosistema recae en la creación de Modelos 3D de las iglesias mediante *Fotogrametría a escala 1:1*. A través de Gafas VR (Meta Quest 3), se lograron revisar flujos y animaciones digitalmente ahorrando ciclos de corrección en terreno físico.
* **Tecnologías:** TouchDesigner, After Effects, Meta Quest 3, Fotogrametría, Resolume, Spatial Audio.

### Ⅱ. Guía Turística Inteligente (El museo que conversa)
Se desplegó una **Progressive Web App (PWA)** a la que los visitantes pueden acceder escaneando un QR offline/online, sin necesidad de instalación de apps propietarias, entablando diálogos fluidos sobre las obras.
* **Arquitectura RAG (Retrieval-Augmented Generation):** Esta IA está protegida de las alucinaciones comerciales, fue implementada conectando una base de datos vectorial impulsada por *Embeddings semánticos* obtenidos exclusivamente de la curaduría oficial del museo. Dependiendo de si se le habla de forma casual o académica, proporciona contexto y respuestas fidedignas (ej. épocas, técnicas como *sfumato* y contextos de donación siglo XVII).
* **Tecnologías:** RAG Pipeline, Vector DB, LLM API, Node.js, Web PWA, Embeddings Semánticos.

### Ⅲ. Sala 360° Inmersiva (La sala que se transforma)
Ubicada en el interior del museo, se reestructuró la sala temporal de la Madre Laura Montoya, reemplazando láminas de texto físicas por *Videomapping 360°* en las paredes interactuando en simultáneo con una experiencia de Realidad Virtual.
* **Diseño e Integración (Foco Central del Repo):** Este repositorio guarda la programación C# (`ControladorNarrativa.cs`, `EventoVisual.cs`) sobre Unity que divide la animación narrativa de la santa antioqueña en etapas interactuables apoyándose en Spatial Audio. Adicionalmente, el espacio se pensó de forma modular, permitiendo al museo reemplazar los contenidos en próximas exposiciones rotativas ("la inversión tecnológica más duradera").
* **Tecnologías:** Unity, Meta Quest 3, Meta XR SDK / Oculus, TouchDesigner, 3D Animation.

---

## 📈 3. El Impacto de Sancta Lumina

- **Educativo y Patrimonial:** Acercó narrativas monótonas al siglo XXI. Se comprobó que el avance tecnológico es aliado del pasado amplificando el respeto, no trivializándolo.
- **Cultural y Turístico:** Amplificó el perfil de visitante para la región con inmersión digital, impulsando a las comunidades a reconectar con espacios litúrgicos a veces olvidados.
- **Institucional (Autonomía):** El museo quedó con infraestructura permanente diseñada para mutar dinámicamente con las futuras exposiciones de temporada.

---

## 👨‍💻 4. Producción y Dirección Transversal

Bajo el marco de un desarrollo de 6 meses de duración (Ene - Jun 2025), la coordinación como **Technology Lead & Director** requirió de la orquestación de un equipo pluridisciplinar superior a **20 personas** (animadores, dev, constructores) logrando de base tres metas de alto calibre: el ruteo base de datos RAG, despliegue de experiencias VR y el videomapping interactivo.

---

## 🎨 5. Identidad Visual

Para la coherencia estética en interfaces y publicidad:
* **Colores Principales:**  
  ⬛ Azul Obsidiana (`#16191F`) | 🟨 Oro Litúrgico (`#9E7E44`) | ⬜ Marfil Claro (`#E7DBC2`)  
* **Colores Secundarios:**  
  🟥 Rojo Terracota (`#783018`) | 🟦 Celeste Vela (`#89A1AD`) | 🟩 Verde Cirprés (`#556342`) | 🟪 Púrpura Envejecido (`#584260`)
* **Tipografías:** `Playfair Display` (Títulos Bold en banners) y la familia `Saira` (Para interfaces digitales).

---

## 📁 6. Análisis y Estructura del Repositorio (Prototipo VR)

Este repositorio contiene el proyecto de Unity ubicado en el directorio principal `/VideoMapping/`. Su propósito técnico es servir como entorno interactivo de la **Sala 360°** y funcionar como sandbox de simulación VR para las fachadas estructurales a escala 1:1.

### Lógica Base y C# Scripts (`Assets/`)
La magia narrativa se apoya en controladores diseñados a medida, logrando una sincronización completa entre audio, inputs y visuales inmersivas:

*   **`ControladorNarrativa.cs`:** Actúa como el cerebro o director de la simulación. Se encarga de gestionar la máquina de estados de la experiencia (capítulos: infancia, vocación, misión y legado de la Madre Laura), coordinando los tiempos para despachar animaciones visuales y guías auditivas.
*   **`EventoVisual.cs`:** Este componente interactúa de cerca con la narrativa, gestionando las proyecciones o "videomapping virtual" dentro del motor. Activa transiciones de texturas, shaders y partículas (almacenadas en `Assets/Particles/` y `Assets/Materials/`).
*   **`SecuenciaPisadas.cs`:** Se encarga de agregar inmersión en la presencia espacial. Administra el feedback de proximidad y posición, permitiendo interacción ambiental a medida que el usuario se mueve por la sala física/digital.
*   **`InputSystem_Actions.inputactions`:** Implementación del *Input System* moderno de Unity adaptado a la Realidad Virtual. Mapea la entrada de las manos, gatillos y orientación de los cascos **Meta Quest 3** con gran precisión.
*   **Audio Espacial (`Laura.wav`):** A través del SDK de Audio, las piezas de voz y soundscapes reaccionan volumétricamente en la posición del Headset.

### Arquitectura de SDKs (VR Pipeline)
El entorno delega gran parte del procesamiento XR al hardware mediante la instalación preconfigurada de repositorios Meta XR y módulos gráficos de alto rendimiento:
* **`Assets/MetaXR/`, `Assets/Oculus/`, y `Assets/XR/`:** Contienen las integraciones subyacentes fundamentales para soporte *Passthrough*, 6DOF (6 grados de libertad) para cabeza/manos, y optimización estereoscópica.
* **Formatos HDRP/URP:** Se implementaron gestiones avanzadas de rendering para emular los cruces lumínicos de un videomapping real manteniendo altas de tasa de refresco necesarias en VR.

### Guía para Ejecutar el Proyecto
Para abrir y colaborar en este prototipo, se recomiendan los siguientes lineamientos:
1. **Engine:** Unity Version (Preferiblemente Serie 2022 LTS o superior).
2. **Build Target:** El proyecto está programado para correr sobre arquitectura Android (necesario para compilación `.apk` hacia Meta Quest 3). Requieres instalar el *Android Build Support* en Unity Hub.
3. **XR Plugin Management:** Asegurarse de que el proveedor "Oculus" sigue habilitado en los `ProjectSettings`.
4. **Inicio Rápido:** Cargar el proyecto añadiendo la carpeta raíz externa `VideoMapping/`. Ejecutar la escena maestra desde el directorio `Assets/Scenes/`.

---
> *"La tecnología y el patrimonio no son opuestos — son aliados.*  
> *El pasado se vuelve más presente cuando encontramos nuevas formas de habitarlo."*
