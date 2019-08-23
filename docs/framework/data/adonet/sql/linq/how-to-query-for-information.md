---
title: Практическое руководство. Как обращаться с запросами о сведениях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 2987e43c83bf84e32cd05a870b24da40dd37d8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943559"
---
# <a name="how-to-query-for-information"></a>Практическое руководство. Как обращаться с запросами о сведениях
Для запросов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] используется тот же синтаксис, что и для запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. Единственное отличие заключается в том, что объекты, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] на которые имеются ссылки в запросах, сопоставляются с элементами в базе данных. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки.  
  
 Некоторым запросам [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], возможно, требуется уделить особое внимание в приложениях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Дополнительные сведения см. в разделе [Основные понятия запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).  
  
## <a name="example"></a>Пример  
 Следующий запрос возвращает список клиентов из Лондона. В этом примере используется таблица `Customers` из учебной базы данных "Northwind".  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Запрос к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
