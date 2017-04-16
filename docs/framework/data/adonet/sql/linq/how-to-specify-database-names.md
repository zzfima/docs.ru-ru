---
title: "Как указывать имена баз данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как указывать имена баз данных
Для указания имени базы данных, если это имя не предоставлено во время подключения, используется свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> атрибута <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
### Указание имени базы данных  
  
1.  Добавьте атрибут <xref:System.Data.Linq.Mapping.DatabaseAttribute> к объявлению класса для базы данных.  
  
2.  Добавьте свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute> атрибуту <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
3.  Установите для свойства <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> значение имени, которое необходимо указать.  
  
## См. также  
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Как настроить классы сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)