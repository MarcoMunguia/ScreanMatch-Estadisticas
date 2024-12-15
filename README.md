# 🌌 Aplicación de Series y Episodios - Análisis con Streams y Spring Framework

Este proyecto es una aplicación en **Java** que interactúa con la **API pública de Star Wars (SWAPI)** para obtener información sobre las películas y episodios, procesarla utilizando **lambdas**, **streams** y el **Spring Framework**, y generar estadísticas detalladas sobre las evaluaciones de episodios. 

El objetivo es aplicar herramientas avanzadas de Java para procesar datos, mejorar la depuración con `peek` y realizar análisis detallados utilizando `DoubleSummaryStatistics`.

---

## 🚀 ¿Qué hace esta aplicación?

1. **Consumo de API con Spring Framework**:
   - La aplicación utiliza Spring para realizar peticiones HTTP hacia la API pública de Star Wars (SWAPI) y recuperar datos de películas y episodios.

2. **Procesamiento de Datos con Streams**:
   - **Operaciones intermedias**: Utiliza `map`, `filter`, `sorted` y otras operaciones para transformar y filtrar datos.
   - **Operaciones finales**: Usa `collect`, `findFirst` y `reduce` para consolidar y obtener resultados.

3. **Visualización con `peek`**:
   - Implementa `peek` para inspeccionar los datos en cada etapa del procesamiento del Stream, facilitando la depuración.

4. **Análisis con `DoubleSummaryStatistics`**:
   - Genera estadísticas detalladas como:
     - Promedio de evaluaciones por temporada.
     - Mejor y peor episodio.
     - Total de evaluaciones.

5. **Uso de `Optional`**:
   - Implementa el contenedor `Optional` para manejar datos faltantes o referencias nulas al procesar episodios.

6. **Filtrado y Visualización de Resultados**:
   - Filtra los episodios más relevantes según las calificaciones y muestra los datos procesados en consola y archivos.

---

## 📂 Estructura del Proyecto

```plaintext
.
├── src
│   ├── main
│   │   ├── java
│   │   │   ├── com.example.seriesapp
│   │   │   │   ├── SeriesApplication.java      # Clase principal
│   │   │   │   ├── Episode.java                # Modelo para representar episodios
│   │   │   │   ├── EpisodeService.java         # Servicio para manejar la lógica del análisis
│   │   │   │   ├── StatisticsService.java      # Servicio para DoubleSummaryStatistics
│   │   │   │   ├── SwapiClient.java            # Cliente para consumir la API de SWAPI
│   │   │   │   └── Utils.java                  # Métodos auxiliares
│   │   ├── resources
│   │   │   ├── application.properties          # Configuración de Spring
│   │   │   └── movies                          # Carpeta con JSONs generados
│   ├── test
│   │   ├── java
│   │   │   ├── com.example.seriesapp           # Tests para validación de datos y lógica
├── README.md                                    # Documentación del proyecto
```

---

## 🛠️ Tecnologías Utilizadas

- **Lenguaje**: Java.
- **Framework**: Spring Framework (Spring Boot).
- **HTTP Client**: RestTemplate (integrado con Spring).
- **Gestión de JSON**: Gson o Jackson para manejar respuestas de la API.
- **Streams y Lambdas**: Para manipulación y procesamiento de datos.
- **DoubleSummaryStatistics**: Para análisis estadísticos.
- **Optional**: Para manejo seguro de referencias nulas.

---

## 🔧 Configuración y Ejecución

1. **Clonar el Repositorio**:
   ```bash
   git clone https://github.com/tuusuario/starwars-series-analysis.git
   cd starwars-series-analysis
   ```

2. **Configurar la API**:
   - En `application.properties`, establece la URL base de la API:
     ```properties
     swapi.api.base-url=https://swapi.dev/api
     ```

3. **Compilar y Ejecutar**:
   - Con **Maven** o **Gradle**, ejecuta:
     ```bash
     mvn spring-boot:run
     ```
   - O usa tu IDE favorito para correr la aplicación.

4. **Resultados**:
   - Los resultados se mostrarán en consola y se generarán archivos JSON por temporada en la carpeta `movies`.

---

## 📝 Ejemplo de Análisis (DoubleSummaryStatistics)

### Salida de Consola:
```plaintext
Temporada 1:
    Promedio de Evaluaciones: 8.5
    Mejor Episodio: Episodio 5 (Calificación: 9.1)
    Peor Episodio: Episodio 2 (Calificación: 7.8)
    Total de Evaluaciones: 10
```

### Ejemplo de Archivo JSON:
**Archivo: `season_1.json`**
```json
{
  "season": 1,
  "averageRating": 8.5,
  "bestEpisode": {
    "title": "The Empire Strikes Back",
    "rating": 9.1
  },
  "worstEpisode": {
    "title": "Attack of the Clones",
    "rating": 7.8
  },
  "totalReviews": 10
}
```

---

## 🎯 Aprendizajes

### 💡 Lambdas y Streams:
- **Filtrado**: Aprendí a filtrar datos relevantes con `filter`.
- **Transformación**: Transformar objetos de la API en modelos internos con `map`.
- **Depuración**: Usar `peek` para entender cada paso del procesamiento del Stream.

### 📊 Análisis con DoubleSummaryStatistics:
- Calcular métricas importantes como promedio, máximo y mínimo con menos código y más eficiencia.

### 🛠️ Spring Framework:
- Integrar una API REST usando **RestTemplate**.
- Configurar un entorno limpio y funcional con **Spring Boot**.

### 🔍 Optional y Manejo Seguro:
- Utilizar `Optional` para manejar datos nulos o faltantes de forma elegante y sin excepciones inesperadas.

---

## 🌟 Funcionalidades Futuras

- Ampliar el análisis para incluir personajes y naves espaciales.
- Crear una interfaz web con Spring MVC para mostrar los resultados.
- Agregar soporte para comparar temporadas y series.

---

## 🏷️ Etiquetas

`#Java` `#Streams` `#SpringFramework` `#SWAPI` `#Lambdas` `#JSON` `#DoubleSummaryStatistics`
