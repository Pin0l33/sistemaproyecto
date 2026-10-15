# sistemaproyecto — Modelado de datos con struct y punteros (C++)

**Materia:** Laboratorio de Programación (LPR) — E.E.S.T. N° 1 "Eduardo Ader", Vicente López  
**Curso:** 5° 3° A-B — **Actividad 5**  
**Integrante:** Lucas Del Pino

## Descripción del modelo
La estructura `EntidadProyecto` agrupa los datos de una entidad (sensor, módulo de hardware, usuario...):

| Miembro   | Tipo        | Uso                                   |
|-----------|-------------|---------------------------------------|
| `id`      | `int`       | Identificador de la entidad           |
| `nombre`  | `char[50]`  | Nombre o descripción                  |
| `metrica` | `float`     | Lectura, consumo, avance, etc.        |

La función `cargarDatos(EntidadProyecto* ptr)` recibe la dirección de la estructura (`&miEntidad`)
y completa sus miembros con el operador flecha (`ptr->id`, `ptr->nombre`, `ptr->metrica`).

## Estructura
```
sistemaproyecto/
├── .gitignore
├── LICENSE
├── README.md
├── docs/
│   ├── InformeEEST1_LPR2026_ACT05_G03_v1.0.0.pdf
│   └── manuales/ (manual_programador_v1.0.0.pdf / .md)
├── src/main.cpp
└── capturas/ejecucion_struct.png
```

## Compilar y ejecutar (PowerShell, Windows)
```
g++ src/main.cpp -o src/sistemaproyecto.exe
.\src\sistemaproyecto.exe
```
