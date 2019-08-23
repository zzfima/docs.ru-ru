---
title: Практическое руководство. Выполнение запросов асинхронной службы данных (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: b5530dea50a6fab8478639def9624f8715ae3f3e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952396"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Практическое руководство. Выполнение запросов асинхронной службы данных (WCF Data Services)
При использовании клиентской библиотеки служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] операции «клиент-сервер», например выполнение запросов и сохранение изменений, можно выполнять асинхронно. Дополнительные сведения см. в разделе [асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
> В приложении, в котором метод обратного вызова должен быть вызван из определенного потока, необходимо выполнить явный маршалинг выполнения метода <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>. Дополнительные сведения см. в разделе [асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует выполнение асинхронного запроса путем вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> для запуска запроса. Встроенный делегат вызывает метод <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> для отображения результатов запроса.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
