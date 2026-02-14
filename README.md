# Ejercicio 1 Brayan Daniel Chaclan Hernandez 202308028

Este ejercicio levanta una infraestructura con 3 contenedores Nginx:
- `paginaweb1`: servidor web 1 sirviendo su `index.html`
- `paginaweb2`: servidor web 2 sirviendo su `index.html`
- `conector`: **balanceador de carga**  en el puerto **8080**, que reparte tráfico entre `paginaweb1` y `paginaweb2`

> Proyecto trabajado en la rama: **ejercicio1**  
> Ruta local del proyecto: `/c/Users/herna/prueba1`

---

## Diagrama de la infraestructura

             Cliente / Navegador
                    |
                    |   http://localhost:8080
                    v
        +--------------------------------+
        |          conector (Nginx)      |
        |   Load Balancer (Round Robin)  |
        |           8080 -> 80           |
        +--------------------------------+
               |                 |
               |                 |
               v                 v
                +------------------------+  +------------------------+
               |    paginaweb1 (Nginx)  |  |    paginaweb2 (Nginx)  |
               |        puerto 80       |  |        puerto 80       |
               |  ./paginaweb1/index    |  |  ./paginaweb2/index    |
               +------------------------+  +------------------------+


# URL Balanceador 
- http://localhost:8080

# Prueba de funcionamiento 
<img width="2559" height="948" alt="image" src="https://github.com/user-attachments/assets/0abb27e4-6f79-49a1-88c5-518b45c5671a" />

