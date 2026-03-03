# 🌐 Web Semántica y Datos Abiertos — Tarea Final

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TU_USUARIO/web-semantica-tarea-final/blob/main/notebooks/Tarea1_Modelado_RDF.ipynb)

**Universidad Técnica Federico Santa María**  
**Departamento de Informática — Magíster en Tecnologías de la Información**  
**Curso:** Web Semántica y Datos Abiertos  
**Profesor:** Jose Emilio Labra Gayo  
**Autores:** Kevin Cortes · Cristian Orellana · Ricardo Roman  
**Fecha de entrega:** 15 de Marzo de 2026

---

## 📋 Descripción del Proyecto

Este repositorio contiene el código, datos y documentación de la **Tarea Final** del curso de Web Semántica y Datos Abiertos. El proyecto aborda el modelado, transformación y validación de datos de salud utilizando tecnologías de la Web Semántica:

| Tarea | Descripción | Notebook |
|-------|-------------|----------|
| **Tarea 1** | Modelado de datos privados (Clínica Bienestar) en RDF/Turtle | [Tarea1_Modelado_RDF.ipynb](notebooks/Tarea1_Modelado_RDF.ipynb) |
| **Tarea 2** | Transformación de datos abiertos (Catálogo Nacional de Hospitales) a RDF | [Tarea2_Transformacion_Datos_Abiertos.ipynb](notebooks/Tarea2_Transformacion_Datos_Abiertos.ipynb) |
| **Tarea 3** | Validación de grafos RDF con ShEx y SHACL | [Tarea3_Validacion_ShEx_SHACL.ipynb](notebooks/Tarea3_Validacion_ShEx_SHACL.ipynb) |
| **Tarea 4** | Comparación SPARQL vs LLMs para consulta de datos | [Tarea4_SPARQL_vs_LLM.ipynb](notebooks/Tarea4_SPARQL_vs_LLM.ipynb) |

---

## 🗂️ Estructura del Repositorio

```
web-semantica-tarea-final/
│
├── README.md                          ← Este archivo
│
├── data/
│   ├── private/
│   │   └── clinica_bienestar.ttl      ← Grafo RDF de pacientes y citas (Turtle)
│   ├── open/
│   │   ├── hospitales.csv             ← Catálogo Nacional de Hospitales (CSV)
│   │   └── hospitales.ttl             ← Hospitales transformados a RDF (Turtle)
│   └── validation/
│       └── datos_incorrectos.ttl      ← Datos con errores para demostrar validación
│
├── schemas/
│   ├── clinica_bienestar.shex         ← Esquema de validación ShEx
│   └── clinica_bienestar.shacl.ttl    ← Esquema de validación SHACL (Turtle)
│
├── notebooks/
│   ├── Tarea1_Modelado_RDF.ipynb
│   ├── Tarea2_Transformacion_Datos_Abiertos.ipynb
│   ├── Tarea3_Validacion_ShEx_SHACL.ipynb
│   └── Tarea4_SPARQL_vs_LLM.ipynb
│
└── sparql/
    └── consultas.sparql               ← Colección de consultas SPARQL
```

---

## 🚀 Instrucciones para Reproducir las Tareas

### Opción A: Google Colab (Recomendada)

Cada notebook está diseñado para ejecutarse directamente en Google Colab sin configuración adicional.

#### Pasos:

1. **Abrir el notebook en Colab** haciendo clic en el badge correspondiente:

   | Tarea | Enlace Colab |
   |-------|-------------|
   | Tarea 1 | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TU_USUARIO/web-semantica-tarea-final/blob/main/notebooks/Tarea1_Modelado_RDF.ipynb) |
   | Tarea 2 | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TU_USUARIO/web-semantica-tarea-final/blob/main/notebooks/Tarea2_Transformacion_Datos_Abiertos.ipynb) |
   | Tarea 3 | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TU_USUARIO/web-semantica-tarea-final/blob/main/notebooks/Tarea3_Validacion_ShEx_SHACL.ipynb) |
   | Tarea 4 | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TU_USUARIO/web-semantica-tarea-final/blob/main/notebooks/Tarea4_SPARQL_vs_LLM.ipynb) |

2. **Actualizar la URL del repositorio** en la celda de clonación:
   ```python
   REPO_URL = 'https://github.com/TU_USUARIO/web-semantica-tarea-final.git'
   ```
   Reemplazar `TU_USUARIO` con el nombre de usuario real de GitHub.

3. **Ejecutar todas las celdas** en orden: `Runtime → Run all` (o `Ctrl+F9`).

---

### Opción B: Entorno Local

#### Requisitos previos
- Python 3.9 o superior
- Git

#### Pasos:

```bash
# 1. Clonar el repositorio
git clone https://github.com/TU_USUARIO/web-semantica-tarea-final.git
cd web-semantica-tarea-final

# 2. Crear entorno virtual (recomendado)
python -m venv venv
source venv/bin/activate        # Linux/Mac
# venv\Scripts\activate         # Windows

# 3. Instalar dependencias
pip install rdflib pyshacl pandas tabulate jupyter

# 4. Lanzar Jupyter Notebook
jupyter notebook notebooks/
```

