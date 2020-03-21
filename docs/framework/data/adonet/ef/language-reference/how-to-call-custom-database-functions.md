---
title: Практическое руководство. Вызов настраиваемых функций базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: f3177ab98382506770c4655c62573da5c1d96c69
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78848760"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="f316a-102">Практическое руководство. Вызов настраиваемых функций базы данных</span><span class="sxs-lookup"><span data-stu-id="f316a-102">How to: Call Custom Database Functions</span></span>

<span data-ttu-id="f316a-103">В данном разделе описаны процедуры вызова пользовательских функций, определенных в базе данных, из запросов LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="f316a-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>

<span data-ttu-id="f316a-104">Функции базы данных, вызываемые в запросах LINQ to Entities, выполняются в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f316a-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="f316a-105">При выполнении функций в базе данных может увеличиться производительность приложений.</span><span class="sxs-lookup"><span data-stu-id="f316a-105">Executing functions in the database can improve application performance.</span></span>

<span data-ttu-id="f316a-106">Процедура, приведенная ниже, обеспечивает высокоуровневую структуру вызова пользовательской функции базы данных.</span><span class="sxs-lookup"><span data-stu-id="f316a-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="f316a-107">В следующем примере подробно описаны шаги данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="f316a-107">The example that follows provides more detail about the steps in the procedure.</span></span>

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="f316a-108">Вызов пользовательских функций, определенных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f316a-108">To call custom functions that are defined in the database</span></span>

1. <span data-ttu-id="f316a-109">Создайте пользовательскую функцию в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f316a-109">Create a custom function in your database.</span></span>

     <span data-ttu-id="f316a-110">Для получения более подробной информации о создании пользовательских функций в сервере S'L, [см.](/sql/t-sql/statements/create-function-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="f316a-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).</span></span>

2. <span data-ttu-id="f316a-111">Объявите функцию на языке SSDL в EDMX-файле.</span><span class="sxs-lookup"><span data-stu-id="f316a-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="f316a-112">Имя функции должно совпадать с именем функции, объявленной в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f316a-112">The name of the function must be the same as the name of the function declared in the database.</span></span>

     <span data-ttu-id="f316a-113">Для получения дополнительной информации [см.](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl)</span><span class="sxs-lookup"><span data-stu-id="f316a-113">For more information, see [Function Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span></span>

3. <span data-ttu-id="f316a-114">Добавьте соответствующий метод к классу в коде приложения и примените <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> к этому методу. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.</span><span class="sxs-lookup"><span data-stu-id="f316a-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="f316a-115">При разрешении имени функции для LINQ учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="f316a-115">Function name resolution for LINQ is case sensitive.</span></span>

4. <span data-ttu-id="f316a-116">Вызовите метод в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="f316a-116">Call the method in a LINQ to Entities query.</span></span>  

## <a name="example"></a><span data-ttu-id="f316a-117">Пример</span><span class="sxs-lookup"><span data-stu-id="f316a-117">Example</span></span>

<span data-ttu-id="f316a-118">В следующем примере показываются процедуры вызова пользовательской функции базы данных из запроса LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="f316a-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="f316a-119">В этом примере используется модель School.</span><span class="sxs-lookup"><span data-stu-id="f316a-119">The example uses the School model.</span></span> <span data-ttu-id="f316a-120">Для получения информации о модели школы [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))см. [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f316a-120">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>

<span data-ttu-id="f316a-121">Следующий код добавляет функцию `AvgStudentGrade` в образец базы данных.</span><span class="sxs-lookup"><span data-stu-id="f316a-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>

> [!NOTE]
> <span data-ttu-id="f316a-122">Шаги вызова пользовательской функции базы данных одинаковы, независимо от сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="f316a-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="f316a-123">Однако следующий код предназначен специально для создания функции в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f316a-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="f316a-124">Код для создания пользовательской функции на других серверах баз данных может отличаться.</span><span class="sxs-lookup"><span data-stu-id="f316a-124">The code for creating a custom function in other database servers might differ.</span></span>

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a><span data-ttu-id="f316a-125">Пример</span><span class="sxs-lookup"><span data-stu-id="f316a-125">Example</span></span>

<span data-ttu-id="f316a-126">Затем объявите функцию в языке определения схемы хранилища (SSDL) файла *.edmx.*</span><span class="sxs-lookup"><span data-stu-id="f316a-126">Next, declare a function in the store schema definition language (SSDL) of your *.edmx* file.</span></span> <span data-ttu-id="f316a-127">Следующий код декларирует функцию `AvgStudentGrade` в SSDL:</span><span class="sxs-lookup"><span data-stu-id="f316a-127">The following code declares the `AvgStudentGrade` function in SSDL:</span></span>

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a><span data-ttu-id="f316a-128">Пример</span><span class="sxs-lookup"><span data-stu-id="f316a-128">Example</span></span>

<span data-ttu-id="f316a-129">Создайте метод и сообразуйте его с функцией, заявленной в SSDL.</span><span class="sxs-lookup"><span data-stu-id="f316a-129">Now, create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="f316a-130">Метод в следующем классе сопоставляется с функцией, определенной на языке SSDL (выше) с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f316a-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="f316a-131">При вызове этого метода в базе данных выполняется соответствующая функция.</span><span class="sxs-lookup"><span data-stu-id="f316a-131">When this method is called, the corresponding function in the database is executed.</span></span>

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="f316a-132">Пример</span><span class="sxs-lookup"><span data-stu-id="f316a-132">Example</span></span>

<span data-ttu-id="f316a-133">Наконец, вызовите метод в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="f316a-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="f316a-134">Следующий код отображает в консоли фамилии студентов и средние баллы:</span><span class="sxs-lookup"><span data-stu-id="f316a-134">The following code displays students' last names and average grades to the console:</span></span>

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="f316a-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f316a-135">See also</span></span>

- <span data-ttu-id="f316a-136">[Общие сведения о EDMX-файлах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f316a-136">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="f316a-137">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="f316a-137">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
