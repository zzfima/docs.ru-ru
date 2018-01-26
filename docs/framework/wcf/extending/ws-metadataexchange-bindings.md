---
title: "Привязки WS-MetadataExchange"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d305f3bf34b3b14da566fa792552e24e695ef33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ws-metadataexchange-bindings"></a>Привязки WS-MetadataExchange
В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.  
  
## <a name="the-default-bindings"></a>Привязки по умолчанию  
  
|Имя привязки по умолчанию|Создание привязки|  
|--------------------------|------------------------------------|  
|MexHttpBinding|Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.|  
|MexHttpsBinding|Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.|  
|MexNamedPipeBinding|Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.|  
|MexTcpBinding|Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.|
