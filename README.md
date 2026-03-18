# ⚡ C DESDE CERO - GUÍA COMPLETA

**C desde Cero** es un sitio educativo completo diseñado para enseñar C desde los fundamentos hasta conceptos avanzados, con explicaciones claras, ejemplos prácticos y código listo para usar.

> *"C is a general-purpose programming language created by Dennis Ritchie at Bell Labs. It remains one of the most widely used programming languages."*

---

## 🎯 ¿Qué es este Proyecto?

Este proyecto proporciona un recurso educativo gratuito para aprender C, incluyendo:

- **Documentación completa** de cada tema
- **Ejemplos de código** listos para ejecutar
- **Ejercicios prácticos** para reforzar el aprendizaje
- **Sitio web educativo** con navegación intuitiva

---

## 📚 Contenido del Curso

### Módulo 1: Fundamentos

1. **Introducción**
   - Historia de C
   - Influencia en otros lenguajes
   - Casos de uso (Sistemas embebidos, SO)

2. **Instalación**
   - GCC / Clang
   - Make y gestión de proyectos
   - IDEs recomendados
   - Configuración del entorno

3. **Conceptos básicos**
   - Variables y tipos de datos
   - Punteros
   - Control de flujo
   - Funciones

### Módulo 2: Intermedio

4. **Ejemplos prácticos**
   - Arrays y strings
   - Structs
   - Manejo de memoria (malloc/free)
   - Archivos

5. **Buenas prácticas**
   - Gestión de memoria segura
   - Error handling
   - Código portable
   - Debugging con GDB

### Módulo 3: Avanzado

6. **Casos reales**
   - Sistemas embebidos
   - Desarrollo de drivers
   - Redes y sockets
   - Multithreading con pthreads

7. **Proyecto final**
   - Aplicación completa
   - Build system con Make
   - Testing y debugging

---

## 🗂️ Estructura del Proyecto

```
Repositorio-MongoDB/
├── index.html          # Página principal
├── css/
│   └── styles.css      # Estilos del sitio
├── js/
│   └── main.js         # JavaScript del sitio
└── README.md
```

---

## 🚀 Cómo Usar este Proyecto

### Opción 1: Navegar el Sitio Web

1. Abre `index.html` en tu navegador
2. Navega por las secciones del curso
3. Haz clic en los temas para ver la documentación detallada

### Opción 2: Ejecutar los Ejemplos

1. Instala GCC
2. Compila con `gcc archivo.c -o programa`
3. Ejecuta `./programa`

### Requisitos

- GCC o Clang
- Make (opcional)
- GDB para debugging

---

## 📝 Ejemplos Rápidos

### Hola Mundo

```c
#include <stdio.h>

int main() {
    printf("Hola Mundo!\n");
    return 0;
}
```

### Variables y Tipos

```c
#include <stdio.h>

int main() {
    // Tipos fundamentales
    int edad = 30;
    float altura = 1.75f;
    double pi = 3.14159265;
    char inicial = 'J';
    _Bool esEstudiante = 1;  // o usar <stdbool.h>

    printf("Edad: %d\n", edad);
    printf("Altura: %.2f\n", altura);
    printf("Inicial: %c\n", inicial);

    return 0;
}
```

### Punteros

```c
#include <stdio.h>

int main() {
    int valor = 42;
    int* ptr = &valor;

    printf("Valor: %d\n", valor);
    printf("Direccion: %p\n", (void*)&valor);
    printf("Valor via puntero: %d\n", *ptr);

    // Puntero a puntero
    int** ptr2 = &ptr;
    printf("Valor via doble puntero: %d\n", **ptr2);

    return 0;
}
```

### Arrays y Strings

```c
#include <stdio.h>
#include <string.h>

int main() {
    // Array
    int numeros[5] = {1, 2, 3, 4, 5};

    // String (array de chars)
    char nombre[] = "Juan";
    char saludo[50];

    // Copiar string
    strcpy(saludo, "Hola ");
    strcat(saludo, nombre);

    printf("%s\n", saludo);
    printf("Longitud: %zu\n", strlen(nombre));

    // Iterar array
    for (int i = 0; i < 5; i++) {
        printf("%d ", numeros[i]);
    }

    return 0;
}
```

### Structs

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

typedef struct {
    char nombre[50];
    int edad;
    float altura;
} Persona;

