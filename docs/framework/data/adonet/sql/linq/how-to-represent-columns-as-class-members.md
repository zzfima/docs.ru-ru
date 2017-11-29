---
title: "Практическое руководство. Представление столбцов как членов класса"
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
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f0e797886b5e2fedafccf08b71e8cbb2791ea72b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-class-members"></a>Практическое руководство. Представление столбцов как членов класса
Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> для связи поля или свойства со столбцом базы данных.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>Сопоставление поля или свойства со столбцом база данных  
  
-   Добавьте атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute> в объявление свойства или поля.  
  
## <a name="example"></a>Пример  
 В следующем коде поле `CustomerID` в классе `Customer` сопоставляется со столбцом `CustomerID` в таблице базы данных `Customers`.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 Если можно определить имя, указывать свойство <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> нет необходимости. Если имя не указано, оно будет считаться совпадающим с именем свойства или поля.  
  
## <a name="see-also"></a>См. также  
 [LINQ to SQL модель объектов](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Как: Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
