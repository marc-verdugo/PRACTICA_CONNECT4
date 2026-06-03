# Conecta 4 - Aplicación Móvil Android

Proyecto realizado por Bruno Verdugo Soria y Marc Verdugo Soria

## Descripción
Este proyecto es una aplicación Android del clásico juego **Conecta 4**. Permite jugar partidas personalizadas contra la máquina (IA) con un diseño moderno, fluido y adaptativo.

## Arquitectura y Tecnologías
La aplicación sigue las guías oficiales de desarrollo de Android, garantizando una separación limpia de responsabilidades y un rendimiento óptimo:

* **Lenguaje:** Kotlin.
* **Interfaz de Usuario:** Jetpack Compose (diseño declarativo y moderno).
* **Patrón Arquitectónico:** MVVM (Model-View-ViewModel).
* **Persistencia de Datos:**
    * **Room Database:** Almacenamiento local estructurado para guardar el historial de partidas.
    * **Preferences DataStore:** Gestión segura de las preferencias del usuario (alias, tamaño de cuadrícula, tiempo límite y dificultad).

## Estructura del Proyecto
El código fuente está organizado en los siguientes paquetes lógicos:
* `iu/`: Contiene las actividades principales (`MainActivity`, `GameActivity`, `ConfigurationActivity`, `HistoryActivity`, `ResultsActivity`, `HelpActivity`) y sus correspondientes layouts declarativos `@Composable`.
* `viewmodel/`: Contiene los ViewModels encargados de retener el estado de la UI y sobrevivir a los cambios de configuración.
* `data/`: Aloja la lógica de datos: Entidades de Room, el DAO (`GameRecordDao`), el Repositorio (`GameRepository`) y el contenedor de dependencias (`AppContainer`).
* `model/`: Lógica interna pura del tablero, direcciones de juego y cálculo de victorias.

## Características Principales
1.  **Partidas Personalizadas:** Configuración de alias de jugador, dimensiones de la cuadrícula (columnas) y modo de juego con temporizador.
2.  **IA Competitiva:** Tres niveles de dificultad ("Fàcil", "Mitjà", "Difícil").
3.  **Persistencia Robusta:** El historial de partidas se mantiene guardado de forma local y permite filtrados por resultado.
4.  **Integración con el Sistema:** Envío automatizado de logs detallados de la partida a través de clientes de correo electrónico externos mediante un Intent implícito.