int main() {
    Persona p1;
    strcpy(p1.nombre, "Juan");
    p1.edad = 30;
    p1.altura = 1.75f;

    // Array de structs
    Persona personas[3];

    // Puntero a struct
    Persona* ptr = &p1;
    printf("%s\n", ptr->nombre);  // equivalente a (*ptr).nombre

    return 0;
}
```

### Manejo de Memoria

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // malloc
    int* array = (int*)malloc(10 * sizeof(int));
    if (array == NULL) {
        fprintf(stderr, "Error asignando memoria\n");
        return 1;
    }

    // Usar memoria
    for (int i = 0; i < 10; i++) {
        array[i] = i * 2;
    }

    // free
    free(array);
    array = NULL;  // Prevenir dangling pointer

    // realloc
    array = (int*)realloc(array, 20 * sizeof(int));

    return 0;
}
```

### Archivos

```c
#include <stdio.h>

int main() {
    // Escribir archivo
    FILE* archivo = fopen("datos.txt", "w");
    if (archivo != NULL) {
        fprintf(archivo, "Hola Archivo\n");
        fclose(archivo);
    }

    // Leer archivo
    archivo = fopen("datos.txt", "r");
    if (archivo != NULL) {
        char linea[100];
        while (fgets(linea, sizeof(linea), archivo) != NULL) {
            printf("%s", linea);
        }
        fclose(archivo);
    }

    return 0;
}
```

---

## 🎓 Metodología de Aprendizaje

### 1. Leer la Teoría
Cada tema comienza con una explicación clara del concepto.

### 2. Ver Ejemplos
Los ejemplos de código muestran la aplicación práctica.

### 3. Practicar
Los ejercicios te permiten aplicar lo aprendido.

### 4. Experimentar
Modifica los ejemplos para entender cómo funcionan.

---

## 🔧 Comandos Esenciales

### Compilación

```bash
# Compilar simple
gcc main.c -o programa

# Compilar con warnings
gcc -Wall -Wextra -pedantic main.c -o programa

# Compilar con debug
gcc -g main.c -o programa

# Compilar múltiples archivos
gcc main.c utils.c -o programa

# Usar Make
make

# Debug con GDB
gdb ./programa
```

---

## 📖 Recursos Adicionales

### Documentación Oficial

- [C Reference](https://en.cppreference.com/w/c)
- [GNU C Manual](https://www.gnu.org/software/gnu-c-manual/)
- [ISO C Standard](https://www.iso.org/standard/74528.html)

### Herramientas Recomendadas

- **GCC** - Compilador GNU
- **GDB** - Debugger
- **Valgrind** - Detección de memory leaks
- **Make** - Build automation

### Comunidades

- [C Community](https://stackoverflow.com/questions/tagged/c)
- [Reddit r/C_Programming](https://www.reddit.com/r/C_Programming/)
- [Comp.lang.c](https://groups.google.com/g/comp.lang.c)

---

## 💡 Consejos para Principiantes

1. **Entiende punteros**: Son fundamentales en C.
2. **Gestiona memoria cuidadosamente**: Siempre haz free().
3. **Usa const**: Previene modificaciones accidentales.
4. **Verifica retornos**: Chequea si malloc/fopen fallan.
5. **Aprende a usar GDB**: Debugging es esencial.

---

## ⚠️ Mejores Prácticas

### Seguridad

- Valida siempre los inputs
- Usa snprintf en lugar de sprintf
- Chequea límites de arrays

### Memoria

- Libera toda memoria asignada
- Setea punteros a NULL después de free
- Usa valgrind para detectar leaks

### Código Limpio

- Sigue convenciones de nombrado
- Comenta código complejo
- Mantén funciones pequeñas

---

## 🧪 Ejercicios Prácticos

### Nivel Básico

1. Calculadora de consola
2. Gestor de contactos
3. Juego de adivinar números

### Nivel Intermedio

1. Sistema de archivos
2. Parser de CSV
3. Lista enlazada

### Nivel Avanzado

1. Servidor TCP
2. Shell simple
3. Implementación de malloc

---

## 👨‍💻 Desarrollado por Isaac Esteban Haro Torres

**Ingeniero en Sistemas · Full Stack · Automatización · Data**

- 📧 Email: zackharo1@gmail.com
- 📱 WhatsApp: 098805517
- 💻 GitHub: https://github.com/ieharo1
- 🌐 Portafolio: https://ieharo1.github.io/portafolio-isaac.haro/

---

© 2026 Isaac Esteban Haro Torres - Todos los derechos reservados.
