---
title: "Выражение типа &lt;тип&gt; Незапрашиваемое | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
dev_langs:
- VB
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1e7e1e2652cf730ef6d14b0579d8a3ee3de67fbb
ms.lasthandoff: 03/13/2017

---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>Выражение типа &lt;тип&gt; не подходит для запроса
Выражение типа \<тип настроек не подходит для запроса. Убедитесь, что не пропущена импортируемый сборки ссылки или пространство имен для поставщика LINQ.  
  
 Запрашиваемые типы определяются в <xref:System.Linq>, <xref:System.Data.Linq>, и <xref:System.Xml.Linq>пространства имен.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq> Необходимо импортировать одно или несколько из этих пространств имен для выполнения запросов LINQ.  
  
 <xref:System.Linq>Пространство имен позволяет запрос объектов, таких как массивы и коллекции, используя LINQ.</xref:System.Linq>  
  
 <xref:System.Data.Linq>Пространство имен позволяет запрашивать наборы данных ADO.NET и базы данных SQL Server с помощью LINQ.</xref:System.Data.Linq>  
  
 <xref:System.Xml.Linq>Пространство имен позволяет запрашивать XML с помощью LINQ и для использования возможностей XML в Visual Basic.</xref:System.Xml.Linq>  
  
 **Идентификатор ошибки:** BC36593  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Добавить `Import` инструкции для <xref:System.Linq>, <xref:System.Data.Linq>, или <xref:System.Xml.Linq>пространства имен в файл кода.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq> Можно также импортировать пространство имен для проекта с помощью **ссылки** страницы в конструкторе проектов (**Мой проект**).  
  
2.  Убедитесь, что тип, определенный как источник запроса является запрашиваемым типом. То есть тип, реализующий <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq></xref:System.Linq>   
 <xref:System.Data.Linq></xref:System.Data.Linq>   
 <xref:System.Xml.Linq>   
 [Введение в LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Страница "Ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)
