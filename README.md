# DooR DasH: Turn-Based Strategy Engine & JavaFX MVC Architecture

A full-featured, turn-based desktop strategy game and rule-execution engine built in **Java** and **JavaFX**. Engineered strictly around **Model-View-Controller (MVC)** separation and **SOLID** object-oriented design principles across 10 modular packages (`game.engine.*`, `game.gui.*`, `game.tests`), the system orchestrates a 100-cell serpentine board grid, polymorphic monster and card hierarchies, CSV-driven state initialization, custom checked exception handling, and an animated 1400x900 JavaFX user interface.

## Core Engineering Highlights

- **Strict 10-Package Modular Hierarchy:** Decouples core board orchestration (`game.engine`), polymorphic entities (`monsters`, `cells`, `cards`), behavioral contracts (`interfaces`), CSV ingestion (`dataloader`), domain-specific error handling (`exceptions`), JUnit verification (`game.tests`), and the JavaFX presentation tier (`game.gui.main`, `game.gui.controller`, `game.gui.view`).
- **Polymorphic State & Energy Modification:** Implements the `CanisterModifier` interface and `Comparable<Monster>` ordering across 4 specialized monster archetypes (`Dasher`, `Dynamo`, `MultiTasker`, `Schemer`), 5 cell subclasses, and 5 dynamic card types.
- **Transactional Movement & Collision Rollback:** Evaluates multi-hop board movement (dice roll -> conveyor/sock transport -> card draw effects) and enforces atomic position rollback with custom checked exceptions (`InvalidMoveException`) whenever a final destination collides with an opponent.
- **Animated 1400x900 JavaFX GUI (`GameView` & `GameController`):** Features a custom dark-neon `BorderPane` layout with a 100-cell `GridPane` (78x78 px `StackPane` tiles), pulsing `ScaleTransition` player tokens, real-time `ProgressBar` energy meters, a live terminal `TextArea` telemetry log, animated card-draw popups, and developer debug keybindings (`W` / `E`).
