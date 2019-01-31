---
title: Выражение типа <type> не доступно для запроса
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 06b2a7f5c6bd838d09fd39f31778462c364fb8bd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261260"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="2f165-102">Выражение типа \<тип > не поддерживает запросы</span><span class="sxs-lookup"><span data-stu-id="2f165-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="2f165-103">Выражение типа \<тип > не поддерживает запросы.</span><span class="sxs-lookup"><span data-stu-id="2f165-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="2f165-104">Убедитесь, что не пропущена импорта сборки ссылки или пространство имен для поставщика LINQ.</span><span class="sxs-lookup"><span data-stu-id="2f165-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="2f165-105">Запрашиваемые типы определяются в <xref:System.Linq>, <xref:System.Data.Linq>, и <xref:System.Xml.Linq> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2f165-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="2f165-106">Необходимо импортировать один или несколько из этих пространств имен для выполнения запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="2f165-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="2f165-107"><xref:System.Linq> Пространства имен позволяет отправлять запрос объектов, таких как массивы и коллекции с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="2f165-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="2f165-108"><xref:System.Data.Linq> Пространства имен позволяет запрашивать наборы данных ADO.NET и баз данных SQL Server с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="2f165-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="2f165-109"><xref:System.Xml.Linq> Пространства имен позволяет запрашивать XML с помощью LINQ и использования возможностей XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2f165-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="2f165-110">**Идентификатор ошибки:** BC36593</span><span class="sxs-lookup"><span data-stu-id="2f165-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f165-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2f165-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="2f165-112">Добавить `Import` инструкции для <xref:System.Linq>, <xref:System.Data.Linq>, или <xref:System.Xml.Linq> пространства имен в файл кода.</span><span class="sxs-lookup"><span data-stu-id="2f165-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="2f165-113">Можно также импортировать пространство имен для проекта с помощью **ссылки** страницы в конструкторе проектов (**Мой проект**).</span><span class="sxs-lookup"><span data-stu-id="2f165-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="2f165-114">Убедитесь, что тип, определенный как источник запроса является запрашиваемым типом.</span><span class="sxs-lookup"><span data-stu-id="2f165-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="2f165-115">То есть тип, реализующий <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="2f165-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f165-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2f165-116">See also</span></span>
- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- <span data-ttu-id="2f165-117">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f165-117">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="2f165-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="2f165-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="2f165-119">XML</span><span class="sxs-lookup"><span data-stu-id="2f165-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="2f165-120">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="2f165-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="2f165-121">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="2f165-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="2f165-122">Страница "Ссылки" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f165-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
