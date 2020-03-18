---
title: Пошаговое руководство. Написание запросов на C# (LINQ)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: f2135c6c3649ba2fc87e3b49770439688a58269b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73418056"
---
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="972f1-102">Пошаговое руководство. Написание запросов на C# (LINQ)</span><span class="sxs-lookup"><span data-stu-id="972f1-102">Walkthrough: Writing Queries in C# (LINQ)</span></span>
<span data-ttu-id="972f1-103">В этом пошаговом руководстве описываются возможности C#, предназначенные для написания выражений запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="972f1-103">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="972f1-104">Создание проекта C#</span><span class="sxs-lookup"><span data-stu-id="972f1-104">Create a C# Project</span></span>  
  
> [!NOTE]
> <span data-ttu-id="972f1-105">Приведенные ниже инструкции относятся к Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="972f1-105">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="972f1-106">Если вы пользуетесь другой средой разработки, создайте консольный проект со ссылкой на библиотеку System.Core.dll и директиву `using` для пространства имен <xref:System.Linq?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="972f1-106">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="972f1-107">Создание проекта в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="972f1-107">To create a project in Visual Studio</span></span>  
  
1. <span data-ttu-id="972f1-108">Запустите среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="972f1-108">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="972f1-109">В главном меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="972f1-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="972f1-110">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="972f1-110">The **New Project** dialog box opens.</span></span>  
  
3. <span data-ttu-id="972f1-111">Последовательно разверните узлы **Установленные**, **Шаблоны** и **Visual C#** , а затем выберите **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="972f1-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4. <span data-ttu-id="972f1-112">В текстовое поле **Имя** введите другое имя или примите имя по умолчанию и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="972f1-112">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="972f1-113">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="972f1-113">The new project appears in **Solution Explorer**.</span></span>  
  
5. <span data-ttu-id="972f1-114">Обратите внимание, что проект содержит ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен <xref:System.Linq?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="972f1-114">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="972f1-115">Создание источника данных в памяти</span><span class="sxs-lookup"><span data-stu-id="972f1-115">Create an in-Memory Data Source</span></span>  
 <span data-ttu-id="972f1-116">Источником данных для запросов является простой список объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="972f1-116">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="972f1-117">Каждая запись `Student` включает имя, фамилию и массив целых чисел, соответствующих их баллам за проведенные в классе тесты.</span><span class="sxs-lookup"><span data-stu-id="972f1-117">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="972f1-118">Скопируйте этот код в проект.</span><span class="sxs-lookup"><span data-stu-id="972f1-118">Copy this code into your project.</span></span> <span data-ttu-id="972f1-119">Обратите внимание на следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="972f1-119">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="972f1-120">Класс `Student` состоит из автоматически внедренных свойств.</span><span class="sxs-lookup"><span data-stu-id="972f1-120">The `Student` class consists of auto-implemented properties.</span></span>  
  
- <span data-ttu-id="972f1-121">Каждый учащийся в списке инициализируется соответствующим инициализатором объекта.</span><span class="sxs-lookup"><span data-stu-id="972f1-121">Each student in the list is initialized with an object initializer.</span></span>  
  