---

## 📦 Dependencias Python

| Librería | Versión mínima | Uso |
|----------|---------------|-----|
| `rdflib` | 6.0+ | Manipulación de grafos RDF, consultas SPARQL |
| `pyshacl` | 0.20+ | Validación SHACL de grafos RDF |
| `pandas` | 1.3+ | Procesamiento del CSV de hospitales |
| `tabulate` | 0.8+ | Visualización de tablas en consola |
| `jupyter` | 1.0+ | Ejecución de notebooks (local) |

Instalación rápida:
```bash
pip install rdflib pyshacl pandas tabulate jupyter
```

---

## 📊 Descripción de los Datos

### Dataset Privado: Clínica Bienestar (`data/private/clinica_bienestar.ttl`)

Datos **ficticios** que simulan el sistema de gestión de historiales clínicos de la Clínica Bienestar.

**Vocabularios utilizados:**
- `foaf:` — Friend of a Friend (nombres de pacientes)
- `sdo:` — Schema.org (fechas de nacimiento)
- `clinic:` — Namespace propio (`http://www.clinica-bienestar.es/ontology#`)

**Clases:**
- `clinic:Paciente` — Paciente registrado en la clínica
- `clinic:Cita` — Cita médica programada

**Propiedades:**
- `clinic:idPaciente` — Identificador único del paciente
- `clinic:tieneCita` — Relación paciente → cita
- `clinic:fechaCita` — Fecha y hora de la cita (`xsd:dateTime`)
- `clinic:conDiagnostico` — Código CIE-10 del diagnóstico

**Pacientes incluidos:**

| ID | Nombre | Diagnósticos |
|----|--------|-------------|
| P7821A | Carlos Sánchez | I10 (Hipertensión), J06.9 (Infección respiratoria) |
| P9345B | Laura Martínez | E11 (Diabetes tipo 2) |
| P4412C | Miguel Torres | M54.5 (Lumbago) |
| P6678D | Ana García | F32.0 (Episodio depresivo leve) |
| P3301E | Pedro Ramírez | I25.1 (Enfermedad aterosclerótica), I10 (Hipertensión) |

---

### Dataset Abierto: Catálogo Nacional de Hospitales (`data/open/`)

**Fuente:** [datos.gob.es — Catálogo Nacional de Hospitales](https://datos.gob.es/es/catalogo/e05070101-centros-y-servicios-del-sns-catalogo-nacional-de-hospitales)  
**Licencia:** Datos abiertos del Gobierno de España

**Formato original:** CSV con columnas `CNH`, `HOSPITAL`, `DIRECCION`, `COD_POSTAL`, `MUNICIPIO`, `COMUNIDAD_AUTONOMA`, `CAMAS`, `TIPO`

**Transformación RDF:**
- Cada hospital → instancia de `sdo:Hospital`
- Código CNH → URI del recurso
- Dirección → instancia de `sdo:PostalAddress`

---

## ✅ Esquemas de Validación

### ShEx (`schemas/clinica_bienestar.shex`)

Define 4 formas de validación:
- `<PacienteShape>` — Valida instancias de `clinic:Paciente`
- `<CitaShape>` — Valida instancias de `clinic:Cita`
- `<HospitalShape>` — Valida instancias de `sdo:Hospital`
- `<PostalAddressShape>` — Valida instancias de `sdo:PostalAddress`

### SHACL (`schemas/clinica_bienestar.shacl.ttl`)

Equivalente SHACL con las mismas restricciones, ejecutable con `pyshacl`.

---

## 🔍 Consultas SPARQL

El archivo `sparql/consultas.sparql` contiene 10 consultas de ejemplo:

1. Listar todos los pacientes
2. Citas de un paciente específico
3. Número de citas por paciente
4. Pacientes con diagnóstico de Hipertensión (I10)
5. Listar hospitales con dirección
6. Hospitales por comunidad autónoma
7. Citas realizadas en 2026
8. CONSTRUCT — Grafo de pacientes y diagnósticos
9. ASK — ¿Existe algún paciente con diabetes?
10. Pacientes con más de una cita (HAVING)

---

## 📚 Referencias

- W3C. (2014). *RDF 1.1 Turtle*. https://www.w3.org/TR/turtle/
- W3C. (2017). *SPARQL 1.1 Query Language*. https://www.w3.org/TR/sparql11-query/
- Prud'hommeaux, E., et al. (2017). *Shape Expressions Language 2.1*. https://shex.io/shex-semantics/
- W3C. (2017). *Shapes Constraint Language (SHACL)*. https://www.w3.org/TR/shacl/
- Ministerio de Sanidad. (2023). *Catálogo Nacional de Hospitales*. https://datos.gob.es/
- Berners-Lee, T. (2009). *Linked Data*. https://www.w3.org/DesignIssues/LinkedData.html

---

## 📄 Licencia

Este proyecto es de uso académico. Los datos de la Clínica Bienestar son **completamente ficticios** y no representan información real de ningún paciente.
