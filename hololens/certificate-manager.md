---
title: Gestor de Certificados
description: Aprenda a instalar, gerir e remover manualmente certificados em HoloLens 2 dispositivos de realidade mista.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b1869e786e3f3324494cecbfd596f61811e1893
ms.sourcegitcommit: 78e5f26014e55c13fee9c2b75a80810fd2e77877
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/31/2021
ms.locfileid: "115009328"
---
# <a name="certificate-manager"></a>Gestor de Certificados

- Melhoria da auditoria, diagnóstico e validação da segurança do dispositivo e cumprimento através do novo Gestor de Certificados. Esta capacidade permitir-lhe-á implantar, resolver problemas e validar os seus certificados em escala em ambientes comerciais.

Na Windows Holographic, versão 20H2, estamos a adicionar um Certificate Manager na aplicação HoloLens 2 Definições. Aceda aos **certificados de > de segurança & Definições > de Definições >.** Esta funcionalidade fornece uma forma simples e fácil de visualizar, instalar e remover certificados no seu dispositivo. Com o novo Gestor de Certificados, os administradores e utilizadores têm agora uma ferramenta melhorada de auditoria, diagnóstico e validação para garantir que os dispositivos se mantenham seguros e conformes. 

-   **Auditoria:** Capacidade de validar que um certificado é implantado corretamente ou de confirmar que foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, validar que os certificados adequados existem no dispositivo poupa tempo e ajuda na resolução de problemas. 
-   **Validação:** Verificar se um certificado serve o fim pretendido e é funcional, pode economizar tempo significativo, particularmente em ambientes comerciais antes de implantar certificados em maior escala.

Para encontrar rapidamente um certificado específico na lista, existem opções para classificar pelo nome, loja ou data de validade. Os utilizadores também podem procurar diretamente um certificado. Para ver as propriedades individuais do certificado, selecione o certificado e clique em **Informação**. 

A instalação do certificado suporta atualmente ficheiros .cer e .crt. Os Proprietários de Dispositivos podem instalar certificados na Máquina Local e no Utilizador Atual;  todos os outros utilizadores só podem instalar-se no Utilizador Atual.

## <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Ligação o seu HoloLens 2 para um PC.
1.  Coloque o ficheiro de certificado que pretende instalar num local na sua HoloLens 2.
1.  Navegue para **Definições App > Atualizar & Certificados de segurança >** e selecione Instalar um certificado.
1.  Clique em **'Importar' e** navegue para o local onde guardou o certificado.
1.  Selecione **a localização da loja**.
1.  Selecione **Certificate Store**.
1.  Clique em **Install** (Instalar).

O certificado deve agora ser instalado no aparelho.

![Espectador de certificado na aplicação Definições ao abrigo de Certificados.](images/certificate-viewer-device.jpg)

![Imagem que mostra como usar o Certificado UI para instalar um certificado em Definições.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Para remover um certificado:

> [!WARNING]
> Utilizando o Certificate Manager, os utilizadores só podem remover certificados instalados diretamente da UI Definições. Se um certificado tiver sido instalado através de outros meios, deve também ser removido pelo mesmo mecanismo e não pode ser removido do Gestor de Certificados. Embora possa ver certificados implantados pelo MDM no Certificate Manager, não pode desinstalá-los no Certificate Manager. Deve desinstalá-los através do MDM.

1. Navegue para **Definições App > atualização e certificados de > de segurança.**
1. Procure o certificado pelo nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique **em Remover**
1. Selecione **Sim** quando solicitado para confirmação.

