---
title: "Динамическое определение фильтров предикатов во время выполнения"
description: "Динамическое определение фильтров предикатов во время выполнения."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e724428bce09e2b2fa20b9391ad131424e16413
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="bc289-104">Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="bc289-104">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="bc289-105">В некоторых случаях количество предикатов, которые нужно применить к исходным элементам в предложении `where`, неизвестно вплоть до времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc289-105">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="bc289-106">Одним из способов динамического определения сразу нескольких фильтров предикатов служит метод <xref:System.Linq.Enumerable.Contains%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bc289-106">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="bc289-107">Пример конструируется двумя способами.</span><span class="sxs-lookup"><span data-stu-id="bc289-107">The example is constructed in two ways.</span></span> <span data-ttu-id="bc289-108">Во-первых, проект запускается в результате применения фильтра к предоставленным в программе значениям.</span><span class="sxs-lookup"><span data-stu-id="bc289-108">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="bc289-109">Затем проект запускается снова, когда применяются данные, введенные в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc289-109">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="bc289-110">Фильтрование с помощью метода Contains</span><span class="sxs-lookup"><span data-stu-id="bc289-110">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="bc289-111">Откройте новое консольное приложение и присвойте ему имя `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="bc289-111">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="bc289-112">Скопируйте класс `StudentClass` из окна [Запрос коллекции объектов](query-a-collection-of-objects.md) и вставьте его в пространство имен `PredicateFilters` под классом `Program`.</span><span class="sxs-lookup"><span data-stu-id="bc289-112">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="bc289-113">`StudentClass` предоставляет список объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="bc289-113">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="bc289-114">Закомментируйте метод `Main` в `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="bc289-114">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="bc289-115">Замените класс `Program` на следующий код.</span><span class="sxs-lookup"><span data-stu-id="bc289-115">Replace class `Program` with the following code.</span></span>  
  
     <span data-ttu-id="bc289-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc289-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span></span>  
  
5.  <span data-ttu-id="bc289-117">Добавьте в метод `Main` в классе `DynamicPredicates` следующую строку под объявлением `ids`.</span><span class="sxs-lookup"><span data-stu-id="bc289-117">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="bc289-118">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="bc289-118">Run the project.</span></span>  
  
7.  <span data-ttu-id="bc289-119">В консольном окне отобразятся следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="bc289-119">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="bc289-120">Гарсия: 114</span><span class="sxs-lookup"><span data-stu-id="bc289-120">Garcia: 114</span></span>  
  
     <span data-ttu-id="bc289-121">О'Доннелл: 112</span><span class="sxs-lookup"><span data-stu-id="bc289-121">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="bc289-122">Омельченко: 111</span><span class="sxs-lookup"><span data-stu-id="bc289-122">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="bc289-123">Следующим шагом станет повторный запуск проекта, на этот раз с данными, введенными в среде выполнения, а не с массивом `ids`.</span><span class="sxs-lookup"><span data-stu-id="bc289-123">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="bc289-124">В методе `Main` измените `QueryByID(ids)` на `QueryByID(args)`.</span><span class="sxs-lookup"><span data-stu-id="bc289-124">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="bc289-125">Запустите проект с аргументами командной строки `122 117 120 115`.</span><span class="sxs-lookup"><span data-stu-id="bc289-125">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="bc289-126">Когда проект будет запущен, эти значения станут элементами `args`, параметра метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="bc289-126">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="bc289-127">В консольном окне отобразятся следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="bc289-127">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="bc289-128">Адамс: 120</span><span class="sxs-lookup"><span data-stu-id="bc289-128">Adams: 120</span></span>  
  
     <span data-ttu-id="bc289-129">Фенг: 117</span><span class="sxs-lookup"><span data-stu-id="bc289-129">Feng: 117</span></span>  
  
     <span data-ttu-id="bc289-130">Гарсия: 115</span><span class="sxs-lookup"><span data-stu-id="bc289-130">Garcia: 115</span></span>  
  
     <span data-ttu-id="bc289-131">Такер: 122</span><span class="sxs-lookup"><span data-stu-id="bc289-131">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="bc289-132">Фильтрование с помощью оператора switch</span><span class="sxs-lookup"><span data-stu-id="bc289-132">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="bc289-133">Оператор `switch` позволяет выбрать один из предустановленных альтернативных запросов.</span><span class="sxs-lookup"><span data-stu-id="bc289-133">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="bc289-134">В следующем примере `studentQuery` использует другое предложение `where`, в зависимости от того, какой уровень оценок или год указан в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc289-134">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="bc289-135">Скопируйте следующий метод и вставьте его в класс `DynamicPredicates`.</span><span class="sxs-lookup"><span data-stu-id="bc289-135">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     <span data-ttu-id="bc289-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc289-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span></span>  
  
3.  <span data-ttu-id="bc289-137">В методе `Main` замените вызов `QueryByID` на следующий вызов, который отправляет первый элемент из массива `args` как аргумент: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="bc289-137">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="bc289-138">Запустите проект с помощью аргумента командной строки, выраженного целочисленным значением от 1 до 4.</span><span class="sxs-lookup"><span data-stu-id="bc289-138">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="bc289-139">См. также</span><span class="sxs-lookup"><span data-stu-id="bc289-139">See Also</span></span>  
 <span data-ttu-id="bc289-140">[Выражения запросов LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="bc289-140">[LINQ Query Expressions](index.md) </span></span>  
 [<span data-ttu-id="bc289-141">предложение where</span><span class="sxs-lookup"><span data-stu-id="bc289-141">where clause</span></span>](../language-reference/keywords/where-clause.md)

