# tp_clinica
# 🏥 Sistema de Gestión para una Clínica

---

## 📝 Consigna

Desarrollar un sistema de gestión para una **clínica médica** utilizando programación orientada a objetos en Python. El sistema debe permitir:

- Registrar y administrar **pacientes** y **médicos**.
- Gestionar las **especialidades médicas** y sus **días de atención**.
- Agendar **turnos** entre pacientes y médicos.
- Emitir **recetas médicas**.
- Mantener una **historia clínica** por paciente.

---

## 📦 Entregables

1. Código fuente con separación entre modelo y CLI.
2. Pruebas unitarias (`unittest`).
3. Documentación breve: ejecución, tests y diseño general.

---

## 👤 Información del Alumno

- **Nombre y Apellido**: Diego Aubone  
- **Ciclo Lectivo**: 2025  
- **Carrera**: Ingenieria Informatica  

---

## ⏰ Fechas Importantes

- **Límite**: 17 de junio de 2025  
- **Sugerida**: Semana del 10 de junio de 2025  

**Instrucciones clave:**

- Leer bien la consigna.
- Consultar dudas en clase.
- No postergar: no se aceptan entregas fuera de término.
- Entrega completa y en tiempo es requisito para continuar cursando.

---

## 🚨 Requisitos Técnicos

- Clases: `Paciente`, `Medico`, `Turno`, `Receta`, `Especialidad`, `HistoriaClinica`, `Clinica`.
- Validaciones desde el modelo.
- Excepciones personalizadas.
- CLI para la interacción.
- Pruebas con `unittest`.

---

## 📘 Clases Principales

### Paciente

- Atributos: `__nombre__`, `__dni__`, `__fecha_nacimiento__`
- Métodos: `obtener_dni()`, `__str__()`

---

### Medico

- Atributos: `__nombre__`, `__matricula__`, `__especialidades__`
- Métodos: `agregar_especialidad()`, `obtener_matricula()`, `obtener_especialidad_para_dia()`, `__str__()`

---

### Especialidad

- Atributos: `__tipo__`, `__dias__`
- Métodos: `obtener_especialidad()`, `verificar_dia()`, `__str__()`

---

### Turno

- Atributos: `__paciente__`, `__medico__`, `__fecha_hora__`, `__especialidad__`
- Métodos: `obtener_medico()`, `obtener_fecha_hora()`, `__str__()`

---

### Receta

- Atributos: `__paciente__`, `__medico__`, `__medicamentos__`, `__fecha__`
- Métodos: `__str__()`

---

### HistoriaClinica

- Atributos: `__paciente__`, `__turnos__`, `__recetas__`
- Métodos: `agregar_turno()`, `agregar_receta()`, `obtener_turnos()`, `obtener_recetas()`, `__str__()`

---

### Clinica

- Atributos: `__pacientes__`, `__medicos__`, `__turnos__`, `__historias_clinicas__`
- Métodos:
  - Registro: `agregar_paciente()`, `agregar_medico()`
  - Acceso: `obtener_pacientes()`, `obtener_medicos()`, `obtener_medico_por_matricula()`
  - Turnos: `agendar_turno()`, `obtener_turnos()`
  - Recetas/Historia: `emitir_receta()`, `obtener_historia_clinica()`
  - Validaciones: `validar_existencia_paciente()`, `validar_turno_no_duplicado()`, etc.

---

## ⚠️ Excepciones Personalizadas

Ejemplos:
- `PacienteNoEncontradoException`
- `MedicoNoDisponibleException`
- `TurnoOcupadoException`
- `RecetaInvalidaException`

Capturadas por `CLI` para evitar errores técnicos en consola.

---

## 💻 Interfaz de Consola (CLI)

### Función

- Muestra menú interactivo.
- Solicita datos.
- Llama métodos de `Clinica`.
- No valida lógica de negocio.
- Maneja errores con `try-except`.

### Menú

```text
1) Agregar paciente
2) Agregar médico
3) Agendar turno
4) Agregar especialidad
5) Emitir receta
6) Ver historia clínica
7) Ver todos los turnos
8) Ver todos los pacientes
9) Ver todos los médicos
0) Salir
