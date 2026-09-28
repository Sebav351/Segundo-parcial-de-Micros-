# Sistema de Logística Inteligente de Monedas

Propuesta de automatización para clasificar monedas colombianas, agruparlas en vasos y transportarlas hasta una meta mediante un minitanque con orugas, brazo articulado y pinza.

## Descripción

El sistema combina clasificación, transporte y entrega de monedas. La propuesta general también contempla un panel de seguimiento y un chatbot que comente el proyecto por voz. El minitanque reemplaza al dron mostrado en el esquema inicial para recoger y transportar los vasos.

## Funcionamiento

1. **Selección y clasificación:** se define cuántas monedas se procesan de cada denominación: $50, $100, $200, $500 y $1.000 COP. En la simulación, un selector rotatorio conduce las monedas por una rampa hacia canales separados por tamaño.
2. **Agrupación:** las monedas clasificadas se acumulan en vasos identificados con su denominación.
3. **Transporte a la zona de carga:** al completar cada grupo, los vasos pasan a una banda transportadora que los lleva a la zona donde espera el minitanque.
4. **Recolección y recorrido:** el minitanque toma un vaso con su brazo y pinza, sigue la pista y ajusta su trayectoria para rodear los obstáculos.
5. **Entrega:** al llegar a la meta, libera el vaso y registra su valor. El ciclo se repite con los demás vasos.

La misión termina cuando los cinco vasos llegan a la meta. El valor entregado corresponde a la suma de las monedas transportadas.

## Simulador 3D

El archivo `minitanque.html` presenta una simulación interactiva en el navegador, construida con Three.js. En ella se visualizan el clasificador, las bandas, los vasos, la pista, los obstáculos y el minitanque.

La simulación permite:

- Configurar cantidades de monedas y velocidad de clasificación.
- Iniciar el proceso de clasificación y transporte.
- Conducir manualmente el minitanque o activar el modo autónomo.
- Controlar el brazo y abrir o cerrar la pinza.
- Cambiar la vista de cámara y la velocidad de la simulación.
- Consultar velocidad, posición, carga, vasos entregados, valor acumulado, distancia y tiempo.

### Controles manuales

| Teclas | Acción |
|---|---|
| `W` / `S` o flechas arriba / abajo | Avanzar / retroceder |
| `A` / `D` o flechas izquierda / derecha | Girar |
| `R` / `F` | Subir / bajar el brazo |
| `Espacio` o `G` | Abrir / cerrar la pinza |
| `P` | Activar / detener el modo autónomo |
| `C` | Cambiar la cámara |
| `X` | Reiniciar la simulación |

La escala de la escena es de una unidad por cada 10 cm.

## Alcance de la implementación

El HTML simula el proceso y sus componentes; no controla maquinaria física ni cuenta monedas mediante una cámara o un sensor. Las cantidades se seleccionan en la interfaz. El panel visible muestra métricas de la simulación; el dashboard independiente y el chatbot por voz aparecen en la propuesta visual, pero no están implementados en este simulador.
