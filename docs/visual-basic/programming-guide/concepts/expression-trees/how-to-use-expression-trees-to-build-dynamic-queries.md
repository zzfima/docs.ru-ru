---
title: "Практическое руководство: использование деревьев выражений для построения динамических запросов (Visual Basic) | Документы Microsoft"
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
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a><span data-ttu-id="3df05-102">Практическое руководство: использование деревьев выражений для построения динамических запросов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3df05-102">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>
<span data-ttu-id="3df05-103">В LINQ деревья выражений используются для представления источников данных, которые реализуют <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> , целевой структурированных запросов</span><span class="sxs-lookup"><span data-stu-id="3df05-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="3df05-104">Например, поставщик LINQ реализует <xref:System.Linq.IQueryable%601>интерфейс для выполнения запросов к реляционным хранилищам данных.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="3df05-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="3df05-105">Компилятор Visual Basic компилирует запросы к источникам данных в код, который строит дерево выражений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3df05-105">The Visual Basic compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="3df05-106">Поставщик запросов можно просматривать структуру данных для дерева выражений и преобразовать ее в язык запросов, соответствующий для источника данных.</span><span class="sxs-lookup"><span data-stu-id="3df05-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="3df05-107">Деревья выражений также используются в LINQ для представления лямбда-выражений, которые присваиваются переменным типа <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601></span><span class="sxs-lookup"><span data-stu-id="3df05-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="3df05-108">В этом разделе описывается использование деревьев выражений для создания динамических запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="3df05-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="3df05-109">Динамические запросы полезны в тех случаях, когда характеристики запроса неизвестны во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="3df05-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="3df05-110">Например приложение может предоставлять пользовательский интерфейс, который позволяет пользователю указать один или несколько предикатов для фильтрации данных.</span><span class="sxs-lookup"><span data-stu-id="3df05-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="3df05-111">Для использования LINQ для запросов, такой тип приложений должен применять деревья выражений для создания запроса LINQ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3df05-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3df05-112">Пример</span><span class="sxs-lookup"><span data-stu-id="3df05-112">Example</span></span>  
 <span data-ttu-id="3df05-113">В следующем примере показано использование деревьев выражений для создания запроса к `IQueryable` источника данных и затем выполнить его.</span><span class="sxs-lookup"><span data-stu-id="3df05-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="3df05-114">В коде создается дерево выражения для представления следующего запроса:</span><span class="sxs-lookup"><span data-stu-id="3df05-114">The code builds an expression tree to represent the following query:</span></span>  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 <span data-ttu-id="3df05-115">Фабричные методы в <xref:System.Linq.Expressions>пространства имен используются для создания деревьев выражений, представляющих общий запрос.</xref:System.Linq.Expressions></span><span class="sxs-lookup"><span data-stu-id="3df05-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="3df05-116">Выражения, которые представляют вызовы методов стандартных операторов запросов ссылаются <xref:System.Linq.Queryable>реализации этих методов.</xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="3df05-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="3df05-117">Итоговое дерево выражения передается <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>реализацию поставщика `IQueryable` источник данных для создания исполняемого запроса типа `IQueryable`.</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29></span><span class="sxs-lookup"><span data-stu-id="3df05-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="3df05-118">Результаты получаются путем перечисление переменных запроса.</span><span class="sxs-lookup"><span data-stu-id="3df05-118">The results are obtained by enumerating that query variable.</span></span>  
  
<span data-ttu-id="3df05-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="3df05-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="3df05-120">Этот код использует фиксированное число выражений в предикате, передаваемый `Queryable.Where` метод.</span><span class="sxs-lookup"><span data-stu-id="3df05-120">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="3df05-121">Тем не менее можно написать приложение, объединяющее переменное число выражений предиката, зависящее от вводимых пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="3df05-121">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="3df05-122">Также можно изменять стандартные операторы, которые вызываются в запросе, в зависимости от входных данных от пользователя.</span><span class="sxs-lookup"><span data-stu-id="3df05-122">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3df05-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3df05-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="3df05-124">Создайте новый **консольное приложение** проекта.</span><span class="sxs-lookup"><span data-stu-id="3df05-124">Create a new **Console Application** project.</span></span>  
  
-   <span data-ttu-id="3df05-125">Добавьте ссылку на System.Core.dll, если нет ссылок.</span><span class="sxs-lookup"><span data-stu-id="3df05-125">Add a reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="3df05-126">Включите пространство имен System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="3df05-126">Include the System.Linq.Expressions namespace.</span></span>  
  
-   <span data-ttu-id="3df05-127">Скопируйте код из примера и вставьте его в `Main` `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="3df05-127">Copy the code from the example and paste it into the `Main` `Sub` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df05-128">См. также</span><span class="sxs-lookup"><span data-stu-id="3df05-128">See Also</span></span>  
 <span data-ttu-id="3df05-129">[Деревья выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="3df05-129">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="3df05-130"> [Практическое руководство: выполнение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="3df05-130"> [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span></span>
