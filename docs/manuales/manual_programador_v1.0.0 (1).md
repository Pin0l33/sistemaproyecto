# Manual del programador v1.0.0 — EntidadProyecto

Alumno: Lucas Del Pino — LPR 5° 3° A-B — E.E.S.T. N° 1 "Eduardo Ader". Documenta el uso de **struct** y del **operador flecha (->)** del archivo `src/main.cpp`.

## 1. La estructura

Un **struct** agrupa variables de distintos tipos bajo una misma entidad lógica, en bloques contiguos de RAM. Este es el modelo base propuesto para el Proyecto Integrador Anual:

```cpp
struct EntidadProyecto {
    int id;
    char nombre[50];
    float metrica;
};
```

`id` identifica la entidad, `nombre` guarda un texto de hasta 49 caracteres (más el terminador nulo) y `metrica` almacena un valor decimal (lectura de sensor, consumo, avance). En esta compilación el tamaño total es de 60 bytes (incluye 2 bytes de relleno para alinear el `float`).

## 2. Acceso a los miembros

Con una variable común se usa el punto (`miEntidad.id`). Con un puntero se usa el operador flecha (`ptr->id`), que equivale a `(*ptr).id`. Con un puntero no se puede escribir `ptr.id`, porque el punto exige un objeto y no una dirección.

## 3. Pasaje por dirección

```cpp
void cargarDatos(EntidadProyecto* ptr);   // prototipo
cargarDatos(&miEntidad);                   // llamada con la dirección
```

La función recibe solamente la dirección de la estructura, por lo que modifica el original sin copiarlo.

## 4. Lectura de datos y buffer de entrada

El orden es: `cin >> ptr->id;`, luego `cin.ignore();` y recién después `cin.getline(ptr->nombre, 50);`. Sin `cin.ignore()`, el Enter (\n) que queda en el buffer después del número hace que `getline` lea una línea vacía y se saltee el ingreso del nombre. El límite de 50 evita escribir fuera del arreglo.

## 5. Compilación y ejecución

```cpp
g++ src/main.cpp -o src/sistemaproyecto.exe
.\src\sistemaproyecto.exe
```

## 6. Uso en el Proyecto Integrador Anual

No aplica