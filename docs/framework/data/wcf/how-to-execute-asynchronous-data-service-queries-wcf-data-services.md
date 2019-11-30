---
title: Практическое руководство. Выполнение асинхронных запросов к службе данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: 68e2035315780b7c6dd60e93ae6eb10d252aabb3
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569071"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Практическое руководство. Выполнение асинхронных запросов к службе данных (службы данных WCF)
С помощью клиентской библиотеки WCF Data Services можно асинхронно выполнять операции типа "клиент-сервер", такие как выполнение запросов и сохранение изменений. Дополнительные сведения см. в разделе [асинхронные операции](asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
> В приложении, в котором метод обратного вызова должен быть вызван из определенного потока, необходимо выполнить явный маршалинг выполнения метода <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>. Дополнительные сведения см. в разделе [асинхронные операции](asynchronous-operations-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует выполнение асинхронного запроса путем вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> для запуска запроса. Встроенный делегат вызывает метод <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> для отображения результатов запроса.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>См. также:

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
