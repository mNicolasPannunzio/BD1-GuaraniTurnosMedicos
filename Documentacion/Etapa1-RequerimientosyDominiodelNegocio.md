## 1️⃣ Etapa I: Requerimientos y Dominio del Negocio
### 📚 Descripción del caso
El sistema **"Guaraní Turnos Médicos"** es una plataforma web y móvil integral orientada a la administración y gestión de turnos en centros clínicos. 
Su propósito principal es optimizar los procesos operativos de programación, reserva, cancelación y supervisión de citas, mitigando ineficiencias tradicionales como los cuellos de botella en la recepción 
y las elevadas tasas de ausentismo.  
El alcance del sistema abarca a múltiples actores y módulos interconectados:
* 🧍‍♂️Pacientes: Cuentan con un entorno de autogestión para visualizar disponibilidad en tiempo real, reservar o cancelar turnos de manera autónoma.  
* 👨‍⚕️Médicos: Disponen de interfaces para visualizar su cronograma diario de pacientes y gestionar el estado de atención en sus consultorios.  
* 🧑‍💼Secretarios y Administradores: Poseen herramientas para el control de la agenda central, bloqueo de rangos horarios, gestión de espacios físicos (consultorios) y configuración de obras sociales aceptadas.

A través de la centralización de los datos, el sistema busca garantizar la consistencia de los registros clínicos y maximizar el aprovechamiento de las horas médicas.

## 📋Reglas de Negocio
A continuación, se detallan las **reglas formales que rigen la lógica operativa del sistema y su consecuente implementación en el modelo de base de datos relacional:**

* 📏*RN1* - Cada usuario del sistema (Paciente, Médico, Secretario o Administrador) se identifica unívocamente mediante su número de DNI y contraseña para iniciar sesión.  
* 📏*RN2* - De cada paciente se registra su DNI, nombre, apellido, correo electrónico, contraseña y, de forma opcional, su obra social.  
* 📏*RN3* - De cada médico profesional se almacena su DNI, nombre, apellido, correo electrónico, contraseña, matrícula y especialidad médica.  
* 📏*RN4* - De cada secretario se almacena su DNI, nombre, apellido, correo electrónico, contraseña y credencial.  
* 📏*RN5* - Una obra social registrada en la institución debe tener asociado de manera obligatoria al menos un plan de salud.  
* 📏*RN6* - Cada turno médico reservado debe quedar registrado indicando su código único, fecha, hora, paciente, médico asignado, especialidad y obra social.  
* 📏*RN7* - Un paciente puede reservar y gestionar uno o varios turnos médicos en el sistema. 
* 📏*RN8* - Un médico puede tener múltiples turnos asignados en su cronograma diario y atiende en un consultorio físico específico.  
* 📏*RN9* - La duración estándar de las consultas médicas en la agenda debe configurarse en un rango válido de entre 5 y 60 minutos.  
* 📏*RN10* - La cancelación de un turno programado solo está permitida si se realiza con un mínimo de 2 horas de anticipación al horario estipulado de inicio.  
* 📏*RN11* - Un paciente cuyo turno fue cancelado ingresa automáticamente a una lista de espera asociada a la especialidad requerida.  
* 📏*RN12* - Un turno médico cambia su estado automáticamente a "Ausente" si el paciente no se presenta en la recepción tras finalizar el horario de tolerancia estipulado. 
