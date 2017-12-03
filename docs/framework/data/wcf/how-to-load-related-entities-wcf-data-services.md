---
title: "Практическое руководство. Загрузка связанных сущностей (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fce222a07ad57820af6165b456fe4e2033900aee
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Практическое руководство. Загрузка связанных сущностей (службы данных WCF)
При необходимости загрузить связанные сущности в службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] можно использовать метод <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> класса <xref:System.Data.Services.Client.DataServiceContext>. Можно также использовать <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> метод <xref:System.Data.Services.Client.DataServiceQuery%601> Чтобы потребовать активной загрузки связанных сущностей в одном ответе на запрос.  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются после выполнения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует явную загрузку сущности `Customer`, связанной с каждым возвращенным экземпляром `Orders`.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует использование метода <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> для возврата сущности `Order Details`, принадлежащей сущности `Orders`, возвращаемой запросом.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>См. также  
 [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
