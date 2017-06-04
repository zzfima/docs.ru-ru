---
title: "Привязки WS-MetadataExchange | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Привязки WS-MetadataExchange
В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.  
  
## Привязки по умолчанию  
  
|Имя привязки по умолчанию|Создание привязки|  
|-------------------------------|-----------------------|  
|MexHttpBinding|Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.|  
|MexHttpsBinding|Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.|  
|MexNamedPipeBinding|Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.|  
|MexTcpBinding|Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.|