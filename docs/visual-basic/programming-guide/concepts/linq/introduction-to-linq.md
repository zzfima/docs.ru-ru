---
title: Введение в LINQ (Visual Basic)
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: 95c1d99604ba9f87e34b5bb423d42bf97c0cd29e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648802"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="ceabb-102">Введение в LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ceabb-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="ceabb-103">LINQ (Language-Integrated Query) — это новая возможность, появившаяся в .NET Framework версии 3.5, которая соединяет мир объектов с миром данных.</span><span class="sxs-lookup"><span data-stu-id="ceabb-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="ceabb-104">Традиционно запросы к данным выражаются в виде простых строк без проверки типов при компиляции или поддержки IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ceabb-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="ceabb-105">Кроме того, разработчику приходится изучать различные языки запросов для каждого типа источников данных: баз данных SQL, XML-документов, различных веб-служб и т. д.</span><span class="sxs-lookup"><span data-stu-id="ceabb-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="ceabb-106">LINQ делает *запроса* очень удобной языковой конструкцией в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ceabb-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="ceabb-107">Вы создаете запросы к строго типизированным коллекциям объектов с помощью ключевых слов языка и знакомых операторов.</span><span class="sxs-lookup"><span data-stu-id="ceabb-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="ceabb-108">Вы можете писать запросы LINQ в Visual Basic для SQL Server базы данных, XML документы, наборы данных ADO.NET и любым коллекциям объектов, который поддерживает <xref:System.Collections.IEnumerable> или универсальный <xref:System.Collections.Generic.IEnumerable%601> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ceabb-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="ceabb-109">Кроме того, сторонние разработчики обеспечивают поддержку LINQ для множества веб-служб и других реализаций баз данных.</span><span class="sxs-lookup"><span data-stu-id="ceabb-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="ceabb-110">Запросы LINQ можно использовать в новых проектах или параллельно с запросами, не относящимися к LINQ, в существующих проектах.</span><span class="sxs-lookup"><span data-stu-id="ceabb-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="ceabb-111">Единственное требование: проект должен разрабатываться для платформы .NET Framework версии 3.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="ceabb-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="ceabb-112">На приведенном ниже рисунке показан частично выполненный запрос LINQ к базе данных SQL Server в C# и Visual Basic с полной проверкой типов и поддержкой IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ceabb-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Схема, shwos запрос LINQ с Intellisense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="ceabb-114">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ceabb-114">Next Steps</span></span>  
 <span data-ttu-id="ceabb-115">Чтобы получить дополнительные сведения о LINQ, начните с ознакомления с некоторыми основным понятиями в разделе Приступая к работе [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), а затем ознакомиться с документацией по технологии LINQ, в которой вы являетесь Вы заинтересованы:</span><span class="sxs-lookup"><span data-stu-id="ceabb-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="ceabb-116">Базы данных SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="ceabb-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="ceabb-117">XML-документы: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="ceabb-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
- <span data-ttu-id="ceabb-118">Наборы данных ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="ceabb-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="ceabb-119">Коллекции, файлы, строки и другие сущности .NET: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="ceabb-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceabb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ceabb-120">See also</span></span>

- [<span data-ttu-id="ceabb-121">Синтаксис LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ceabb-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
