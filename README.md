# DBT-Code-Challenge
DBT usado para un challenge de DBT para la empresa Pipol

En esta tabla buscamos info de 4 CSV, lo consolidamos con los datos necesarios para análisis, agregar la columna de segmento para calcular costos, le normalizamos los canales y si, es necesario, se pueden cambiar los nombres de las marcas para análisis.

También tiene un listado de marcas excluidas modificable, que se utiliza para filtrar si hay falsos positivos y eliminarlos de la tabla consolidada final y no queden en los registros.

En caso de que se necesite agregar nuevos registros, utilizar el primer código y agregar nuevas tablas a la lista de UNION ALL

```mermaid
graph TD
    %% Estilos de las cajas
    classDef source fill:#f9f9f9,stroke:#333,stroke-width:1px,stroke-dasharray: 5 5;
    classDef process fill:#e1f5fe,stroke:#0288d1,stroke-width:2px;
    classDef output fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px;

    %% Nodos
    A[Fuentes de Origen<br>Brasil & México]:::source
    B(Consolidación1):::process
    C(Normalización):::process
    D(MarcasExcluidas):::process
    E(CanalesDistintos):::process
    F(MarcasDistintas):::process
    G[ArmadoFinal<br>Output Limpio]:::output

    %% Conexiones/Flujo
    A --> B
    B --> C
    C --> D
    D --> E
    D --> F
    F --> G

    %% Ajuste de diseño personalizado
    style A color:#333
    style G color:#1b5e20,font-weight:bold
