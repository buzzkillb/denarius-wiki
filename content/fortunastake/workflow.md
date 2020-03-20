---
title: "Workflow"
date: 2020-03-04T23:16:51-08:00
---
{{<mermaid align="left">}}
graph LR;
    A[Get 5000 Denarius] -->B(Send to Collateral Address)
    B --> C{Setup Wallets}
    C --> D[PC]
    D --> E(Hot Wallet)
    C --> F[VPS]
    F --> G(Cold Wallet)
{{< /mermaid >}}
#### PC - Hot Wallet
{{<mermaid align="left">}}
graph LR;
    A[Hot Wallet] -->B(fortunastake.conf)
    B --> C[wait 500 confirms]
    C --> D[fortunastake start-alias NAME]
{{< /mermaid >}}
#### VPS - Cold Wallet
{{<mermaid align="left">}}
graph LR;
    A[Cold Wallet] -->B(denarius.conf)
{{< /mermaid >}}
