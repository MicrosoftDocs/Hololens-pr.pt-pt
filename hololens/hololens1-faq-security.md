---
title: Perguntas frequentes de segurança
description: Mantenha-se atualizado com perguntas de segurança e respostas sobre hololelens dispositivos de realidade mista.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Realidade Mista de Janelas, segurança
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378680"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Frequentemente perguntou HoloLens (1ª gen) Questões de Segurança

1. **Que nível de proteção de dados os HoloLens 1 oferecem?**
    1. Ver [HoloLens (1ª Gen) BitLocker Encryption](hololens1-encryption.md)
1. **Que tipo de sem fios é usado?**
    1. 802.11ac e Bluetooth 4.1 LE
1. **Que tipo de arquitetura é incorporada?  Por exemplo: ponto a ponto, malha, ou outra coisa?**
    1. Wi-Fi podem ser usados em modo de infraestrutura para comunicar com outros pontos de acesso sem fios.
    1. O Bluetooth pode ser utilizado para falar entre vários HoloLens se a aplicação dos clientes o suportar ou a outros dispositivos Bluetooth.
1. **O que é a ID da FCC?**
    1. C3K1688
1. **Que gama de frequências e canais o dispositivo funciona e é configurável?**
    1. Wi-Fi: A gama de frequências não é configurável pelo utilizador e depende do país de utilização. Nos EUA, o Wi-Fi utiliza canais de 2,4 GHz (1-11) e 5 GHz (36-64, 100-165).
    1. Bluetooth: Bluetooth utiliza a gama padrão 2.4-2.48 GHz.
1. **O dispositivo pode permitir ou bloquear frequências específicas?**
    1. Isto não é controlável pelo utilizador/dispositivo.
