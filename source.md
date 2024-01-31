---
title-prefix: WebAuthn
title: Passwordless Innovation for <br> Blockchain Security and User Experience
author: andy@kadena.io
date: January 31, 2024
background: assets/images/bg.png # image background; used if video is not present or slide_bg_is_video is not true
logosig: assets/icons/k-logo-icon-alpha.png # "signature" logo at bottom right of each slide. to disable this, set to a 1x1 transparent png
icons: # icon sources for title slide
  - assets/icons/k-logo-icon.jpg
video: # video for background. multiple formats are supported
  - src: assets/videos/kd-back.mp4
    type: video/mp4
video_playback_rate: 0.5 # slow down the video
slide_bg_is_video: true # true to use a darkened version of the video as slide background
---

# Password

:::::::::::::: {.columns}
::: {.column width="30%"}

- Forgotten
- Leaked
- Fatigue

:::
::: {.column width="70%"}
![](./assets/images/forgot-password.jpg)
:::
::::::::::::::

# Password exposure

:::::::::::::: {.columns}
::: {.column width="30%"}

- Entering password
- Sending password
- Storing password

:::
::: {.column width="70%"}
![](./assets/images/phishing.jpg)
:::
::::::::::::::

# Asymmetric signing

```{.mermaid width=100% format=svg theme=dark background=transparent}
flowchart LR
  M(message)
  PrK((private key))
  S(signature)
  M --> PrK --> S
```

```{.mermaid width=100% format=svg theme=dark background=transparent}
flowchart LR
  M(message)
  S(signature)
  PubK((public key))
  I{verified}
  M --> PubK
  S --> PubK
  PubK --> I
```

# Asymmetric signing exposure

```{.mermaid width=100% format=svg theme=dark background=transparent}
flowchart LR

subgraph Website
  direction TB
  a(Password Form)
  c(KeyStore)
end

subgraph Server
  b(Public Key)
end

a --Unlock Keystore--> c
c --Signs message--> a
Server --Sign this message--> Website
Website --Sends signature--> Server
```

# WebAuthn

```{.mermaid width=100% format=svg theme=dark background=transparent}
flowchart LR

subgraph Client
  direction TB
  subgraph SE/TEE
    c(KeyStore)
  end

  subgraph Website
  end
end

subgraph Server
  b(Public Key)
end

c --Signs message--> c
Website --Sign this message--> SE/TEE
SE/TEE --Sends signature--> Website
Server --Sign this message--> Website
Website --Sends signature--> Server
```

# WebAuthn

:::::::::::::: {.columns}
::: {.column width="50%"}

- Secure Enclave/Trusted Execution Environment
- No more forgotten passwords
- No more passwords leaked
- Easy to access

Lost or broken device?

:::
::: {.column width="50%"}
![](./assets/images/broken-phone.png)
:::
::::::::::::::

# Passkeys

:::::::::::::: {.columns}
::: {.column width="50%"}

- Extention on top of WebAuthn
- Defaults to Google/iCloud
- Allows 3rd party storage

:::
::: {.column width="50%"}
![](./assets/images/passkeys-hero.jpg)
:::
::::::::::::::

# Register Demo

:::::::::::::: {.columns}
::: {.column width="50%"}

Register now and get a 10 KDA welcome bonus!

:::
::: {.column width="50%"}
![](./assets/images/register.svg)
:::
::::::::::::::

#

![](./assets/videos/web-auth-n.mp4){style="object-fit: contain; position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; z-index: 0;" autoplay="autoplay"}

# Webshop Demo

:::::::::::::: {.columns}
::: {.column width="50%"}

Order your cookie now with WebAuthn!

:::
::: {.column width="50%"}
![](./assets/images/webshop.svg)
:::
::::::::::::::

# Thank you

Andy Tang
@andortang
