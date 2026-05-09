# Práctica 3: Simulación de Robots usando Middleware

## 1. Explicación Detallada de las Gráficas
A continuación se describen los resultados obtenidos tras la teleoperación del robot y la ejecución de la tarea de *pick and place*.

### A. Posición de las ruedas vs Tiempo
<img width="1201" height="602" alt="ruedas_tiempo" src="https://github.com/user-attachments/assets/e1c7d3bb-583e-4859-93d1-45cea65b033c" />

En esta gráfica se observa el desplazamiento lineal de la base del robot. 
- **Comportamiento:** Las pendientes constantes indican una velocidad de crucero estable hacia el objetivo (cubo verde). Los tramos planos representan los momentos en los que el robot se detiene para que el brazo ejecute las maniobras de agarre.
- **Análisis:** Se aprecia una sincronía entre las cuatro ruedas, lo que indica un control de tracción correcto en la plataforma móvil.

### B. Aceleración vs Tiempo
<img width="1201" height="602" alt="aceleracion_tiempo" src="https://github.com/user-attachments/assets/e83f11ab-4c94-44d1-9b33-fdd5cc8984d6" />

La gráfica muestra las lecturas del sensor inercial en los ejes X, Y y Z.
- **Comportamiento:** El eje Z se mantiene constante cerca de los 9.8 m/s² (gravedad). Se observan picos de aceleración en los ejes X e Y que coinciden con los arranques y frenadas bruscas durante la teleoperación con el teclado.
- **Análisis:** Los picos menores durante el movimiento del brazo sugieren que las vibraciones del mecanismo SCARA son absorbidas correctamente por la inercia del chasis.

### C. Gasto vs Tiempo (Potencia del Mecanismo)

<img width="1201" height="602" alt="gasto_tiempo" src="https://github.com/user-attachments/assets/d43b18f2-afb6-4fc5-980e-40cded40053e" />

Se representa el gasto parcial calculado mediante la fórmula $G_{parcial}=\sum_{i=1}^{n}||F_{i}||$.
- **Comportamiento:** El gasto es mínimo cuando el brazo está en reposo. Se observa un pico máximo de esfuerzo en el momento en que el `joint_3` (prismático) eleva el cubo verde, venciendo la gravedad y la fricción.
- **Análisis:** El gasto aumenta proporcionalmente a la carga transportada, validando el análisis de coste del mecanismo.

---

## 2. Enlace al Rosbag
Puedes descargar el archivo de datos (`.mcap`) generado durante la práctica en el siguiente enlace:
- [Descargar Rosbag (Topics: /cmd_vel, /imu, /joint_states)](AQUÍ_TU_ENLACE_A_DRIVE_O_GITHUB)

---

## 3. Capturas de RViz y Transformadas
### A. Interfaz de Control y TFs
<img width="1853" height="961" alt="joint_state_publisher" src="https://github.com/user-attachments/assets/6106decb-8d90-492d-970d-5d03464fd0cb" />
*Descripción: RViz con TFs visibles, `joint_state_publisher_gui` activo y articulaciones desplazadas.*

### B. Árbol de Transformadas (TF Tree)
<img width="7835" height="2210" alt="arbol_transformadas" src="https://github.com/user-attachments/assets/5fb7e51e-4c2d-4f73-83ea-1c11800f59d5" />
*Descripción: Estructura jerárquica de los links del robot.*

---

## 4. Imágenes de la Simulación (Gazebo)
### Sujetando cubo verde en el aire
<img width="465" height="517" alt="sujetando_cubo_verde" src="https://github.com/user-attachments/assets/e68674f6-4a7f-4ac9-b575-8158038aeca4" />

### Colocando cubo azul sobre el rojo
<img width="481" height="554" alt="sujetando_cubo_azul" src="https://github.com/user-attachments/assets/dabf938d-237e-4cb2-a576-65c49fede45a" />

<img width="481" height="554" alt="dejando_cubo_azul" src="https://github.com/user-attachments/assets/64e67349-717a-443b-af30-e65ea5621103" />

<img width="481" height="554" alt="cubo_azul_encima_rojo" src="https://github.com/user-attachments/assets/d2a8cc68-475f-45d8-b567-fa6beaa270d9" />

### Rover al avanzar 10 metros
<img width="481" height="554" alt="rover_10m" src="https://github.com/user-attachments/assets/689cdc6e-0fa3-4bc8-94f7-941db13c2f68" />





---
