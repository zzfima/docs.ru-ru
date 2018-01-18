---
title: "Практическое руководство. Возврат наборов строк"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c2a11ae83be1c7f75c5bc440c5f8162877106b07
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-return-rowsets"></a>Практическое руководство. Возврат наборов строк
В данном примере показано возвращение набора строк из базы данных и включение входного параметра в результаты фильтрации.  
  
 При выполнении хранимой процедуры, возвращающей набор строк, используйте *результат* класс, который хранит возвращает из хранимой процедуры. Дополнительные сведения см. в разделе [анализ кода LINQ to SQL источника](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).  
  
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
 [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
