# TEST
sourcetree软件测试
%%{init: {'theme': 'neutral', 'themeVariables': { 'primaryColor': '#F3F4F6'}}}%%
flowchart TD
    A[1. 菌群样本采集与预处理] --> B[临床队列]
    B --> C[样本采集]
    C -->|胆结石患者(n=30)| D[粪便冻存]
    C -->|健康对照(n=30)| D
    D --> E[菌群分析]
    E --> E1["16S rRNA测序<br>（α/β多样性、差异菌属）"]
    E --> E2["宏基因组测序<br>（KEGG功能注释→胆汁酸代谢基因筛选）"]

    F[2. 人源菌群-C57BL/6小鼠模型] --> G[模型构建]
    G --> G1["实验组：患者菌群悬液(n=20)"]
    G --> G2["对照组：健康菌群悬液(n=20)"]
    G --> G3["空白组：PBS(n=10)"]
    G --> H[定植验证]
    H --> H1["qPCR检测7α-脱羟酶基因"]
    H --> H2["16S时序分析"]
    H --> I[功能验证]
    I --> I1["宏基因组分析（胆汁酸代谢基因丰度）"]
    I --> I2["LC-MS/MS定量DCA/LCA"]

    J[3. 宿主代谢与病理表型分析] --> K[代谢物检测]
    K --> K1["胆汁分析：HPLC(CSI)+LC-MS/MS(DCA/CA)"]
    K --> K2["血清/肝脏：UPLC-QTOF-MS(脂质/SCFAs)"]
    K --> K3["qRT-PCR：HMGCR/CYP7A1/ABCG5/G8"]
    J --> L[病理评估]
    L --> L1["胆囊结石率+CMC偏振光分析"]
    L --> L2["HE染色（中性粒细胞评分）"]
    L --> L3["MUC5AC免疫组化"]
    L --> L4["ELISA：LPS/IL-6/TNF-α"]
    L --> L5["肠道屏障免疫荧光(ZO-1/Occludin)"]

    M[4. 多组学整合机制解析] --> N[宏基因组-代谢组关联]
    N --> N1["KEGG通路富集分析"]
    N --> N2["Spearman网络(|r|>0.6)"]
    M --> O[单细胞转录组]
    O --> O1["10x Genomics建库"]
    O --> O2["UMAP分群(EpCAM+/CD45+)"]
    O --> O3["差异通路：MUC5AC分泌、NF-κB炎症、PPARγ脂代谢"]
    M --> P[跨组学整合]
    P --> P1["代谢物-受体互作验证<br>（DCA-FXR/TGR5信号轴）"]

    Q[5. 关键菌株与代谢物验证] --> R[致病菌验证]
    R --> R1["Clostridium scindens定植→DCA生成↑"]
    R --> R2["结石发生率↑"]
    R --> R3["DCA回补→IL-6↑/CMC形成↑"]
    Q --> S[益生菌干预]
    S --> S1["Faecalibacterium灌胃→CSI↓"]
    S --> S2["结石抑制"]

    %% 阶段间连接
    A --> F
    F --> J
    J --> M
    M --> Q

    classDef phase fill:#E8F4FD,stroke:#4A90E2;
    classDef analysis fill:#E6F9E6,stroke:#50B83C;
    classDef animal fill:#FCE8E6,stroke:#DE3618;
    class A,F,J,M,Q phase;
    class E1,E2,N,O,P analysis;
    class G1,G2,G3,H,I animal;
