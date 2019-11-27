---
title: Введение в LINQ
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: add442583bd81665533b704c0c9721b111cddd78
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338908"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="97222-102">Введение в LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97222-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="97222-103">LINQ (Language-Integrated Query) — это новая возможность, появившаяся в .NET Framework версии 3.5, которая соединяет мир объектов с миром данных.</span><span class="sxs-lookup"><span data-stu-id="97222-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="97222-104">Традиционно запросы к данным выражаются в виде простых строк без проверки типов при компиляции или поддержки IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="97222-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="97222-105">Кроме того, разработчику приходится изучать различные языки запросов для каждого из типов источников данных: баз данных SQL, XML-документов, различных веб-служб и т. д.</span><span class="sxs-lookup"><span data-stu-id="97222-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="97222-106">LINQ делает *запрос* к конструкции языка первого класса в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="97222-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="97222-107">Вы создаете запросы к строго типизированным коллекциям объектов с помощью ключевых слов языка и знакомых операторов.</span><span class="sxs-lookup"><span data-stu-id="97222-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="97222-108">Можно писать запросы LINQ в Visual Basic для SQL Server баз данных, XML-документов, наборов данных ADO.NET и любой коллекции объектов, поддерживающей <xref:System.Collections.IEnumerable> или универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="97222-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="97222-109">Кроме того, сторонние разработчики обеспечивают поддержку LINQ для множества веб-служб и других реализаций баз данных.</span><span class="sxs-lookup"><span data-stu-id="97222-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="97222-110">Запросы LINQ можно использовать в новых проектах или параллельно с запросами, не относящимися к LINQ, в существующих проектах.</span><span class="sxs-lookup"><span data-stu-id="97222-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="97222-111">Единственное требование: проект должен разрабатываться для платформы .NET Framework версии 3.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="97222-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="97222-112">На приведенном ниже рисунке показан частично выполненный запрос LINQ к базе данных SQL Server в C# и Visual Basic с полной проверкой типов и поддержкой IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="97222-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Схема, показывающая запрос LINQ с Intellisense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="97222-114">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="97222-114">Next Steps</span></span>  
 <span data-ttu-id="97222-115">Чтобы получить дополнительные сведения о LINQ, начните с ознакомления с некоторыми основными понятиями в начало работы разделе [Начало работы с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), а затем прочитайте документацию по интересующей вас технологии LINQ:</span><span class="sxs-lookup"><span data-stu-id="97222-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="97222-116">Базы данных SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="97222-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="97222-117">XML-документы: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="97222-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
- <span data-ttu-id="97222-118">Наборы данных ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="97222-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="97222-119">Коллекции .NET, файлы, строки и т. д. [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="97222-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97222-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="97222-120">See also</span></span>

- [<span data-ttu-id="97222-121">Синтаксис LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97222-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
