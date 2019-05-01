---
title: Практическое руководство. Использование ChannelFactory
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7d542a3dcae514e75194b49c23a8dec5dd7e8c3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047260"
---
# <a name="how-to-use-the-channelfactory"></a>Практическое руководство. Использование ChannelFactory
Универсальный класс <xref:System.ServiceModel.ChannelFactory%601> используется в сложных сценариях, требующих создания фабрики каналов, которая может использоваться для создания нескольких каналов.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Создание и использование класса ChannelFactory  
  
1. Постройте и запустите службу Windows Communication Foundation (WCF). Дополнительные сведения см. в разделе [проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Настройка служб](../../../../docs/framework/wcf/configuring-services.md), и [размещение служб](../../../../docs/framework/wcf/hosting-services.md).  
  
2. Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контракта (интерфейс) для клиента.  
  
3. В коде клиента для создания нескольких прослушивателей конечной точки используйте класс <xref:System.ServiceModel.ChannelFactory%601>.  
  
## <a name="example"></a>Пример  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
