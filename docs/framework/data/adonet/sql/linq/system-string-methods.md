---
title: "Методы System.String | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Методы System.String
Ниже перечислены методы <xref:System.String>, не поддерживаемые технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
## Неподдерживаемые методы System.String в целом  
 Далее представлены общие сведения о неподдерживаемых методах <xref:System.String>.  
  
-   Перегрузки, учитывающие язык и региональные параметры \(методы, которые принимают параметр `CultureInfo` \/ `StringComparison` \/ `IFormatProvider`\).  
  
-   Методы, которые принимают или создают массивы значений типа `char`.  
  
## Неподдерживаемые статические методы System.String  
  
|Неподдерживаемые статические методы System.String|  
|-------------------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=fullName>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|<xref:System.String.Format%2A?displayProperty=fullName>|  
|<xref:System.String.Join%2A?displayProperty=fullName>|  
  
## Неподдерживаемые методы System.String, не являющиеся статическими  
  
|Неподдерживаемые методы System.String, не являющиеся статическими|  
|-----------------------------------------------------------------------|  
|[String.IndexOfAny\(Char\<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=fullName>|  
|<xref:System.String.Split%2A?displayProperty=fullName>|  
|<xref:System.String.ToCharArray?displayProperty=fullName>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=fullName>|  
|[String.TrimEnd\(Char\<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=fullName>|  
|[String.TrimStart\(Char\<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=fullName>|  
  
## Отличия от платформы .NET  
  
-   Запросы не учитывают параметры сортировки SQL Server, которые могут применяться на сервере, и поэтому по умолчанию выполняют сравнения, зависящие от языка и региональных параметров и не зависящие от регистра.  Это поведение отличается от семантики платформы .NET Framework, по умолчанию учитывающей регистр.  
  
-   Если метод `LastIndexOf` возвращает значение 0, это означает, что либо строка равна `NULL`, либо найденная позиция равна 0.  
  
-   При объединении строк фиксированной длины \(`CHAR`, `NCHAR`\) или выполнении других операций над этими строками могут возвращаться непредвиденные результаты, поскольку к этим типам применяется автоматическое заполнение в базе данных.  
  
-   Для многих методов, таких как `Replace`, `ToLower`, `ToUpper` и индексатор знаков, не предусмотрено допустимого предобразования столбцов или кода XML типа `TEXT` или `NTEXT`, поэтому при их преобразовании, как правило, вызываются исключения `SqlExceptions`.  Это поведения считается допустимым для этих типов.  Однако все операции над строками должны соответствовать семантике среды CLR для типов `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` и `NVARCHAR(max)`.  
  
## См. также  
 [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)