---
title: Привязки WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
