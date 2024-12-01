# kata_dni

Kata---DNI

Este proyecto es una aplicación Java que calcula la letra del DNI (Documento Nacional de Identidad) español.

Estructura del Proyecto

Kata---DNI

├── src

│   ├── main

│   │   └── java

│   │       └── App.java

│   └── test

│       └── java

│           └── AppTest.java

└── pom.xml


Funcionamiento
El programa sigue estos pasos:

    Solicita al usuario un número de DNI (entre 0 y 99999999).
    Valida la entrada del usuario.
    Calcula la letra correspondiente al número de DNI.
    Muestra el resultado al usuario.


    Diagrama de Secuencia
    ```mermaid
    sequenceDiagram
    actor Usuario
    participant App
    participant FuncionPedirNumero
    participant FuncionCalcularLetra

    loop Hasta que se introduzca un número válido
        Usuario->>App: Introduce número DNI
        App->>FuncionPedirNumero: Llama a pedirNumero()
        FuncionPedirNumero->>FuncionPedirNumero: Valida el número
        alt Número válido
            FuncionPedirNumero-->>App: Devuelve número válido
        else Número inválido
            FuncionPedirNumero-->>Usuario: Muestra mensaje de error
        end
    end

    App->>FuncionCalcularLetra: Llama a calcularLetra(numero)
    FuncionCalcularLetra->>FuncionCalcularLetra: Calcula módulo 23
    FuncionCalcularLetra->>FuncionCalcularLetra: Selecciona letra correspondiente
    FuncionCalcularLetra-->>App: Devuelve letra calculada

    App-->>Usuario: Muestra número y letra del DNI

    Requisitos

    Java Development Kit (JDK) 8 o superior
    JUnit 5 para los tests unitarios

Cómo ejecutar

    Clona este repositorio.
    Abre el proyecto en Visual Studio Code.
    Ejecuta la clase App.java para iniciar la aplicación.

Tests
Los tests unitarios se encuentran en AppTest.java. Puedes ejecutarlos directamente desde Visual Studio Code.