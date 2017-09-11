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
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84563c7339ffe7415017280d74a13d6501236da5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a><span data-ttu-id="7356a-102">Выражение типа &lt;тип&gt; не подходит для запроса</span><span class="sxs-lookup"><span data-stu-id="7356a-102">Expression of type &lt;type&gt; is not queryable</span></span>
<span data-ttu-id="7356a-103">Выражение типа \<тип настроек не подходит для запроса.</span><span class="sxs-lookup"><span data-stu-id="7356a-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="7356a-104">Убедитесь, что не пропущена импортируемый сборки ссылки или пространство имен для поставщика LINQ.</span><span class="sxs-lookup"><span data-stu-id="7356a-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="7356a-105">Запрашиваемые типы определяются в <xref:System.Linq>, <xref:System.Data.Linq>, и <xref:System.Xml.Linq>пространства имен.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="7356a-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="7356a-106">Необходимо импортировать одно или несколько из этих пространств имен для выполнения запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="7356a-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="7356a-107"><xref:System.Linq>Пространство имен позволяет запрос объектов, таких как массивы и коллекции, используя LINQ.</xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="7356a-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="7356a-108"><xref:System.Data.Linq>Пространство имен позволяет запрашивать наборы данных ADO.NET и базы данных SQL Server с помощью LINQ.</xref:System.Data.Linq></span><span class="sxs-lookup"><span data-stu-id="7356a-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="7356a-109"><xref:System.Xml.Linq>Пространство имен позволяет запрашивать XML с помощью LINQ и для использования возможностей XML в Visual Basic.</xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="7356a-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="7356a-110">**Идентификатор ошибки:** BC36593</span><span class="sxs-lookup"><span data-stu-id="7356a-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7356a-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7356a-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="7356a-112">Добавить `Import` инструкции для <xref:System.Linq>, <xref:System.Data.Linq>, или <xref:System.Xml.Linq>пространства имен в файл кода.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="7356a-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="7356a-113">Можно также импортировать пространство имен для проекта с помощью **ссылки** страницы в конструкторе проектов (**Мой проект**).</span><span class="sxs-lookup"><span data-stu-id="7356a-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="7356a-114">Убедитесь, что тип, определенный как источник запроса является запрашиваемым типом.</span><span class="sxs-lookup"><span data-stu-id="7356a-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="7356a-115">То есть тип, реализующий <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="7356a-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7356a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7356a-116">See Also</span></span>  
 <span data-ttu-id="7356a-117"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="7356a-117"><xref:System.Linq></span></span>   
 <span data-ttu-id="7356a-118"><xref:System.Data.Linq></xref:System.Data.Linq></span><span class="sxs-lookup"><span data-stu-id="7356a-118"><xref:System.Data.Linq></span></span>   
 <span data-ttu-id="7356a-119"><xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="7356a-119"><xref:System.Xml.Linq></span></span>   
<span data-ttu-id="7356a-120"> [Введение в LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="7356a-120"> [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="7356a-121"> [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="7356a-121"> [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="7356a-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="7356a-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="7356a-123"> [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7356a-123"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="7356a-124"> [Оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="7356a-124"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="7356a-125"> [Страница "Ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="7356a-125"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
