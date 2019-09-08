---
title: Начало работы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: bd82b7e83149aaa53cf1b240cb79f8747bccba47
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793912"
---
# <a name="getting-started"></a>Начало работы
С помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]можно [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] использовать технологию для доступа к базам данных SQL так же, как и к коллекции в памяти.  
  
 В следующем примере кода создается объект `nw` для представления базы данных `Northwind`, выполняется запрос к таблице `Customers`, фильтруются строки для поиска клиентов (`Customers`) из Лондона (`London`) и выбирается строка `CompanyName` для извлечения.  
  
 При выполнении цикла извлекается коллекция значений `CompanyName`.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>Следующие шаги  
 Дополнительные примеры, включая вставку и обновление, см. [в разделе что можно делать с LINQ to SQL](what-you-can-do-with-linq-to-sql.md).  
  
 Далее ознакомьтесь с некоторыми пошаговыми руководствами и учебниками, чтобы получить практический навык работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. См. раздел [обучение по пошаговым руководствам](learning-by-walkthroughs.md).  
  
 Наконец, Узнайте, как приступить к работе над [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] собственным проектом, прочитав [типичные шаги для использования LINQ to SQL](typical-steps-for-using-linq-to-sql.md).  
  
## <a name="see-also"></a>См. также

- [LINQ to SQL](index.md)
- [Введение в LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Знакомство с LINQ (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