1. **Qual é o nível de potência para transmitir e receber? É ajustável? Qual é o alcance de operação?**
    1. Os nossos padrões de teste de emissões podem ser [encontrados aqui.](https://fccid.io/C3K1688) A gama de operações é altamente dependente do ponto de acesso e do ambiente - mas é aproximadamente equivalente a outros telefones, tablets ou Computadores de alta qualidade.
1. **Qual é o ciclo de serviço/vida útil para o funcionamento normal?**
    1. 2-3 horas de uso ativo e até duas semanas de tempo de espera
    1. A duração da bateria não está disponível.
1. **O que é transmitir e receber comportamento quando uma ferramenta não está ao alcance?**
    1. HoloLens transmitem/recebem segue o padrão Wi-Fi/Bluetooth. Na borda da sua gama, provavelmente notará a entrada a ficar agitada até que se desconecte completamente, mas depois de voltar ao alcance, deve voltar a ligar-se rapidamente.
1. **O que é densidade de implantação por metro quadrado?**
    1. Isto depende da sua infraestrutura de rede.
1. **O dispositivo pode usar a infraestrutura como cliente?**
    1. Yes
1. **Que protocolo é usado?**
    1. HoloLens não usa nenhum protocolo proprietário
1. **Frequência de atualização do SO – Qual é a frequência das atualizações do SO para o HL?  Há um horário definido?  A Microsoft lança patches de segurança conforme necessário, etc.**
    1. A Microsoft fornece atualizações de SO para HoloLens exatamente da mesma forma que é feito para o Windows 10. Normalmente há duas grandes atualizações por ano, uma na primavera, outra no outono. Como o HoloLens é um dispositivo Windows, o conceito de atualização é o mesmo que qualquer outro dispositivo Windows. A Microsoft lança patches de Segurança conforme necessário e segue o mesmo conceito que o feito em qualquer outro dispositivo Windows.
1. **Endurecimento do SISTEMA – Que opções existem para endurecer o SISTEMA?  Podemos remover ou encerrar aplicações ou serviços desnecessários?**
    1. HoloLens comporta-se como um smartphone. É comparável a outros dispositivos Windows modernos. Os HoloLens podem ser geridos pela Microsoft Intune ou por outras Soluções modernas de gestão de dispositivos, como mobileIron, Airwatch ou Soti. Existem Políticas que pode definir nestes Sistemas de Gestão para colocar políticas de Segurança no dispositivo e para endurecer o dispositivo. Há também a opção de eliminar quaisquer aplicações desnecessárias se quiser.
1. **Como é que as aplicações de software serão geridas e atualizadas? Que controlo temos para definir quais as aplicações carregadas e o processo de atualização de aplicações para apps que estão a viver na loja da Microsoft?**
    1. O HoloLens obtém aplicações de software apenas através da loja Do Windows. Apenas podem ser instalados Pacotes de Aplicações Appx, que são desenvolvidos para uso de HoloLens. Pode ver isto na Microsoft Store com um pequeno logótipo ao lado da aplicação que mostra o dispositivo HoloLens. Qualquer controlo que tenha sobre a gestão das aplicações da Store também se aplica aos HoloLens. Pode utilizar o conceito da loja oficial ou da loja para negócios. As aplicações podem ser side-loaded (processo manual para carregar uma aplicação num dispositivo Windows) ou podem ser geridas através de um MDM para que as aplicações sejam automaticamente retiradas da loja quando necessário.
1. **Qual é a frequência de atualizações para apps na loja para HoloLens?**
    1. À medida que seguimos o mesmo conceito da Microsoft Store e puxamos as aplicações a partir daí, o ciclo de atualização é determinado pelo desenvolvedor da Aplicação. Todas as opções de gestão que você tem que controlar o mecanismo de atualização na loja aplicam-se também aos HoloLens.
1. **Existe uma capacidade de arranque segura para os HoloLens?**
    1. Yes
1. **Existe a capacidade de desativar ou desligar o suporte periférico do dispositivo?**
    1. Yes
1. **Existe a capacidade de controlar ou desativar a utilização de portas no dispositivo?**
    1. Os HoloLens contêm apenas duas portas (uma para auscultadores e outra para carregamento ou ligação a Computadores). Não existe capacidade de desativar a porta devido a razões de funcionalidade e recuperação.
1. **Antivírus, deteção de pontos finais, IPS, lista de controlo de aplicações – Qualquer capacidade de executar antivírus, deteção de pontos finais, IPS, lista de permitis de controlo de aplicações, etc.**
    1. O Windows Holographic for Business (suite comercial) suporta o Windows Defender Smart Screen. Se uma empresa antivírus criar e publicar a sua aplicação para a Plataforma Universal windows, poderia ser descarregada no HoloLens. Atualmente, nenhuma empresa fez isto pela HoloLens.
    1. Permitir aplicações é possível utilizando a Microsoft Enterprise Store, onde só pode escolher quais aplicações específicas podem ser descarregadas. Além disso, através do MDM pode bloquear quais aplicações específicas podem ser executadas ou até mesmo vistas no dispositivo.
1. **Podemos colocar o dispositivo em quarentena a partir da rede de prod até atualizarmos o dispositivo se este estiver desligado por um longo período de tempo?  Ex. O dispositivo está sentado numa gaveta não ligado há um período (seis meses) e não recebeu quaisquer atualizações, patches, etc.  Quando tentar entrar na rede, podemos sinalizá-la e dizer que tem de atualizar outra rede antes de ser reclamada para aderir à rede.**
    1. Isto é algo que pode ser gerido ao nível da infraestrutura por um MDM ou um servidor on-prem. O dispositivo pode ser sinalizado como não conforme se não cumprir uma versão de Atualização especificada.
1. **A Microsoft inclui portas traseiras ou acesso a serviços que permitam à Microsoft ligar-se ao dispositivo para partilha de ecrãs ou suporte remoto à vontade?**
    1. No
1. **Quando um cert PKI está a ser gerado para uma comunicação fidedigna, queremos que o certificado seja gerado no dispositivo para que saibamos que é apenas nesse dispositivo, exclusivo desse dispositivo, e não pode ser exportado ou usado para personificar o dispositivo. Isto é verdade no HoloLens? Se não houver uma potencial atenuação?**
    1. O CSR para SCEP é gerado no próprio dispositivo. Intune e o conector SCEP no local ajudam a garantir os pedidos por si mesmos adicionando e verificando uma cadeia de desafio que é enviada ao cliente.
    1. Uma vez que os HoloLens (1ª Gen e 2ª Gen) têm um módulo TPM, estes certificados seriam armazenados no módulo TPM, e não podem ser extraídos. Além disso, mesmo que pudesse ser extraído, as cordas de desafio não podiam ser verificadas num dispositivo diferente, tornando os certificados/chave inutilizáveis em diferentes dispositivos.
