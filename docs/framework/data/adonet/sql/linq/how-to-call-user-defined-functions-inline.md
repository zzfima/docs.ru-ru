---
title: Практическое руководство. Как вызывать встроенные определяемые пользователем функции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 01ba9ab4359cbd124b2207c87d5dae904641911a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002987"
---
# <a name="how-to-call-user-defined-functions-inline"></a>Практическое руководство. Как вызывать встроенные определяемые пользователем функции
Пользовательские функции можно вызывать из строки кода, однако функции, включенные в запрос, выполнение которого отложено, выполняются только одновременно с запросом. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Если та же функция вызывается за пределами запроса, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает простой запрос из выражения вызова метода. Ниже показан синтаксис SQL (параметр `@p0` привязан к передаваемой константе).  
  
```sql  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает следующий код:  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a>Пример  
 В следующем [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запросе можно увидеть встроенный вызов созданного определяемого пользователем метода функции `ReverseCustName`. Функция не выполняется немедленно, поскольку выполнение запроса отложено. Код SQL, созданный для этого запроса, преобразуется в вызов пользовательской функции в базе данных (см. код SQL, расположенный после запроса).  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```sql  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a>См. также

- [Определяемые пользователем функции](user-defined-functions.md)