- <span data-ttu-id="972f1-122">Сам список инициализируется инициализатором коллекции.</span><span class="sxs-lookup"><span data-stu-id="972f1-122">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="972f1-123">Вся эта структура данных инициализируется и создается без явных вызовов какого-либо конструктора или прямого доступа к членам.</span><span class="sxs-lookup"><span data-stu-id="972f1-123">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="972f1-124">Дополнительные сведения об этих новых возможностях см. в разделах [Автоматически внедренные свойства](../../classes-and-structs/auto-implemented-properties.md) и [Инициализаторы объектов и коллекций](../../classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="972f1-124">For more information about these new features, see [Auto-Implemented Properties](../../classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="972f1-125">Добавление источника данных</span><span class="sxs-lookup"><span data-stu-id="972f1-125">To add the data source</span></span>  
  
- <span data-ttu-id="972f1-126">Добавьте класс `Student` и инициализированный список учащихся в класс `Program` в проекте.</span><span class="sxs-lookup"><span data-stu-id="972f1-126">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     [!code-csharp[CsLinqGettingStarted#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#11)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="972f1-127">Добавление нового учащегося в список учащихся</span><span class="sxs-lookup"><span data-stu-id="972f1-127">To add a new Student to the Students list</span></span>  
  
1. <span data-ttu-id="972f1-128">Добавьте новый объект `Student` в список `Students` и введите любое имя и результаты тестирования.</span><span class="sxs-lookup"><span data-stu-id="972f1-128">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="972f1-129">Чтобы лучше изучить синтаксис инициализатора объекта, постарайтесь заполнить все данные нового учащегося.</span><span class="sxs-lookup"><span data-stu-id="972f1-129">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="972f1-130">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="972f1-130">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="972f1-131">Создание простого запроса</span><span class="sxs-lookup"><span data-stu-id="972f1-131">To create a simple query</span></span>  
  
- <span data-ttu-id="972f1-132">В методе `Main` приложения создайте простой запрос, при выполнении которого будет возвращаться список учащихся, набравших в первом тесте больше 90 баллов.</span><span class="sxs-lookup"><span data-stu-id="972f1-132">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="972f1-133">Поскольку выбран весь объект `Student`, запрос имеет тип `IEnumerable<Student>`.</span><span class="sxs-lookup"><span data-stu-id="972f1-133">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="972f1-134">Несмотря на то, что код можно также набрать напрямую, используя ключевое слово [var](../../../language-reference/keywords/var.md), для демонстрации результатов применяется неявная типизация.</span><span class="sxs-lookup"><span data-stu-id="972f1-134">Although the code could also use implicit typing by using the [var](../../../language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="972f1-135">(Дополнительные сведения о `var` см. в разделе [Неявно типизированные локальные переменные](../../classes-and-structs/implicitly-typed-local-variables.md).)</span><span class="sxs-lookup"><span data-stu-id="972f1-135">(For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="972f1-136">Кроме того переменная диапазона в запросе, `student`, служит ссылкой на каждый объект `Student` в источнике и предоставляет доступ к каждому объекту.</span><span class="sxs-lookup"><span data-stu-id="972f1-136">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#12)]  
  
## <a name="execute-the-query"></a><span data-ttu-id="972f1-137">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="972f1-137">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="972f1-138">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="972f1-138">To execute the query</span></span>  
  
1. <span data-ttu-id="972f1-139">Теперь напишите цикл `foreach`, вызывающий выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="972f1-139">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="972f1-140">Обратите внимание на следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="972f1-140">Note the following about the code:</span></span>  
  
    - <span data-ttu-id="972f1-141">Доступ к каждому элементу в возвращаемой последовательности осуществляется с помощью переменной итерации в цикле `foreach`.</span><span class="sxs-lookup"><span data-stu-id="972f1-141">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    - <span data-ttu-id="972f1-142">Эта переменная имеет тип `Student`, а переменная запроса — совместимый тип `IEnumerable<Student>`.</span><span class="sxs-lookup"><span data-stu-id="972f1-142">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2. <span data-ttu-id="972f1-143">Добавив код, соберите и запустите приложение, чтобы отобразить результаты в окне **Консоль**.</span><span class="sxs-lookup"><span data-stu-id="972f1-143">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#13)]  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="972f1-144">Добавление другого условия фильтра</span><span class="sxs-lookup"><span data-stu-id="972f1-144">To add another filter condition</span></span>  
  
1. <span data-ttu-id="972f1-145">Чтобы сделать запрос более точным, можно объединить несколько логических условий в предложение `where`.</span><span class="sxs-lookup"><span data-stu-id="972f1-145">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="972f1-146">Следующий код добавляет условие, согласно которому запрос возвращает учащихся, которые по первому тесту набрали больше 90 баллов, а по последнему — меньше 80 баллов.</span><span class="sxs-lookup"><span data-stu-id="972f1-146">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="972f1-147">Предложение `where` должно быть аналогично приведенному ниже коду.</span><span class="sxs-lookup"><span data-stu-id="972f1-147">The `where` clause should resemble the following code.</span></span>  
  
    ```csharp
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="972f1-148">Дополнительные сведения см. в разделе [Предложение where](../../../language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="972f1-148">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="972f1-149">Изменение запроса</span><span class="sxs-lookup"><span data-stu-id="972f1-149">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="972f1-150">Упорядочение результатов</span><span class="sxs-lookup"><span data-stu-id="972f1-150">To order the results</span></span>  
  
1. <span data-ttu-id="972f1-151">С результатами проще работать, если они упорядочены.</span><span class="sxs-lookup"><span data-stu-id="972f1-151">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="972f1-152">Возвращаемую последовательность можно упорядочить по любому доступному полю в исходных элементах.</span><span class="sxs-lookup"><span data-stu-id="972f1-152">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="972f1-153">Например, следующее предложение `orderby` упорядочивает результаты в алфавитном порядке от А до Z, используя фамилии учащихся.</span><span class="sxs-lookup"><span data-stu-id="972f1-153">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="972f1-154">Добавьте к запросу следующее предложение `orderby`, указав его после оператора `where` и перед оператором `select`:</span><span class="sxs-lookup"><span data-stu-id="972f1-154">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```csharp
    orderby student.Last ascending  
    ```  
  
2. <span data-ttu-id="972f1-155">Теперь измените предложение `orderby` таким образом, чтобы результаты были упорядочены по баллам за первый тест в обратном порядке, от наибольшего к наименьшему.</span><span class="sxs-lookup"><span data-stu-id="972f1-155">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```csharp
    orderby student.Scores[0] descending  
    ```  
  
3. <span data-ttu-id="972f1-156">Измените строку формата `WriteLine` таким образом, чтобы отобразить баллы:</span><span class="sxs-lookup"><span data-stu-id="972f1-156">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```csharp
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="972f1-157">Дополнительные сведения см. в разделе [Предложение orderby](../../../language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="972f1-157">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="972f1-158">Группировка результатов</span><span class="sxs-lookup"><span data-stu-id="972f1-158">To group the results</span></span>  
  
1. <span data-ttu-id="972f1-159">Группировка представляет собой полезную возможность в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="972f1-159">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="972f1-160">Запрос с предложением group создает последовательность групп, в которой каждая группа содержит `Key`, и последовательность, состоящую из всех членов этой группы.</span><span class="sxs-lookup"><span data-stu-id="972f1-160">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="972f1-161">Представленный ниже запрос группирует учащихся, используя в качестве ключа первую букву фамилии.</span><span class="sxs-lookup"><span data-stu-id="972f1-161">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#14)]  
  
2. <span data-ttu-id="972f1-162">Обратите внимание на то, что тип запроса изменился.</span><span class="sxs-lookup"><span data-stu-id="972f1-162">Note that the type of the query has now changed.</span></span> <span data-ttu-id="972f1-163">Теперь он создает последовательность групп с типом `char` в качестве ключа и последовательность объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="972f1-163">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="972f1-164">Поскольку тип запроса изменился, следующий код изменяет также цикл выполнения `foreach`:</span><span class="sxs-lookup"><span data-stu-id="972f1-164">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#15)]  
  
3. <span data-ttu-id="972f1-165">Запустите приложение и просмотрите результаты в окне **Консоль**.</span><span class="sxs-lookup"><span data-stu-id="972f1-165">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="972f1-166">Дополнительные сведения см. в разделе [Предложение group](../../../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="972f1-166">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="972f1-167">Преобразование переменных в явно типизированные</span><span class="sxs-lookup"><span data-stu-id="972f1-167">To make the variables implicitly typed</span></span>  
  
1. <span data-ttu-id="972f1-168">Набирать код `IEnumerables` в `IGroupings` напрямую — далеко не самое увлекательное занятие.</span><span class="sxs-lookup"><span data-stu-id="972f1-168">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="972f1-169">Написать тот же запрос и цикл `foreach` можно быстрее и проще, воспользовавшись переменной `var`.</span><span class="sxs-lookup"><span data-stu-id="972f1-169">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="972f1-170">Ключевое слово `var` не приводит к изменению типов объектов, оно просто сообщает компилятору о том, что он должен вывести типы логически.</span><span class="sxs-lookup"><span data-stu-id="972f1-170">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="972f1-171">Измените тип `studentQuery` и переменную итерации `group` на `var` и выполните запрос заново.</span><span class="sxs-lookup"><span data-stu-id="972f1-171">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="972f1-172">Обратите внимание на то, что во внутреннем цикле `foreach` переменная итерации по-прежнему типизируется как `Student`, а запрос работает так же, как раньше.</span><span class="sxs-lookup"><span data-stu-id="972f1-172">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="972f1-173">Измените переменную итерации `s` на `var` и выполните запрос заново.</span><span class="sxs-lookup"><span data-stu-id="972f1-173">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="972f1-174">Результаты будут точно такими же.</span><span class="sxs-lookup"><span data-stu-id="972f1-174">You see that you get exactly the same results.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#16)]  
  
     <span data-ttu-id="972f1-175">Дополнительные сведения о переменной [var](../../../language-reference/keywords/var.md) см. в разделе [Неявно типизированные локальные переменные](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="972f1-175">For more information about [var](../../../language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="972f1-176">Упорядочение групп по значению ключа</span><span class="sxs-lookup"><span data-stu-id="972f1-176">To order the groups by their key value</span></span>  
  
1. <span data-ttu-id="972f1-177">Выполняя предыдущий запрос, вы могли заметить, что группы отображаются не в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="972f1-177">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="972f1-178">Для того чтобы это изменить, необходимо указать предложение `orderby` после предложения `group`.</span><span class="sxs-lookup"><span data-stu-id="972f1-178">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="972f1-179">Но, чтобы использовать предложение `orderby`, нужен идентификатор, служащий в качестве ссылки на группы, создаваемые предложением `group`.</span><span class="sxs-lookup"><span data-stu-id="972f1-179">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="972f1-180">Укажите идентификатор с помощью ключевого слова `into`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="972f1-180">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#17)]  
  
     <span data-ttu-id="972f1-181">После выполнения этого запроса группы будут отсортированы в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="972f1-181">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="972f1-182">Введение идентификаторов с помощью предложения let</span><span class="sxs-lookup"><span data-stu-id="972f1-182">To introduce an identifier by using let</span></span>  
  
1. <span data-ttu-id="972f1-183">Ключевое слово `let` позволяет ввести идентификатор для любого результата в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="972f1-183">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="972f1-184">Этот идентификатор может применяться для удобства, как в следующем примере, или повышать производительность, сохраняя результаты выражения, чтобы не вычислять их повторно.</span><span class="sxs-lookup"><span data-stu-id="972f1-184">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#18)]  
  
     <span data-ttu-id="972f1-185">Дополнительные сведения см. в разделе [Предложение let](../../../language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="972f1-185">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="972f1-186">Использование синтаксиса метода в выражении запроса</span><span class="sxs-lookup"><span data-stu-id="972f1-186">To use method syntax in a query expression</span></span>  
  
1. <span data-ttu-id="972f1-187">Как описано в разделе [Синтаксис запросов и синтаксис методов в LINQ](./query-syntax-and-method-syntax-in-linq.md), некоторые операции запросов можно выразить, только используя синтаксис метода.</span><span class="sxs-lookup"><span data-stu-id="972f1-187">As described in [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="972f1-188">Представленный ниже код вычисляет общий балл для каждого объекта `Student` в исходной последовательности, а затем применяет метод `Average()` к результатам запроса, чтобы рассчитать средний балл класса.</span><span class="sxs-lookup"><span data-stu-id="972f1-188">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span>
  
     [!code-csharp[csLINQGettingStarted#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#19)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="972f1-189">Преобразование или проецирование в предложение select</span><span class="sxs-lookup"><span data-stu-id="972f1-189">To transform or project in the select clause</span></span>  
  
1. <span data-ttu-id="972f1-190">Запрос очень часто выдает последовательность, элементы которой отличаются от элементов в исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="972f1-190">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="972f1-191">Удалите или закомментируйте предыдущий запрос и цикл выполнения и замените его на представленный ниже код.</span><span class="sxs-lookup"><span data-stu-id="972f1-191">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="972f1-192">Обратите внимание на то, что запрос возвращает последовательность строк (не `Students`), и этот факт отражается в цикле `foreach`.</span><span class="sxs-lookup"><span data-stu-id="972f1-192">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#20)]  
  
2. <span data-ttu-id="972f1-193">Код, представленный выше в этом пошаговом руководстве, показывает, что среднее количество баллов по классу составляет около 334.</span><span class="sxs-lookup"><span data-stu-id="972f1-193">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="972f1-194">Для создания последовательности `Students`, сумма баллов в которой будет выше, чем средний показатель по классу, с указанием `Student ID` можно вставить в оператор `select` анонимный тип:</span><span class="sxs-lookup"><span data-stu-id="972f1-194">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#21)]  
  
## <a name="next-steps"></a><span data-ttu-id="972f1-195">Next Steps</span><span class="sxs-lookup"><span data-stu-id="972f1-195">Next Steps</span></span>  
 <span data-ttu-id="972f1-196">Ознакомившись с основными аспектами работы с запросами в C#, вы будете готовы прочитать документацию и примеры по интересующему вас типу поставщика LINQ:</span><span class="sxs-lookup"><span data-stu-id="972f1-196">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="972f1-197">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="972f1-197">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="972f1-198">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="972f1-198">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="972f1-199">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="972f1-199">LINQ to XML (C#)</span></span>](./linq-to-xml-overview.md)  
  
 [<span data-ttu-id="972f1-200">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="972f1-200">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="972f1-201">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="972f1-201">See also</span></span>

- [<span data-ttu-id="972f1-202">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="972f1-202">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="972f1-203">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="972f1-203">LINQ Query Expressions</span></span>](../../../linq/index.md)
