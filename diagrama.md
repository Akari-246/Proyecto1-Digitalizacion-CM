# Diagrama Mermaid
Diagrama de la estructura de la empresa. Separa el entorno **OT** (planta) del entorno **IT** (negocio) y muestra dónde actúa la inteligencia artificial.

```mermaid
flowchart TB
    subgraph OT[ENTORNO OT - PLANTA]
        A["Sensores IoT (temperatura, humedad, presión)"]
        B[Máquinas de fabricación]
        C[Sistema de visión artificial]
        D[IA: Control de calidad]
        E[IA: Mantenimiento predictivo]
        F[Envasado y etiquetado]
        A --> B
        B --> C
        C --> D
        A --> E
        D --> F
        E --> B
    end

    subgraph IT[ENTORNO IT - NEGOCIO]
        G[ERP inteligente]
        H[IA: Previsión de demanda]
        I[Gestión de inventarios]
        J[Distribución y pedidos]
        K[Dirección empresarial]
        G --> I
        H --> G
        I --> J
        J --> K
    end
    F -->|Datos de producción| G
    K -->|Planificación| B

    classDef ot fill:#e0e7ff,stroke:#818cf8,stroke-width:1.5px,color:#312e81
    classDef it fill:#f3e8ff,stroke:#c084fc,stroke-width:1.5px,color:#581c87
    classDef ai fill:#fbcfe8,stroke:#db2777,stroke-width:2px,color:#831843
    class A,B,C,F ot
    class G,I,J,K it
    class D,E,H ai

    style OT fill:#f5f7ff,stroke:#a5b4fc,stroke-width:1.5px,color:#3730a3
    style IT fill:#fbf7ff,stroke:#d8b4fe,stroke-width:1.5px,color:#6b21a8
    linkStyle default stroke:#5b5675,stroke-width:1.5px
```

**Leyenda de colores**
- Azul: elementos de planta (OT).
- Lila: elementos de negocio (IT).
- Rosa: componentes de IA.
<br>

> Si el diagrama no se renderiza, consulta la imagen.
![Diagrama IT/OT](imagenes/diagrama.png)

---

## Relación entre IT y OT

El diagrama se organiza en dos entornos conectados por dos flujos:

- **De OT a IT: datos de producción.** Desde *Envasado y etiquetado*, la planta envía al *ERP inteligente* la información real de lo que se ha fabricado. Así, el negocio trabaja con datos actualizados.
- **De IT a OT: planificación.** Desde *Dirección empresarial*, las decisiones y los planes de producción vuelven a *Máquinas de fabricación*, que ajustan su actividad a lo que el negocio necesita.

Esta conexión es lo que permite la digitalización: la planta y el negocio dejan de funcionar como sistemas aislados.

## Dónde actúa la IA

| Entorno | Componente de IA | Qué aporta |
|---|---|---|
| OT | Control de calidad | Analiza las imágenes del sistema de visión artificial y detecta defectos antes del envasado. |
| OT | Mantenimiento predictivo | Usa los datos de los sensores IoT para anticipar averías en las máquinas y evitar paradas. |
| IT | Previsión de demanda | Alimenta al ERP con estimaciones de ventas, de modo que la planificación y los inventarios se ajusten a la demanda real. |

## Impacto organizacional

- **En planta:** los sensores y la visión artificial generan datos de forma continua. La IA convierte esos datos en decisiones: rechazar un producto defectuoso o programar una intervención en una máquina.
- **En negocio:** el ERP centraliza la información de producción, la gestión de inventarios y la distribución. La previsión de demanda reduce el exceso o la falta de stock.
- **En la organización:** la planificación deja de ser un proceso aislado de dirección y pasa a basarse en datos reales de planta, con un ciclo continuo de información entre ambos entornos.