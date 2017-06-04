---
title: "Как представить вычисляемые столбцы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как представить вычисляемые столбцы
Чтобы представить столбец, содержимым которого является результат вычисления, используется свойство [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> атрибута <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает вычисляемые столбцы в качестве первичных ключей.  
  
### Представление вычисляемого столбца  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
2.  Присвойте атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> строковое представление формулы.  
  
## См. также  
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Как настроить классы сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)