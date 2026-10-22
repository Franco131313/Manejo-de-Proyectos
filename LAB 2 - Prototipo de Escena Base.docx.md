# **SEMANA 4** 



## **LAB 2** : 

## Prototipo de Escena Base 

**Autor** : Joaquín Macías Cáceres (joaquin.macias@usach.cl) **Última actualización** : 15-10-2026 



### **Guía de laboratorio** 

- **Asignatura** : Ingeniería de Videojuegos: Fundamentos y Aplicaciones Interactivas 

- **Entrega** : Semana 5 <mark>(Vie 23-Oct 17:00 / Presentación: en clase Vie 23-Oct)</mark> 

- **Modalidad** : Grupal (equipos de 3 a 4 personas) 

- **Formato de entrega** : Documento PDF + Presentación (5-10 min.). 

- **Ponderación** : LAB 2 de 8 

### **Contexto** 

El LAB 2 es el primer hito de implementación del proyecto semestral. En esta etapa no se espera un juego funcional, sino una escena base operativa que demuestre que el equipo domina los fundamentos del motor elegido y comprende la arquitectura del game loop y el sistema de componentes. 

Es normal y esperado que la escena sea simple. El foco está en la solidez técnica de lo que se entrega, no en la cantidad de contenido. 

### **Requisitos mínimos** 

El prototipo debe cumplir con todos los siguientes requisitos: 

R1 - Escena funcional en motor: 

- El proyecto debe abrirse y ejecutarse sin errores en el motor elegido (Unity, Godot u otro acordado con el docente). 

- Debe existir al menos una escena con nombre representativo del proyecto. 

### R2 - Objetos y jerarquía: 

- La escena debe contener al menos 4 objetos de juego con roles diferenciados: 

   - Un objeto que represente al personaje o elemento principal. 

   - Un objeto de cámara configurado correctamente. 

   - Al menos dos elementos del entorno (plataforma, suelo, obstáculo, pared, etc.). 

- Los objetos deben estar organizados en una jerarquía lógica (no todos al mismo nivel raíz). 

### R3 - Movimiento básico con delta time: 

- El personaje principal debe moverse en respuesta a input del teclado o gamepad. 

- El movimiento debe implementarse correctamente usando delta time para ser independiente del framerate. 

- El código debe estar comentado explicando el uso de delta time. 

### R4 - Al menos dos componentes personalizados: 

- Deben existir al menos dos scripts propios (no solo componentes del motor): 

   - Uno para el movimiento del personaje. 



- Uno para cualquier otro comportamiento (cámara, objeto interactuable, etc.). 

R5 - Cámara funcional: 

- La cámara debe seguir al personaje o estar correctamente posicionada para mostrar la acción. 

- Si el juego es 3D, la cámara debe tener la perspectiva configurada correctamente. 

- Si el juego es 2D, la cámara debe estar en proyección ortográfica. 

### **Requisitos de documentación** 

### **Documento de reflexión técnica (PDF, máx. 5 páginas)** 

El documento debe responder las siguientes preguntas de forma concisa: 

1. ¿Qué motor y versión están usando?, ¿hubo cambios respecto a lo declarado en el LAB 1? ¿por qué?. 

2. ¿Cómo estructuraron la jerarquía de objetos?, incluir una captura del panel de jerarquía del editor con una breve justificación. 

3. ¿Cómo implementaron el movimiento con delta time?, incluir el fragmento de código relevante y explicar por qué es necesario usarlo. 

4. ¿Qué decisiones técnicas tomaron que no eran obvias? (al menos una decisión de diseño técnico y su justificación). 

5. ¿Qué desafíos encontraron y cómo los resolvieron?. 

### **Video de demostración (máx. 3 min) + Presentación (de 5-10 min)** 

- Mostrar la escena en ejecución. 

- Demostrar el movimiento del personaje con input. 

- Recorrer brevemente la jerarquía en el editor. 

- No es necesaria edición: puede ser una grabación de pantalla simple. 

### **Criterios de evaluación** 

|**Criterio**|**Descripción**|**Ponderación**|
|---|---|---|
|Escena funcional|El proyecto abre y corre sin errores.|15%|
|Jerarquía y organización|Objetos bien organizados y con nombres<br>descriptivos.|15%|
|Movimiento con delta time|Implementación correcta y comentada.|25%|
|Componentes<br>personalizados|Scripts propios coherentes con la propuesta<br>del proyecto.|20%|





|Cámara funcional|Configuración adecuada al tipo de juego.|10%|
|---|---|---|
|Documento de reflexión|Respuestas claras, código incluido, reflexión<br>genuina.|15%|
|Total||100%|



### **Notas importantes** 

- El repositorio debe tener un archivo README.md con: nombre del equipo, nombre del proyecto, motor utilizado e instrucciones para abrir el proyecto. 

- Si el motor requiere ignorar carpetas pesadas (como Library/ en Unity), el repositorio debe incluir un .gitignore apropiado. 

- No se evaluará la calidad visual (texturas, modelos, colores). Solo la correctitud técnica de lo implementado. 

- Los equipos que en el LAB 1 recibieron sugerencias de ajuste por parte del profesor, deben reflejar esos ajustes en la escena entregada. 

### **Material disponible** 

