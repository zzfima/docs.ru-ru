---
title: Выражение типа &lt;тип&gt; не поддерживает запросы
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 9d333abda5e303f8fab6d1f707df7ac77d8e03ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589013"
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>Выражение типа &lt;тип&gt; не поддерживает запросы
Выражение типа \<тип > не поддерживает запросы. Убедитесь, что не пропущена сборки ссылки или импорт пространства имен для поставщика LINQ.  
  
 Запрашиваемые типы определены в <xref:System.Linq>, <xref:System.Data.Linq>, и <xref:System.Xml.Linq> пространства имен. Необходимо импортировать одно или несколько из этих пространств имен для выполнения запросов LINQ.  
  
 <xref:System.Linq> Пространство имен позволяет указать запрос объектов, таких как массивы и коллекции с помощью LINQ.  
  
 <xref:System.Data.Linq> Пространство имен позволяет запрашивать наборы данных ADO.NET и базы данных SQL Server с помощью LINQ.  
  
 <xref:System.Xml.Linq> Пространство имен позволяет запрашивать XML с помощью LINQ и использования возможностей XML в Visual Basic.  
  
 **Идентификатор ошибки:** BC36593  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Добавить `Import` инструкции для <xref:System.Linq>, <xref:System.Data.Linq>, или <xref:System.Xml.Linq> пространства имен в файл кода. Можно также импортировать пространство имен для проекта с помощью **ссылки** страницы конструктора проектов (**Мой проект**).  
  
2.  Убедитесь, что тип, определенный как источник запроса является запрашиваемым типом. То есть тип, реализующий <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq>  
 <xref:System.Data.Linq>  
 <xref:System.Xml.Linq>  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Страница "Ссылки" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
