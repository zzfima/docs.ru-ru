---
title: "Как представить столбцы как сформированные базой данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как представить столбцы как сформированные базой данных
Чтобы назначить свойство или поле, представляющие столбец, созданный базой данных, используется свойство [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> атрибута <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
### Назначение поля или свойства, представляющего столбец, созданный базой данных  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
2.  В качестве значения свойства задайте `true`.  
  
## См. также  
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Как настроить классы сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)