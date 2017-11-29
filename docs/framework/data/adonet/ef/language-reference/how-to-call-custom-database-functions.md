---
title: "Практическое руководство. Вызов настраиваемых функций базы данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 181ea834bfc4e252ec57e9dbf76acfb0ea5120fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="c06c5-102">Практическое руководство. Вызов настраиваемых функций базы данных</span><span class="sxs-lookup"><span data-stu-id="c06c5-102">How to: Call Custom Database Functions</span></span>
<span data-ttu-id="c06c5-103">В данном разделе описаны процедуры вызова пользовательских функций, определенных в базе данных, из запросов LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c06c5-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="c06c5-104">Функции базы данных, вызываемые в запросах LINQ to Entities, выполняются в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c06c5-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="c06c5-105">При выполнении функций в базе данных может увеличиться производительность приложений.</span><span class="sxs-lookup"><span data-stu-id="c06c5-105">Executing functions in the database can improve application performance.</span></span>  
  
 <span data-ttu-id="c06c5-106">Процедура, приведенная ниже, обеспечивает высокоуровневую структуру вызова пользовательской функции базы данных.</span><span class="sxs-lookup"><span data-stu-id="c06c5-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="c06c5-107">В следующем примере подробно описаны шаги данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="c06c5-107">The example that follows provides more detail about the steps in the procedure.</span></span>  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="c06c5-108">Вызов пользовательских функций, определенных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c06c5-108">To call custom functions that are defined in the database</span></span>  
  
1.  <span data-ttu-id="c06c5-109">Создайте пользовательскую функцию в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c06c5-109">Create a custom function in your database.</span></span>  
  
     <span data-ttu-id="c06c5-110">Дополнительные сведения о создании пользовательских функций в SQL Server см. в разделе [CREATE FUNCTION (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkID=139871).</span><span class="sxs-lookup"><span data-stu-id="c06c5-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkID=139871).</span></span>  
  
2.  <span data-ttu-id="c06c5-111">Объявите функцию на языке SSDL в EDMX-файле.</span><span class="sxs-lookup"><span data-stu-id="c06c5-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="c06c5-112">Имя функции должно совпадать с именем функции, объявленной в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c06c5-112">The name of the function must be the same as the name of the function declared in the database.</span></span>  
  
     <span data-ttu-id="c06c5-113">Дополнительные сведения см. в разделе [функция элемент SSDL](http://msdn.microsoft.com/en-us/b60cfc3d-8b93-423e-8c99-b867256640a4).</span><span class="sxs-lookup"><span data-stu-id="c06c5-113">For more information, see [Function Element (SSDL)](http://msdn.microsoft.com/en-us/b60cfc3d-8b93-423e-8c99-b867256640a4).</span></span>  
  
3.  <span data-ttu-id="c06c5-114">Добавьте соответствующий метод к классу в коде приложения и примените <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> к этому методу. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.</span><span class="sxs-lookup"><span data-stu-id="c06c5-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="c06c5-115">При разрешении имени функции для LINQ учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c06c5-115">Function name resolution for LINQ is case sensitive.</span></span>  
  
4.  <span data-ttu-id="c06c5-116">Вызовите метод в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c06c5-116">Call the method in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c06c5-117">Пример</span><span class="sxs-lookup"><span data-stu-id="c06c5-117">Example</span></span>  
 <span data-ttu-id="c06c5-118">В следующем примере показываются процедуры вызова пользовательской функции базы данных из запроса LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c06c5-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="c06c5-119">В этом примере используется модель School.</span><span class="sxs-lookup"><span data-stu-id="c06c5-119">The example uses the School model.</span></span> <span data-ttu-id="c06c5-120">Сведения о модели School см. в разделе [Создание образца базы данных School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) и [Создание EDMX-файла School файл](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span><span class="sxs-lookup"><span data-stu-id="c06c5-120">For information about the School model, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) and [Generating the School .edmx File](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span></span>  
  
 <span data-ttu-id="c06c5-121">Следующий код добавляет функцию `AvgStudentGrade` в образец базы данных.</span><span class="sxs-lookup"><span data-stu-id="c06c5-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c06c5-122">Шаги вызова пользовательской функции базы данных одинаковы, независимо от сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="c06c5-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="c06c5-123">Однако следующий код предназначен специально для создания функции в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c06c5-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="c06c5-124">Код для создания пользовательской функции на других серверах баз данных может отличаться.</span><span class="sxs-lookup"><span data-stu-id="c06c5-124">The code for creating a custom function in other database servers might differ.</span></span>  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a><span data-ttu-id="c06c5-125">Пример</span><span class="sxs-lookup"><span data-stu-id="c06c5-125">Example</span></span>  
 <span data-ttu-id="c06c5-126">Затем объявите функцию на языке SSDL в EDMX-файле.</span><span class="sxs-lookup"><span data-stu-id="c06c5-126">Next, declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="c06c5-127">в следующем коде объявляется функция `AvgStudentGrade` на языке SSDL:</span><span class="sxs-lookup"><span data-stu-id="c06c5-127">the following code declares the `AvgStudentGrade` function in SSDL:</span></span>  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a><span data-ttu-id="c06c5-128">Пример</span><span class="sxs-lookup"><span data-stu-id="c06c5-128">Example</span></span>  
 <span data-ttu-id="c06c5-129">Теперь следует создать метод и сопоставить его с функцией, объявленной на языке SSDL.</span><span class="sxs-lookup"><span data-stu-id="c06c5-129">Now create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="c06c5-130">Метод в следующем классе сопоставляется с функцией, определенной на языке SSDL (выше) с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c06c5-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="c06c5-131">При вызове этого метода в базе данных выполняется соответствующая функция.</span><span class="sxs-lookup"><span data-stu-id="c06c5-131">When this method is called, the corresponding function in the database is executed.</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="c06c5-132">Пример</span><span class="sxs-lookup"><span data-stu-id="c06c5-132">Example</span></span>  
 <span data-ttu-id="c06c5-133">Наконец, вызовите метод в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c06c5-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="c06c5-134">Следующий код отображает в консоли фамилии студентов и средние баллы:</span><span class="sxs-lookup"><span data-stu-id="c06c5-134">The following code displays students' last names and average grades to the console:</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="c06c5-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c06c5-135">See Also</span></span>  
 [<span data-ttu-id="c06c5-136">Общие сведения о файлах .edmx</span><span class="sxs-lookup"><span data-stu-id="c06c5-136">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="c06c5-137">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c06c5-137">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
