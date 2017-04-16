---
title: "Как задавать типы данных базы данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как задавать типы данных базы данных
Для задания точного текста, определяющего столбец в объявлении таблицы на языке T\-SQL, используется свойство [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> в <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
 Свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> следует задавать, только если для создания экземпляра базы данных планируется использовать <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### Задание текста для определения типа данных в таблице T\-SQL  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
2.  В качестве значения свойства <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> укажите точный текст, используемый T\-SQL.  
  
## См. также  
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Как настроить классы сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)