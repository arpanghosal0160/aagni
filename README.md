
graph LR
    A[Physical Server] -- P2V Conversion Process --> B(Virtual Machine)

    subgraph Standard VM Lifecycle in CCE
        direction LR
        B -- Power On / Run --> C{Manage & Maintain}
        C -- Monitoring, Patching, Backup --> C
        C -- Needs Retirement --> D[Retire / Decommission]
        D -- Shutdown, Archive, Delete --> E[(End State)]
    end

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ccf,stroke:#333,stroke-width:2px

    %% Add a floating note (mermaid doesn't support notes perfectly, this is a workaround)
    A -.-> F["Note: P2V acts as an entry point,<br>effectively creating the VM<br>based on the physical system."]
    style F fill:#fff,stroke:#999,stroke-dasharray: 5 5
