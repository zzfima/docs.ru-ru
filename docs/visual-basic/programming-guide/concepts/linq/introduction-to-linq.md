---
title: "Введение в LINQ (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d2c02daacc2674da31715e5fda027b97e6b7bc97
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="651ea-102">Введение в LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="651ea-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="651ea-103">Новая возможность, появившаяся в .NET Framework версии 3.5, мосты вовлеченности мир объектов с миром данных является Language Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="651ea-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="651ea-104">Традиционно запросы к данным выражаются в виде простых строк без проверки типов при компиляции или поддержки IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="651ea-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="651ea-105">Кроме того, необходимо узнать различные языки запросов для каждого типа источника данных: SQL базы данных, документы XML, различных веб-служб и т. д.</span><span class="sxs-lookup"><span data-stu-id="651ea-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="651ea-106">LINQ позволяет *запроса* конструкцию полноправный язык в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="651ea-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="651ea-107">Писать запросы к строго типизированным коллекциям объектов с помощью ключевых слов языка и знакомых операторов.</span><span class="sxs-lookup"><span data-stu-id="651ea-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="651ea-108">Можно писать запросы LINQ в Visual Basic для SQL Server базы данных, XML документы, наборы данных ADO.NET и коллекцию объектов, которая поддерживает <xref:System.Collections.IEnumerable>или универсальный <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="651ea-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="651ea-109">Поддержка LINQ также предоставляется сторонними производителями для многих веб-служб и других реализаций базы данных.</span><span class="sxs-lookup"><span data-stu-id="651ea-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="651ea-110">Запросы LINQ можно использовать в новых проектах или параллельно с не использующего LINQ запросы в существующих проектах.</span><span class="sxs-lookup"><span data-stu-id="651ea-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="651ea-111">Единственным требованием является то, что проект предназначены для .NET Framework 3.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="651ea-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="651ea-112">На следующем из Visual Studio рисунке частично завершенной LINQ-запрос для базы данных SQL Server в C# и Visual Basic с полной проверкой типов и поддержку технологии IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="651ea-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="651ea-113">![Запрос LINQ с Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="651ea-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="651ea-114">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="651ea-114">Next Steps</span></span>  
 <span data-ttu-id="651ea-115">Чтобы получить дополнительные сведения о LINQ, начните с ознакомления с некоторыми основными понятиями в разделе Приступая к работе [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), а затем прочитайте документацию по технологии LINQ, который вас интересует:</span><span class="sxs-lookup"><span data-stu-id="651ea-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="651ea-116">Базы данных SQL Server: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="651ea-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="651ea-117">XML-документы: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="651ea-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="651ea-118">Наборы данных ADO.NET: [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)</span><span class="sxs-lookup"><span data-stu-id="651ea-118">ADO.NET Datasets: [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)</span></span>  
  
-   <span data-ttu-id="651ea-119">Коллекции .NET, файлы, строк и т. д: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="651ea-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651ea-120">См. также</span><span class="sxs-lookup"><span data-stu-id="651ea-120">See Also</span></span>  
 [<span data-ttu-id="651ea-121">Интегрированный в язык запрос (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="651ea-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
