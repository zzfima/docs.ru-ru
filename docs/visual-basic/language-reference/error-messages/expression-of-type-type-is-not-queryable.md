---
title: "Выражение типа &lt;тип&gt; не доступно для запроса | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36593"
  - "vbc36593"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36593"
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Выражение типа &lt;тип&gt; не доступно для запроса
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Выражение типа \<тип\> не доступно для запроса.Убедитесь, что имеются сборки ссылки или пространство имен импорта для LINQ поставщика.  
  
 Доступные для запроса типы определены в пространствах имен <xref:System.Linq>, <xref:System.Data.Linq> и <xref:System.Xml.Linq>.  Необходимо импортировать одно или несколько этих пространств имен для выполнения запросов LINQ.  
  
 Пространство имен <xref:System.Linq> позволяет запрашивать объекты, такие как массивы и коллекции, используя LINQ.  
  
 Пространство имен <xref:System.Data.Linq> позволяет запрашивать набор данных ADO.NET и базы данных SQL Server, используя LINQ.  
  
 Пространство имен <xref:System.Xml.Linq> позволяет запрашивать XML с помощью LINQ и для использования средств XML в Visual Basic.  
  
 **Идентификатор ошибки:** BC36593  
  
### Чтобы исправить эту ошибку  
  
1.  Добавьте оператор `Import` для пространства имен <xref:System.Linq>, <xref:System.Data.Linq> или <xref:System.Xml.Linq> в файл кода.  Можно также импортировать пространство имен для проекта с помощью страницы **ссылок** конструктора проектов \(**Мой проект**\).  
  
2.  Убедитесь, что тип, определенный как источник запроса, доступен для запроса типом.  То есть типом, реализующим <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.  
  
## См. также  
 <xref:System.Linq>   
 <xref:System.Data.Linq>   
 <xref:System.Xml.Linq>   
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Страница "Ссылки" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)