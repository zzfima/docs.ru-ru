---
title: Практическое руководство. Как возвращать наборы строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: 5ec188e0345140297062d0a10dfbbc4a294bbb7d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781606"
---
# <a name="how-to-return-rowsets"></a>Практическое руководство. Как возвращать наборы строк
В данном примере показано возвращение набора строк из базы данных и включение входного параметра в результаты фильтрации.  
  
 При выполнении хранимой процедуры, возвращающей набор строк, используется *результирующий* класс, хранящий возвращаемые результаты из хранимой процедуры. Дополнительные сведения см. в разделе [анализ исходного кода LINQ to SQL](analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Пример  
 В следующем примере представлена хранимая процедура, которая возвращает строки клиентов и использует входной параметр для возврата только тех строк, в которых "Лондон" указан как город клиентов. В примере предполагается использование перечислимого класса `CustomersByCityResult`.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Хранимые процедуры](stored-procedures.md)
- [Загрузка примеров баз данных](downloading-sample-databases.md)
