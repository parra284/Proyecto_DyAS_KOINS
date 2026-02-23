# Proyecto de Diseño de Software – Corte Uno

## Presentación del Problema

KOINS es una aplicación diseñada para centralizar la gestión de **facturas electrónicas y manuales**, organizar finanzas personales y ofrecer asesoría mediante **inteligencia artificial**.  

El problema principal que aborda es la falta de control financiero y la pérdida de facturas que afecta a muchos usuarios, generando desorden, estrés económico y dificultades para llevar un registro mensual adecuado.  

**Usuarios beneficiados:**  
- Estudiantes  
- Jóvenes profesionales  
- Emprendedores  
- Personas interesadas en mejorar su **gestión financiera personal**

---

## Creatividad en la Presentación

Enlace al recurso creativo que explica el problema:  
- [Video/animación](https://drive.google.com/file/d/1hCow4LncccwsIB-q21858jmLDCwcpJlI/view?usp=sharing)

---

## Fundamentos de Ingeniería de Software

Los atributos de calidad priorizados en KOINS son:

- **Usabilidad:** Interfaz intuitiva, flujos simples y navegación clara.  
- **Mantenibilidad:** Código modular y uso de **interfaces y patrones de diseño**.  
- **Escalabilidad:** Backend desacoplado y arquitectura preparada para crecer con nuevos módulos.
---

## Diseño de Software

### Principios SOLID aplicados

1. **SRP (Single Responsibility Principle):** Cada clase tiene una única responsabilidad.  
   **Ejemplo:** `FacturaBuilder` solo se encarga de construir objetos `Factura`, mientras que `FacturaContext` se encarga de aplicar estrategias de parsing y categorización.

2. **OCP (Open/Closed Principle):** El sistema es extensible sin modificar el código base.  
   **Ejemplo:** Nuevos tipos de `ParserStrategy` o `CategoriaStrategy` pueden agregarse sin alterar las clases existentes.

3. **DIP (Dependency Inversion Principle):** Los módulos dependen de **interfaces** en lugar de implementaciones concretas.  
   **Ejemplo:** `RecommendationUseCase` depende de `ITransactionsRepository` e `AIService`, no de sus implementaciones concretas (`TransactionsRepository` o `SimpleAIService`).

---

### Patrones de diseño utilizados

1. **Strategy:** Permite definir una familia de algoritmos intercambiables.  
   **Ejemplo:** `ManualParserStrategy` y `ImagenParserStrategy` implementan `ParserStrategy`, seleccionadas dinámicamente mediante `ParserStrategySelector`.

2. **Observer:** Permite notificaciones automáticas tras registrar facturas o ingresos.  
   **Suscriptores:** `Dashboard`, `StatsService` reciben actualizaciones desde `SubjectNotifier`.

3. **Builder:** Facilita la construcción de objetos complejos de forma controlada.  
   **Ejemplo:** `FacturaBuilder` permite crear facturas paso a paso, agregando atributos opcionales según el origen de los datos.

4. **Repository:** Encapsula la persistencia de entidades.  
   **Ejemplo:** `FacturaRepository` y `IngresoRepository` implementan la interfaz `Repository` para manejo de datos.

**Justificación:**  
Estos patrones facilitan el desacoplamiento entre la lógica de negocio y su uso, manteniendo una arquitectura modular y flexible, lo que permite extender y mantener el sistema de manera sencilla.

---

### Diagramas UML

[Diagramas UML - Google Drive](https://drive.google.com/drive/folders/1VjrKOqD-fDst-tjtKH1ZarCc2-aHZkT-?usp=sharing)

---

## Implementación

- **Flujos clave:**  
  1. Registro de facturas e ingresos → notificación a observadores → actualización de dashboard/estadísticas.  
  2. Generación de recomendaciones → consulta de datos → procesamiento por AI → entrega al usuario.  
  3. Parsing y categorización de facturas mediante estrategias seleccionadas dinámicamente.

## Análisis Técnico

KOINS mantiene:

- **Cohesión:** Cada módulo tiene una función específica, evitando responsabilidades mezcladas.  
- **Bajo acoplamiento:** Comunicación entre módulos mediante interfaces, facilitando cambios y extensiones.  
- **Cumplimiento de atributos de calidad:** Se garantiza usabilidad, seguridad, mantenibilidad, escalabilidad y rendimiento mediante la arquitectura modular y patrones de diseño.

---

## Créditos y Roles

| Nombre           | Rol                       | Contribución principal                                     |
|-----------------|---------------------------|-----------------------------------------------------------|
| Juanita Parra     | Multimedia | Producción de video y recursos visuales     |
| Alejandro parra   | Modelado   | Diseño de diagramas UML, patrones de diseño, modelado de clases y relaciones |
| Esteban Sequeda      | Documentación | Redacción del documento y coordinación del proyecto |

---

## Adicionales
[Prototipo en Figma](https://www.figma.com/make/tQGUC20DmAsd0Wcd2sJA6u/Koins-Mobile-Finance-App?p=f&fullscreen=1)
