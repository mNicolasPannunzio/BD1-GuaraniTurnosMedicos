
## 🏛️ Universidad Nacional del Nordeste (UNNE)

### Facultad de Ciencias Exactas y Naturales y Agrimensura (FACENA)
* **Asignatura:** **BASES DE DATOS 1**
* **Año Académico:** 2026

### 👥 Integrantes del Grupo:
* **Obregón, Adrián Jesús** — *DNI: 45.456.141*
* **Pannunzio, Mario Nicolas** — *DNI: 43.825.227*
* **Perone, Tiziano** — *DNI: 46.724.743*

---

## 📌 DESCRIPCIÓN DEL PROYECTO

### 📐 Proyecto Base de Origen
Este trabajo toma como base conceptual y de especificación el **Proyecto Integrador realizado para la asignatura Ingeniería de Software 1** (Año 2026). 

Para consultar el documento original de Especificación de Requisitos de Software (ERS), la educción de requerimientos, entrevistas, historias de usuario y prototipos de pantalla, se puede acceder al siguiente enlace:

📄 **Documento Base ERS:** [ERS-GuaraniTurnosMedicos.pdf](Documentacion/ERS-GuaraniTurnosMedicos.pdf)

---

## 🎯 ALCANCE EN BASES DE DATOS 1

El objetivo principal de este repositorio es llevar a cabo la **fase de modelado, diseño conceptual, lógico, físico y desarrollo SQL de la Base de Datos Relacional** para el sistema *"Guaraní Turnos Médicos"*, tomando como referencia los requisitos educativos previamente formalizados.

### 🗄️ Aspectos Técnicos y Funcionalidades del Sistema a Persistir:

1. **Gestión de Usuarios y Roles (RBAC):**
   * Manejo de perfiles diferenciados: *Pacientes*, *Médicos*, *Secretarios* y *Administradores*.
   * Cifrado e integridad de credenciales de acceso conforme a la **Ley 25.326** (Protección de Datos Personales).

2. **Estructura y Catálogos Clínicos:**
   * Catálogo de **Especialidades Médicas** y asignación a profesionales.
   * Gestión de **Consultorios / Espacios Físicos** para evitar superposiciones.
   * Configuración de **Obras Sociales** y planes de salud aceptados (ej. *IOSCOR*, *Jerárquicos Salud*).

3. **Gestión de Agenda Médica y Disponibilidad:**
   * Configuración de días y rangos horarios de atención semanal por especialidad/médico.
   * Parametrización de la duración de consultas (15, 20, 30 min).
   * **Bloqueo temporal de agendas** por licencias, congresos o feriados (HU#15).

4. **Ciclo de Vida y Transacciones de Turnos Médicos:**
   * **Estados del Turno:** `Disponible` ➡️ `En proceso de reserva` ➡️ `Reservado` ➡️ `Paciente en Espera` ➡️ `En consulta` ➡️ `Finalizado` / `Ausente` / `Cancelado`.
   * **Control de Concurrencia (Bloqueo en tiempo real):** Prevención de condiciones de carrera cuando dos usuarios intentan seleccionar el mismo turno simultáneamente.
   * **Manejo de Tiempos de Expiración:** Liberación automática de turnos tras 5 minutos de inactividad durante la reserva.
   * **Reglas de Cancelación:** Permitida únicamente con más de 2 horas de anticipación.
   * **Lista de Espera Prioritaria:** Generación automática de cola de reasignación para turnos cancelados.

---

## 🛠️ TECNOLOGÍAS Y MOTOR DE BASE DE DATOS

* **Motor Relacional:** SQLServer / DBeaver (SGBD Relacional con soporte ACID)
* **Lenguaje:** SQL (DDL, DML, DCL, Triggers, Stored Procedures y Vistas)
* **Modelado:** Diagrama Entidad-Relación (DER) / Diagrama Relacional Tabular

---
