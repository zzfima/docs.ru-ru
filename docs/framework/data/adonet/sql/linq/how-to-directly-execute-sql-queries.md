---
title: Как выполнить прямо выполнять запросы SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 1caf81df5998e5aaef4ad011a399d70aff43ca9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634462"
---
# <a name="how-to-directly-execute-sql-queries"></a>Как выполнить прямо выполнять запросы SQL
Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в параметризованные запросы SQL (в текстовой форме) и отправляет их на сервер SQL для обработки.  
  
 В SQL не может выполняться все разнообразие методов, локально доступных приложению. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] пытается преобразовать эти локальные методы в равноценные операторы и функции среды SQL. Для большинства методов и операторов, основанных на встроенных типах [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], предусмотрены непосредственные преобразования в команды SQL. Некоторые методы и операторы можно создать из доступных функций, а те, которые не могут быть преобразованы, вызывают исключения во время выполнения. Дополнительные сведения см. в разделе [сопоставления типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 В тех случаях, когда запроса [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] недостаточно для выполнения специализированной задачи, можно использовать метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> для выполнения запроса SQL и последующего преобразования результата запроса непосредственно в объекты.  
  
## <a name="example"></a>Пример  
 В следующем примере предполагается, что данные для класса `Customer` распределены по двум таблицам (customer1 и customer2). Запрос возвращает последовательность объектов `Customer`.  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 До тех пор, пока имена столбцов в табличных результатах соответствуют свойствам столбцов класса сущностей, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объекты вне запроса SQL.  
  
## <a name="example"></a>Пример  
 Метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> также допускает использование параметров. Для выполнения параметризованного запроса используется код, аналогичный представленному ниже.  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 Параметры записываются в тексте запроса с помощью той же нотации с фигурными скобками, которая используется в методах `Console.WriteLine()` и `String.Format()`. На самом деле `String.Format()` фактически вызывается в строке запроса, вы предоставляете, заменив фигурные скобки параметры на созданные имена параметров, таких как @p0, @p1 ..., @p(n).  
  
## <a name="see-also"></a>См. также
- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Запрос к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
