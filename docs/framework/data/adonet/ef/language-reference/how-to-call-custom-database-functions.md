---
title: Практическое руководство. Вызов настраиваемых функций базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: e357868361e11dc919fa09db9a36185923a6e40e
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847096"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="27f84-102">Практическое руководство. Вызов настраиваемых функций базы данных</span><span class="sxs-lookup"><span data-stu-id="27f84-102">How to: Call Custom Database Functions</span></span>

<span data-ttu-id="27f84-103">В данном разделе описаны процедуры вызова пользовательских функций, определенных в базе данных, из запросов LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="27f84-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>

<span data-ttu-id="27f84-104">Функции базы данных, вызываемые в запросах LINQ to Entities, выполняются в базе данных.</span><span class="sxs-lookup"><span data-stu-id="27f84-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="27f84-105">При выполнении функций в базе данных может увеличиться производительность приложений.</span><span class="sxs-lookup"><span data-stu-id="27f84-105">Executing functions in the database can improve application performance.</span></span>

<span data-ttu-id="27f84-106">Процедура, приведенная ниже, обеспечивает высокоуровневую структуру вызова пользовательской функции базы данных.</span><span class="sxs-lookup"><span data-stu-id="27f84-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="27f84-107">В следующем примере подробно описаны шаги данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="27f84-107">The example that follows provides more detail about the steps in the procedure.</span></span>

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="27f84-108">Вызов пользовательских функций, определенных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="27f84-108">To call custom functions that are defined in the database</span></span>

1. <span data-ttu-id="27f84-109">Создайте пользовательскую функцию в базе данных.</span><span class="sxs-lookup"><span data-stu-id="27f84-109">Create a custom function in your database.</span></span>

     <span data-ttu-id="27f84-110">Дополнительные сведения о создании пользовательских функций в SQL Server см. в разделе [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span><span class="sxs-lookup"><span data-stu-id="27f84-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span></span>

2. <span data-ttu-id="27f84-111">Объявите функцию на языке SSDL в EDMX-файле.</span><span class="sxs-lookup"><span data-stu-id="27f84-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="27f84-112">Имя функции должно совпадать с именем функции, объявленной в базе данных.</span><span class="sxs-lookup"><span data-stu-id="27f84-112">The name of the function must be the same as the name of the function declared in the database.</span></span>

     <span data-ttu-id="27f84-113">Дополнительные сведения см. в разделе [элемент Function (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="27f84-113">For more information, see [Function Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span></span>

3. <span data-ttu-id="27f84-114">Добавьте соответствующий метод к классу в коде приложения и примените <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> к этому методу. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.</span><span class="sxs-lookup"><span data-stu-id="27f84-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="27f84-115">При разрешении имени функции для LINQ учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="27f84-115">Function name resolution for LINQ is case sensitive.</span></span>

4. <span data-ttu-id="27f84-116">Вызовите метод в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="27f84-116">Call the method in a LINQ to Entities query.</span></span>  

## <a name="example"></a><span data-ttu-id="27f84-117">Пример</span><span class="sxs-lookup"><span data-stu-id="27f84-117">Example</span></span>

<span data-ttu-id="27f84-118">В следующем примере показываются процедуры вызова пользовательской функции базы данных из запроса LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="27f84-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="27f84-119">В этом примере используется модель School.</span><span class="sxs-lookup"><span data-stu-id="27f84-119">The example uses the School model.</span></span> <span data-ttu-id="27f84-120">Сведения о модели School см. в разделе [Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) и [Создание файла School. EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="27f84-120">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>

<span data-ttu-id="27f84-121">Следующий код добавляет функцию `AvgStudentGrade` в образец базы данных.</span><span class="sxs-lookup"><span data-stu-id="27f84-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>

> [!NOTE]
> <span data-ttu-id="27f84-122">Шаги вызова пользовательской функции базы данных одинаковы, независимо от сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="27f84-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="27f84-123">Однако следующий код предназначен специально для создания функции в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="27f84-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="27f84-124">Код для создания пользовательской функции на других серверах баз данных может отличаться.</span><span class="sxs-lookup"><span data-stu-id="27f84-124">The code for creating a custom function in other database servers might differ.</span></span>

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a><span data-ttu-id="27f84-125">Пример</span><span class="sxs-lookup"><span data-stu-id="27f84-125">Example</span></span>

<span data-ttu-id="27f84-126">Затем объявите функцию на языке SSDL для *EDMX* -файла.</span><span class="sxs-lookup"><span data-stu-id="27f84-126">Next, declare a function in the store schema definition language (SSDL) of your *.edmx* file.</span></span> <span data-ttu-id="27f84-127">Следующий код объявляет функцию `AvgStudentGrade` на языке SSDL:</span><span class="sxs-lookup"><span data-stu-id="27f84-127">The following code declares the `AvgStudentGrade` function in SSDL:</span></span>

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a><span data-ttu-id="27f84-128">Пример</span><span class="sxs-lookup"><span data-stu-id="27f84-128">Example</span></span>

<span data-ttu-id="27f84-129">Теперь создайте метод и сопоставьте его с функцией, объявленной в SSDL.</span><span class="sxs-lookup"><span data-stu-id="27f84-129">Now, create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="27f84-130">Метод в следующем классе сопоставляется с функцией, определенной на языке SSDL (выше) с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="27f84-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="27f84-131">При вызове этого метода в базе данных выполняется соответствующая функция.</span><span class="sxs-lookup"><span data-stu-id="27f84-131">When this method is called, the corresponding function in the database is executed.</span></span>

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="27f84-132">Пример</span><span class="sxs-lookup"><span data-stu-id="27f84-132">Example</span></span>

<span data-ttu-id="27f84-133">Наконец, вызовите метод в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="27f84-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="27f84-134">Следующий код отображает в консоли фамилии студентов и средние баллы:</span><span class="sxs-lookup"><span data-stu-id="27f84-134">The following code displays students' last names and average grades to the console:</span></span>

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="27f84-135">См. также</span><span class="sxs-lookup"><span data-stu-id="27f84-135">See also</span></span>

- <span data-ttu-id="27f84-136">[Общие сведения о файле EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="27f84-136">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="27f84-137">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="27f84-137">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
