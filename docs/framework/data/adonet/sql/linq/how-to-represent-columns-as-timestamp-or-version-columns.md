---
title: "Как представить столбцы как столбцы отметки времени или версии | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как представить столбцы как столбцы отметки времени или версии
Чтобы назначить свойство или поле, представляющее столбец базы данных, хранящий метки времени или номера версий базы данных, используется свойство [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> атрибута <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### Назначение поля или свойства, представляющего столбец версии или отметки времени  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
2.  Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> значение `true`.  
  
## См. также  
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Как указать, для каких элементов тестируется возникновение конфликтов параллелизма](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)   
 [Как настроить классы сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)