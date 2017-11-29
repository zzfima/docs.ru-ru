---
title: "Практическое руководство. Использование ChannelFactory"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cd9c7c69ba65fe676e9ea0eba250fc3200e90c51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-the-channelfactory"></a>Практическое руководство. Использование ChannelFactory
Универсальный класс <xref:System.ServiceModel.ChannelFactory%601> используется в сложных сценариях, требующих создания фабрики каналов, которая может использоваться для создания нескольких каналов.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Создание и использование класса ChannelFactory  
  
1.  Создайте и запустите службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Настройка служб](../../../../docs/framework/wcf/configuring-services.md), и [услуг](../../../../docs/framework/wcf/hosting-services.md).  
  
2.  Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контракта для клиента (интерфейс).  
  
3.  В коде клиента для создания нескольких прослушивателей конечной точки используйте класс <xref:System.ServiceModel.ChannelFactory%601>.  
  
## <a name="example"></a>Пример  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
