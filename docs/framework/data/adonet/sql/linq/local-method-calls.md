---
title: Локальные вызовы методов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: 366c174a13e9a1a1928ef943febf199ae8485dfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="local-method-calls"></a>Локальные вызовы методов
Локальным вызовом метода называется вызов, который выполняется в объектной модели. Удаленный вызов метода - это вызов, который [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует в команды SQL и передает в ядро базы данных для выполнения. Локальные вызовы методов необходимы при [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не удается преобразовать вызов в команды SQL. В противном случае <xref:System.InvalidOperationException> возникает исключение.  
  
## <a name="example-1"></a>Пример 1  
 В следующем примере класс `Order` сопоставлен с таблицей "Orders" базы данных "Northwind". К классу добавлен локальный экземпляр метода.  
  
 В запросе 1 конструктор для класса `Order` выполняется локально. В запросе 2, если бы технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] попыталась преобразовать метод `LocalInstanceMethod()`в команды SQL, попытка закончилась бы неудачей и было бы создано исключение <xref:System.InvalidOperationException>. Однако поскольку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обеспечивает поддержку локальных вызовов метода, в запросе 2 не создается исключение.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
