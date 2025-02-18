# Actividad 6.3 Diagramas de estado

- **ID de la Actividad:** 6.3
- **Módulo:** EDES
- **Unidad de Trabajo:** UD6: Diagramas de comportamiento. Casos de uso y secuencia.
- **Fecha de Creación:** 18/02/2025
- **Fecha de Entrega:** 18/02/2025
- **Alumno(s):** 
  - **Nombre y Apellidos:** Jesús Gallardo Domínguez
  - **Correo electrónico:** jgaldom0701@g.educaand.es
  - **Iniciales del Alumno/Grupo:** JGD


## Diagrama de estados UML:

El código de mi diagrama de estados según mi criterio es el siguiente:

```
@startuml

[*] -->  cerrada
cerrada: Entry/ inicio detector
cerrada: Do/ detecta persona o no
cerrada: Exit/ respuesta del detector

cerrada --> cerrada: no detecta persona
cerrada --> puertaAbriendose : detecta persona

puertaAbriendose --> abierta: abriendo

abierta: Entry/ detector activo
abierta: Do/ vuelve a detectar persona o/e inicia contador
abierta: Exit/ respuesta del detector y volver a iniciar el mismo estado.


abierta --> puertaCerrandose : cerrando 
abierta --> abierta: detecta persona

puertaCerrandose --> cerrada : puerta cerrada
puertaCerrandose --> puertaAbriendose : detecta persona mientras cierra

@enduml
```

Gráficamente sería algo tal que así:

![](/assets/diagrama.png)

## Explicación:

La puerta inicialmente se encuentra cerrada, en el momento que detecta a alguien, la puerta comienza a abrirse. 

Una vez abierta, inicia un contador, si vuelve a detectar a alguien, el contador se reinicia, si no, cuando acabe la puerta comenzará a cerrarse. 

Si mientras está cerrándose, se detecta a una persona, la puerta pasará directamente a volver a abrirse hasta estar abierta, de lo contrario, la puerta pasará a estar cerrada y volverá a repetir dicho proceso.
