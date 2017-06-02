---
title: "Как указать, для каких элементов тестируется возникновение конфликтов параллелизма | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как указать, для каких элементов тестируется возникновение конфликтов параллелизма
Чтобы указать, какие члены должны включаться в проверку обновлений на наличие конфликтов оптимистического параллелизма, в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] примените одно из трех перечислений к свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибута <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
 Свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> \(сопоставляемое во время разработки\) используется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вместе с функциями параллелизма времени выполнения.  Для получения дополнительной информации см. [Оптимистичный параллелизм. Общие сведения](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  Если ни одному члену не присвоено значение `IsVersion=true`, исходные значения членов сравниваются с текущим состоянием базы данных.  Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
### Чтобы всегда использовать этот член для обнаружения конфликтов, выполните следующие действия.  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
2.  Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `Always`.  
  
### Чтобы никогда не использовать этот член для обнаружения конфликтов, выполните следующие действия.  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
2.  Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `Never`.  
  
### Чтобы использовать этот член для обнаружения конфликтов, только когда приложение изменяет его значение, выполните следующие действия.  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
2.  Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `WhenChanged`.  
  
## Пример  
 В следующем примере указывается, что объекты `HomePage` никогда не должны включаться в проверки обновлений.  Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## См. также  
 [Как управлять конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Внесение и отправка изменений данных ](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)