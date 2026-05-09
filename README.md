# Práctica 3

## 1. Explicación de las Gráficas
A continuación se describen los resultados obtenidos tras la teleoperación del robot y la ejecución de la tarea de pick and place.

### A. Posición de las ruedas vs Tiempo
<img width="1201" height="602" alt="ruedas_tiempo" src="https://github.com/user-attachments/assets/e1c7d3bb-583e-4859-93d1-45cea65b033c" />


- La **primera fase** corresponde al desplazamiento hacia adelante del rover para recoger el cubo verde. Se observa cómo las ruedas giran algo menos de 5 radianes, adquiriendo valores positivos y negativos; esto se debe a que los ejes de giro de las ruedas derechas e izquierdas son opuestos.

- La **segunda fase** corresponde a la tarea de pick and place del cubo azul. En la gráfica se aprecia que las ruedas regresan a su posición inicial y permanecen detenidas durante más de 200 segundos.

- La **tercera fase** corresponde al desplazamiento final de 10 metros del rover, motivo por el cual se registra un incremento muy pronunciado en la posición angular de las ruedas.


### B. Aceleración vs Tiempo
<img width="1201" height="602" alt="aceleracion_tiempo" src="https://github.com/user-attachments/assets/e83f11ab-4c94-44d1-9b33-fdd5cc8984d6" />

- La **aceleración en el eje Z** se mantiene estable en un valor aproximado de 10 m/s², lo cual se debe a la fuerza de la gravedad simulada por Gazebo. Los picos que alteran esta constante coinciden exactamente con los instantes en los que el robot acelera (algo que resulta evidente al comparar estos datos con la gráfica anterior).

- La **aceleración en los ejes X e Y** oscila en torno a cero, pero presenta picos claros durante las aceleraciones del rover. El pico más marcado ocurre en la fase final, cuando el robot avanza los 10 metros de forma continua.

### C. Gasto vs Tiempo

<img width="1201" height="602" alt="gasto_tiempo" src="https://github.com/user-attachments/assets/d43b18f2-afb6-4fc5-980e-40cded40053e" />

- En el **estado de reposo**, el gasto se estabiliza en un valor aproximado de 200. No desciende a 0 porque los joints necesitan ejercer fuerza continuamente para mantener el brazo en su posición, en especial el joint prismático vertical. Además, se aprecian picos que coinciden con las aceleraciones del rover; al moverse, las articulaciones deben aplicar fuerza adicional para contrarrestar la inercia del brazo.

- Durante el **estado de pick and place**, el gasto supera el valor de 2000 en dos ocasiones distintas. La primera elevación corresponde al pick del cubo verde y se identifica fácilmente por ser más breve en el tiempo. La segunda corresponde al proceso completo de pick and place del cubo azul. En ambos casos el gasto se incrementa drásticamente porque los joints deben realizar un esfuerzo mucho mayor para sostener y desplazar el cubo.

- En el **estado final**, se observa cómo el gasto se dispara. Como se mencionó en el primer punto, esto es consecuencia de las inercias generadas en el brazo; dado que en esta fase el rover realiza una aceleración brusca y prolongada, los joints se ven obligados a ejercer una fuerza extrema para mantener el brazo rígido.

---

## 2. Enlace al Rosbag
### Enlace de Github
https://github.com/miguelpina5/Practica_3_modelado/tree/main/mi_rosbag_practica

### Enlace de OneDrive
https://urjc-my.sharepoint.com/:f:/g/personal/ma_pina_2023_alumnos_urjc_es/IgCtL3fIm99zR4JQ6dTsl8j5AWhR2cwnCR5KQGAj1_xAkRE?e=7fIcMe

---

## 3. Capturas de RViz y Transformadas
### A. joint_state_publisher_gui y TFs
<img width="1853" height="961" alt="joint_state_publisher" src="https://github.com/user-attachments/assets/6106decb-8d90-492d-970d-5d03464fd0cb" />

### B. Árbol de Transformadas
<img width="7835" height="2210" alt="arbol_transformadas" src="https://github.com/user-attachments/assets/5fb7e51e-4c2d-4f73-83ea-1c11800f59d5" />

---

## 4. Imágenes de la Simulación
### Sujetando cubo verde en el aire
<img width="465" height="517" alt="sujetando_cubo_verde" src="https://github.com/user-attachments/assets/e68674f6-4a7f-4ac9-b575-8158038aeca4" />


### Colocando cubo azul sobre el rojo
<img width="481" height="554" alt="sujetando_cubo_azul" src="https://github.com/user-attachments/assets/dabf938d-237e-4cb2-a576-65c49fede45a" />


<img width="481" height="554" alt="dejando_cubo_azul" src="https://github.com/user-attachments/assets/64e67349-717a-443b-af30-e65ea5621103" />


<img width="481" height="554" alt="cubo_azul_encima_rojo" src="https://github.com/user-attachments/assets/d2a8cc68-475f-45d8-b567-fa6beaa270d9" />

### Rover al avanzar 10 metros
<img width="481" height="554" alt="rover_10m" src="https://github.com/user-attachments/assets/689cdc6e-0fa3-4bc8-94f7-941db13c2f68" />


---
