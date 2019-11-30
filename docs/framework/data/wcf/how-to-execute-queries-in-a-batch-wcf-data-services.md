---
title: Практическое руководство. Пакетное выполнение запросов (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: 0ddf5b4f68ca08fca0c55cfcdfcd5431bcec6de2
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569057"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Практическое руководство. Пакетное выполнение запросов (службы данных WCF)
С помощью клиентской библиотеки WCF Data Services можно выполнять более одного запроса к службе данных в одном пакете. Дополнительные сведения см. в разделе [операции пакетной обработки](batching-operations-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует вызов метода <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> для выполнения массива объектов <xref:System.Data.Services.Client.DataServiceRequest%601>, содержащих запросы, которые возвращают как объекты `Customers`, так и объекты `Products` из службы данных Northwind. Коллекция объектов <xref:System.Data.Services.Client.QueryOperationResponse%601> в возвращенном объекте <xref:System.Data.Services.Client.DataServiceResponse> перечисляется, также перечисляется и коллекция объектов, содержащаяся в каждом объекте <xref:System.Data.Services.Client.QueryOperationResponse%601>.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>См. также:

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
