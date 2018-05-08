---
title: Практическое руководство. Добавление, изменение и удаление сущностей (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: a00f8933-b232-4445-95ba-adc634f055d8
ms.openlocfilehash: 4475d8767226a810c7b6f7d8949e9cbe2d846cca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-modify-and-delete-entities-wcf-data-services"></a>Практическое руководство. Добавление, изменение и удаление сущностей (службы данных WCF)
С [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] клиентские библиотеки можно создать, обновить и удаление данных сущности в службе данных путем выполнения эквивалентных действий над объектами в <xref:System.Data.Services.Client.DataServiceContext>. Дополнительные сведения см. в разделе [обновление службы данных](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются после выполнения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 В следующем примере создается новый экземпляр объекта и вызывается метод <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> контекста <xref:System.Data.Services.Client.DataServiceContext> для создания в контексте нового элемента. Сообщение HTTP POST отправляется в службу данных при вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addproduct)]
 [!code-vb[Astoria Northwind Client#AddProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addproduct)]  
  
## <a name="example"></a>Пример  
 Следующий пример извлекает и модифицирует существующий объект, после чего вызывает метод <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> в контексте <xref:System.Data.Services.Client.DataServiceContext>, чтобы пометить элемент контекста как обновленный. Сообщение HTTP MERGE отправляется в службу данных при вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#modifycustomer)]
 [!code-vb[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#modifycustomer)]  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает метод <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> объекта <xref:System.Data.Services.Client.DataServiceContext> для пометки элемента контекста как удаленного. Сообщение HTTP DELETE отправляется в службу данных при вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#deleteproduct)]
 [!code-vb[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#deleteproduct)]  
  
## <a name="example"></a>Пример  
 В следующем примере создается новый экземпляр объекта и вызывается метод <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> контекста <xref:System.Data.Services.Client.DataServiceContext> для создания в контексте нового элемента и ссылки на связанный с ним заказ. Сообщение HTTP POST отправляется в службу данных при вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="see-also"></a>См. также  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Практическое руководство. Присоединение существующей сущности к контексту DataServiceContext](../../../../docs/framework/data/wcf/attach-an-existing-entity-to-dc-wcf-data.md)  
 [Практическое руководство. Определение связей сущностей](../../../../docs/framework/data/wcf/how-to-define-entity-relationships-wcf-data-services.md)  
 [Пакетные операции](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)
