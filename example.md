graph TD
    A[开始] -->|检查 person 是否为 null| B{person == null?}
    B -->|是| C[抛出 NullPointerException]
    B -->|否| D{salary < 0?}
    D -->|是| E[抛出 IllegalArgumentException]
    D -->|否| F[初始化 res = salary - 5000]
    F --> G{children_Num > 0?}
    G -->|是| H[减去子女教育扣除]
    G -->|否| I[继续]
    H --> J{is_KeepStu?}
    I --> J{is_KeepStu?}
    J -->|0| K[继续]
    J -->|1| L[减去继续教育扣除400]
    J -->|2| M[减去继续教育扣除3600]
    L --> N{is_HouseLoans?}
    M --> N{is_HouseLoans?}
    K --> N{is_HouseLoans?}
    N -->|是| O[减去住房贷款利息扣除]
    N -->|否| P[继续]
    O --> Q{is_RentHouse?}
    P --> Q{is_RentHouse?}
    Q -->|0| R[继续]
    Q -->|1| S[减去直辖市租房扣除]
    Q -->|2| T[减去市辖区租房扣除]
    Q -->|3| U[减去其他城市租房扣除]
    S --> V{is_SupportingElderly?}
    T --> V{is_SupportingElderly?}
    U --> V{is_SupportingElderly?}
    R --> V{is_SupportingElderly?}
    V -->|是| W[减去赡养老人扣除]
    V -->|否| X[继续]
    W --> Y[计算税率]
    X --> Y[计算税率]
    Y --> Z[返回计算的税额]
    Z --> AA[结束]
