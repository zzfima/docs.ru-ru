---
title: Начало работы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 506257c13bbaada98dffa9d3a15c834037c1d971
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155237"
---
# <a name="getting-started"></a>Начало работы
С помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], можно использовать [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] технологии для доступа к SQL базы данных, так же, как вы к коллекции в памяти.  
  
 В следующем примере кода создается объект `nw` для представления базы данных `Northwind`, выполняется запрос к таблице `Customers`, фильтруются строки для поиска клиентов (`Customers`) из Лондона (`London`) и выбирается строка `CompanyName` для извлечения.  
  
 При выполнении цикла извлекается коллекция значений `CompanyName`.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>Следующие шаги  
 Дополнительные примеры, включая вставки и обновления, см. в разделе [что вам можно делать с помощью LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).  
  
 Далее ознакомьтесь с некоторыми пошаговыми руководствами и учебниками, чтобы получить практический навык работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. См. в разделе [обучения с использованием пошаговых руководств](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
 Наконец, узнайте, как приступить к разработке собственных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта путем чтения [стандартная последовательность действий с помощью LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).  
  
## <a name="see-also"></a>См. также

- [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [Введение в LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq.md)
- [Знакомство с LINQ (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
