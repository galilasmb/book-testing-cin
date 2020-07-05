---
title: Página Inicial
subtitle: Descrição da página inicial
layout: page
show_sidebar: true
youtubeId: dhh9zcA6Xwk
driveId: 1XejOcnSVg5KWxweoe-TXaDol-dqTeHTE
formsId: 1FAIpQLScPE3QyL3DsoXuOgY-uaVBEMQjZ1Seuckubarbi1JTIRygtWw
---

# Para inserir um vídeo do Youtube

```
Para incluir um vídeo do Youtube, procure pelo seu ID!
Exemplo:     youtubeId: dhh9zcA6Xwk
Insira o comando abaixo dentro das chaves:{ % Aqui %}
     include youtubePlayer.html id=page.youtubeId
```

{% include youtubePlayer.html id=page.youtubeId %}


# Para inserir um vídeo do Google Drive

```
Para incluir um vídeo do Google Drive, procure pelo ID no youtube!
Exemplo:     driveId: dhh9zcA6Xwk
Insira o comando abaixo dentro das chaves:{ % Aqui %}
    include googleDrivePlayer.html id=page.driveId
```

{% include googleDrivePlayer.html id=page.driveId %}

# Para inserrir um Google Formulário

```
Para incluir um vídeo do Google Drive, procure pelo ID no youtube!
Exemplo:     formsId: 1FAIpQLScPE3QyL3DsoXuOgY-uaVBEMQjZ1Seuckubarbi1JTIRygtWw
Insira o comando abaixo dentro das chaves:{ % Aqui %}
    include forms.html id=page.formsId
```

{% include forms.html id=page.formsId %}