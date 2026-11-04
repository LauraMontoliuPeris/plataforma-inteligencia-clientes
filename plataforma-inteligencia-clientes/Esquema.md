1. Nuestra Empresa Ficticia

Online Retail Co.

Es una tienda online que vende productos y regalos.

Nuestro equipo de datos recibe el historial de compras y la dirección quiere saber:

¿Qué clientes están en riesgo de dejar de comprar y qué podemos hacer para retenerlos?

2. Preguntas que queremos responder

A. Comportamiento de clientes

Queremos saber:

¿Cuántos clientes tenemos?
¿Cuánto gastan?
¿Con qué frecuencia compran?
¿Cuánto tiempo llevan comprando?
¿Cuándo compraron por última vez?
¿Cuántos productos diferentes compran?
¿Hay clientes que compran muchísimo más que otros?
¿Existen diferentes tipos de clientes?

B. Segmentación
Descubirir grupos de Clientes ejemplo:

                 CLIENTES
                    │
        ┌───────────┼───────────┐
        ↓           ↓           ↓
     VIP         Regulares    Inactivos


C. Abandono (Churn)

¿Qué clientes tienen mayor probabilidad de dejar de comprar?

Y queremos saber:

¿Qué características tienen los clientes que abandonan?
¿Cuánto tiempo pasa normalmente entre compras?
¿El gasto está relacionado con el abandono?
¿La frecuencia de compra está relacionada?
¿Hay determinados segmentos con mayor abandono?
¿Podemos predecir el abandono antes de que ocurra?


D. Decisión empresarial

Cliente A
Riesgo: 85%
Gasto histórico: 2.400 €
→ PRIORIDAD ALTA

Cliente B
Riesgo: 90%
Gasto histórico: 20 €
→ PRIORIDAD BAJA

La empresa no necesariamente debería tratar igual a todos los clientes con el mismo riesgo. 
(Valor económico del cliente)

3. Definir Churn

CHURN = 1 si el cliente no realiza ninguna compra durante el período futuro. (abandona)
CHURN = 0 si vuelve a comprar. (permanece activo)

4. Definir Variables

| Variable              | Qué representa                       |
| --------------------- | ------------------------------------ |
| `customer_id`         | Identificador                        |
| `recency`             | Días desde la última compra          |
| `frequency`           | Número de compras                    |
| `monetary`            | Gasto total                          |
| `average_order_value` | Gasto medio por pedido               |
| `unique_products`     | Número de productos diferentes       |
| `total_items`         | Número total de artículos            |
| `customer_lifetime`   | Tiempo entre primera y última compra |
| `purchase_frequency`  | Frecuencia de compra                 |
| `country`             | País                                 |
| `churn`               | Abandono                             |

5. Base de datos

Customers
    customer_id
    country

Orders
    order_id
    customer_id
    order_date

orders_datails
    order_id
    product_id
    quantity
    unit_price

products
    product_id
    description

6. Estructura tabla Machine Learning

| customer_id | recency | frequency | monetary | avg_order | products | churn |
| ----------- | ------: | --------: | -------: | --------: | -------: | ----: |
| 123         |      15 |        24 |     2450 |       102 |       18 |     0 |
| 456         |     180 |         3 |      120 |        40 |        5 |     1 |
| 789         |      32 |        12 |      850 |        71 |        9 |     0 |


7. Estructura Proyecto

DATOS TRANSACCIONALES
        │
        ▼
     SQL / BBDD
        │
        ▼
   LIMPIEZA DATOS
        │
        ▼
 FEATURE ENGINEERING
        │
        ├───────────────┐
        ▼               ▼
 SEGMENTACIÓN        CHURN
        │               │
     CLUSTERING      ML
                        │
                        ▼
                  INTERPRETACIÓN
                        │
                        ▼
                DECISIÓN EMPRESARIAL