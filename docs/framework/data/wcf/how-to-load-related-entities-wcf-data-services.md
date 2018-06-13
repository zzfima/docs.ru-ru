---
title: Практическое руководство. Загрузка связанных сущностей (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: f7aa13ac217d86be23d0957ddb6c069831cacd2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358167"
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
