# Bono Parcial - Primer Corte AREP 2024-1

---

## Descripción del Proyecto

Este proyecto es una extensión del parcial **ReflexCalculator**, una aplicación web que funciona como calculadora. Permite realizar operaciones matemáticas básicas y, además, ordenar una lista de números utilizando el algoritmo **BubbleSort** mediante el comando `bbl`. Los resultados se presentan en la parte inferior de la página.

---

## Requisitos Funcionales

- La **calculadora** (ReflexCalculator) es responsable de realizar los cálculos. La **fachada de servicios** (ServiceFacade) actúa como intermediario, delegando los cálculos al ReflexCalculator.
- El diseño de los servicios web debe seguir buenas prácticas de programación orientada a objetos (POO).
- Los servicios deben desplegarse en máquinas virtuales separadas.
- Las solicitudes desde el cliente hacia el servicio de la calculadora deben ser asíncronas y utilizar el mínimo de JavaScript posible, evitando la recarga de la página en cada llamada. Solo se actualizará el resultado.
- El API de la fachada será:
    - `/calculadora`: Entrega el cliente web en formato HTML + JS.
    - `/computar?comando=[comando con parámetros]`: Retorna el valor solicitado en formato JSON.
- El API de la calculadora será:
    - `/compreflex=[comando con parámetros]`: Retorna el valor solicitado en formato JSON.
- Asegúrese de devolver los encabezados HTTP correctos y responder con mensajes válidos ante solicitudes inesperadas.

---

## Arquitectura

![Diagrama de la Arquitectura](https://github.com/user-attachments/assets/09d66978-5c60-4b60-8c06-9f0f02b2b5e3)

- La aplicación consta de tres componentes: una fachada de servicios, un servicio de calculadora y un cliente web (HTML + JS).
- Los servicios de la fachada y de la calculadora deben estar desplegados en diferentes máquinas virtuales Java (no es necesario usar Docker ni AWS).
- El cliente web se descarga desde la fachada y no es necesario cargarlo desde disco.
- La comunicación se realiza a través de HTTP, y las respuestas de los servicios son en formato JSON.

---

### Construido con:

* [Git](https://git-scm.com) - Control de versiones
* [Maven](https://maven.apache.org/download.cgi) -  Manejador de dependencias
* [java](https://www.oracle.com/java/technologies/downloads/#java22) - Lenguaje de programación

### Requisitos:

#### ⚠️ Importante

Es necesario tener instalado Git, Maven 3.9.9 y Java 17 para poder ejecutar el proyecto.

## Instalación

1. **Clona el proyecto:**

    ```bash
    git clone https://github.com/AndresArias02/BonoArepParcial1.git
    ```

2. **Accede al directorio del proyecto:**

    ```bash
    cd BonoArepParcial1
    ```

3. **Compila el proyecto utilizando Maven:**

    ```bash
    mvn clean compile
    ```

4. **Ejecuta los siguientes comandos en terminales diferentes:**

    ```bash
    java -cp target/classes org.example.CalcReflexServer
    ```

    ```bash
    java -cp target/classes org.example.CalcReflexFacade
    ```

El proyecto estará funcionando. Para abrirlo, accede al siguiente enlace en tu navegador: [http://localhost:35000](http://localhost:35000).

---

## Pruebas

Hemos realizado pruebas de la calculadora para los siguientes casos:

- **Sin parámetros:**

  ![Sin parametros Prueba](https://github.com/user-attachments/assets/727e0510-f91f-4223-b296-110d293ca235)

- **Un parámetro:**

  ![Un parametro Prueba](https://github.com/user-attachments/assets/146a183e-1bf7-4cb3-a73c-bca3d2e46116)

- **Dos parámetros:**

  ![Dos parametros Prueba](https://github.com/user-attachments/assets/d1947c5a-dba1-4ed8-a66a-da4d1393a273)

- **BBL:**

  ![BBL Prueba](https://github.com/user-attachments/assets/a0c5acc0-c467-427a-95a3-0f89d5cd313d)

## Autores

- Andrés Arias - [AndresArias02](https://github.com/AndresArias02)

## Licencia

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Este proyecto está bajo la Licencia (MIT) - ver el archivo [LICENSE](LICENSE.md) para ver más detalles.

## Agradecimientos

- Al profesor [Luis Daniel Benavides Navarro](https://ldbn.is.escuelaing.edu.co) por compartir sus conocimientos.
    
