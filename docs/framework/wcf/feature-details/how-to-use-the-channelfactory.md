---
title: "Практическое руководство. Использование ChannelFactory | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Практическое руководство. Использование ChannelFactory
Универсальный класс <xref:System.ServiceModel.ChannelFactory%601> используется в сложных сценариях, требующих создания фабрики каналов, которая может использоваться для создания нескольких каналов.  
  
### Создание и использование класса ChannelFactory  
  
1.  Создайте и запустите службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Настройка служб](../../../../docs/framework/wcf/configuring-services.md) и [Размещение служб](../../../../docs/framework/wcf/hosting-services.md).  
  
2.  С помощью [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) создайте контракт \(интерфейс\) для клиента.  
  
3.  В коде клиента для создания нескольких прослушивателей конечной точки используйте класс <xref:System.ServiceModel.ChannelFactory%601>.  
  
## Пример  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]