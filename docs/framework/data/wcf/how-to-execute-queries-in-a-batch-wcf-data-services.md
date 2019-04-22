---
title: Практическое руководство. Выполнение запросов в пакете (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: e5cd44ee7c3b2c2744e87ebf66973b637961893c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517581"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Практическое руководство. Выполнение запросов в пакете (службы данных WCF)
С помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] клиентской библиотеки, чтобы выполнить несколько запросов к службе данных в одном пакете. Дополнительные сведения см. в разделе [пакетной обработки операций](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются при завершении [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует вызов метода <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> для выполнения массива объектов <xref:System.Data.Services.Client.DataServiceRequest%601>, содержащих запросы, которые возвращают как объекты `Customers`, так и объекты `Products` из службы данных Northwind. Коллекция объектов <xref:System.Data.Services.Client.QueryOperationResponse%601> в возвращенном объекте <xref:System.Data.Services.Client.DataServiceResponse> перечисляется, также перечисляется и коллекция объектов, содержащаяся в каждом объекте <xref:System.Data.Services.Client.QueryOperationResponse%601>.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