### ● **Unity** : 

- Unity Learn<sup>1</sup> ofrece tutoriales, cursos y rutas de aprendizaje guiadas de forma gratuita para dominar el desarrollo 3D en tiempo real, incluyendo videojuegos, VR y AR. 

- Rutas de aprendizaje: 

   - Unity Essentials<sup>2</sup> (para quienes son completamente nuevos). 

   - Junior Programmer<sup>3</sup> (orientada a empezar a programar desde cero hasta nivel empleable). 

   - Creative Core<sup>4</sup> (aspectos creativos del motor). 

   - VR Development<sup>5</sup> y AR Development<sup>6</sup> . 

- Cursos destacados: 

   - Juego 2D para principiantes<sup>7</sup> . 

   - Real-Time Animated Storytelling para crear animaciones 3D<sup>8</sup> . 

> 1 learn.unity.com 

- 2 https://learn.unity.com/pathway/unity-essentials 

- 3 https://learn.unity.com/pathway/junior-programmer 

4 

https://learn.unity.com/pathway/creative-core/unit/introduction-to-creative-core/tutorial/welcome-to-thecreative-core-pathway 

- 5 https://learn.unity.com/pathway/vr-development 

- 6 https://learn.unity.com/pathway/mobile-ar-development 

- 7 https://learn.unity.com/course/2d-beginner-adventure-game 

- 8 https://learn.unity.com/course/real-time-animated-storytelling 



         - Certificación Unity Certified Associate<sup>9</sup> : Game Developer, que cubre programación en C#, efectos visuales, audio, interfaces de usuario y animación. 

      - Documentación técnica: 

         - Unity Manual<sup>10</sup> , documentación completa del editor. 

         - Scripting API<sup>11</sup> , referencias de la API de C#. 

         - Unity Blog<sup>12</sup> , artículos técnicos y noticias del motor. 

      - Asset Store<sup>13</sup> , más de 9000 recursos gratuitos para proyectos. 

   - **Unreal Engine** : 

      - Learn Unreal Engine<sup>14</sup> 

      - Documentación<sup>15</sup> 

      - Epic Dev Community<sup>16</sup> 

      - Unreal Online Learning<sup>17</sup> 

      - Proyectos de muestra descargables: 

         - Stack O' Bot<sup>18</sup> (punto de partida para principiantes avanzados). 

         - Content Examples<sup>19</sup> (diversas técnicas para construir juegos). 

         - Lyra Sample Game<sup>20</sup> (punto de partida ideal para desarrollo de juegos con UE). 

         - Cropout<sup>21</sup> (ejemplo de buenas prácticas para títulos multiplataforma). 

   - **Godot Engine** : 

      - Documentación oficial<sup>22</sup> . 

      - Tu primer juego<sup>23</sup> . 

      - Recurso comunitario destacado GDQuest<sup>24</sup> . 

      - Asset Library, desde el editor o desde la web<sup>25</sup> . 

   - **GameMaker** : 

      - Documentación<sup>26</sup> . 

         - Tu primer juego según: 

- 9 https://unity.com/es/products/unity-certifications 

- 10 https://docs.unity3d.com/Manual/ 

11 https://docs.unity3d.com/ScriptReference/ 

- 12 https://unity.com/blog 

13 https://assetstore.unity.com/search#q=free&nf-ec_price_filter=0...0 

- 14 https://dev.epicgames.com/community/unreal-engine/learning 

- 15 https://dev.epicgames.com/documentation/ 

- 16 https://dev.epicgames.com/ 

17 https://dev.epicgames.com/community/unreal-engine/learning 18 

https://www.unrealengine.com/en-US/news/updated-stack-o-bot-for-unreal-engine-5-6-available-now 

19 

https://dev.epicgames.com/documentation/en-us/unreal-engine/content-examples-sample-project-forunreal-engine 

20 https://dev.epicgames.com/documentation/en-us/unreal-engine/lyra-sample-game-in-unreal-engine 21 https://www.unrealengine.com/en-US/blog/cropout-casual-rts-game-sample-project 22 https://docs.godotengine.org/en/stable/ 

23 https://docs.godotengine.org/en/3.0/getting_started/step_by_step/your_first_game.html 

- 24 https://www.gdquest.com/tutorial/#gamedev 

25 https://godotengine.org/asset-library/asset 

26 https://gamemaker.io/en/tutorials/get-started-gamemaker-2026 



   - Arcade Game<sup>27</sup> . 

   - Platformer<sup>28</sup> . 

   - Role-Playing Game<sup>29</sup> . 

   - How to Make a Mobile Game<sup>30</sup> . 

   - The Important of Source Control<sup>31</sup> . 

- Manual oficial<sup>32</sup> . 

> 27 https://www.youtube.com/playlist?list=PLhIbBGhnxj5JeenLZYjjG-IltQyUE7QW_ 28 https://www.youtube.com/watch?v=a9f4QdHGM4k&t=34s 

> 29 https://youtu.be/1J5EydrnIPs 

> 30 https://www.youtube.com/watch?v=2DzcRUP9dLg 

> 31 https://www.youtube.com/watch?v=qjy7x-QGVLA 

> 32 https://manual.gamemaker.io/monthly/en/#t=Content.htm 

