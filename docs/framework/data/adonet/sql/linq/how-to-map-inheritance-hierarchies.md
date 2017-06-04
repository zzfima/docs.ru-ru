---
title: "Как сопоставить иерархии наследования | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Как сопоставить иерархии наследования
Чтобы реализовать сопоставление наследования в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], в корневом классе иерархии наследования необходимо указать атрибуты и свойства атрибутов, как описано в следующих шагах.  Сопоставить иерархии наследования пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут с помощью [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  См. [Как настроить наследование с использованием реляционного конструктора объектов](../Topic/How%20to:%20Configure%20inheritance%20by%20using%20the%20O-R%20Designer.md).  
  
> [!NOTE]
>  Особые атрибуты или свойства подклассов не требуются.  Обратите особое внимание на то, что подклассы не имеют атрибута <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
### Сопоставление иерархий наследования  
  
1.  Добавьте к корневому классу атрибут <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
2.  Кроме того, в корневом классе необходимо добавить атрибут <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> для каждого класса в структуре иерархии.  
  
3.  Определите свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> для каждого атрибута <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
     Это свойство содержит значение, которое отображается в столбце <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> таблицы базы данных и указывает, к какому классу или подклассу принадлежит эта строка данных.  
  
4.  Добавьте также для каждого атрибута <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>.  
  
     Данное свойство содержит значение, которое указывает, на какой класс или подкласс указывает значение ключа.  
  
5.  Добавьте свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> только к одному атрибуту <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>.  
  
     Данное свойство используется для определения *резервного* сопоставления в случаях, когда значение дискриминатора из таблицы базы данных не соответствует ни одному значению <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> в сопоставлениях наследования.  
  
6.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> к атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
     Это свойство означает, что данный столбец содержит значение <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
## Пример  
  
> [!NOTE]
>  Пользователь среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] может настроить наследование с помощью [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  См. [Как настроить наследование с использованием реляционного конструктора объектов](../Topic/How%20to:%20Configure%20inheritance%20by%20using%20the%20O-R%20Designer.md).  
  
 В следующем примере кода определяется корневой класс `Vehicle` и выполняются указанные выше шаги с целью описания иерархии для [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## См. также  
 [Поддержка наследования](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)   
 [Как настроить классы сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)