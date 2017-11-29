---
title: "Практическое руководство. Представление столбцов как меток времени или столбцов версии"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 88e30b947f18afd4ba93f816d9205c13d32fce82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a>Практическое руководство. Представление столбцов как меток времени или столбцов версии
Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут, чтобы назначить свойство или поле, представляющее столбец базы данных, хранящий номера версии или отметки времени базы данных.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a>Назначение поля или свойства, представляющего столбец версии или отметки времени  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> значение `true`.  
  
## <a name="see-also"></a>См. также  
 [LINQ to SQL модель объектов](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Как: Укажите, какие элементы проверяются на наличие конфликтов параллелизма](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 [Как: Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
