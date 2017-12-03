---
title: "Практическое руководство. Пакетное выполнение запросов (службы данных WCF)"
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
helpviewer_keywords: WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 384274b127e04004117cbb2f6d5f7764c3212d0b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Практическое руководство. Пакетное выполнение запросов (службы данных WCF)
С помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] клиентской библиотеки можно выполнить несколько запросов к службе данных в одном пакете. Дополнительные сведения см. в разделе [операциями пакетной обработки](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются после выполнения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует вызов метода <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> для выполнения массива объектов <xref:System.Data.Services.Client.DataServiceRequest%601>, содержащих запросы, которые возвращают как объекты `Customers`, так и объекты `Products` из службы данных Northwind. Коллекция объектов <xref:System.Data.Services.Client.QueryOperationResponse%601> в возвращенном объекте <xref:System.Data.Services.Client.DataServiceResponse> перечисляется, также перечисляется и коллекция объектов, содержащаяся в каждом объекте <xref:System.Data.Services.Client.QueryOperationResponse%601>.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>См. также  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
