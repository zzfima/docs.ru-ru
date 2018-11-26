---
title: Динамическое определение фильтров предикатов во время выполнения (LINQ в C#)
description: Узнайте, как выполнять динамическое определение фильтров предикатов во время выполнения с помощью LINQ в C#.
ms.date: 12/1/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: ece5940edd615f30acab06a429de300e27811a66
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296078"
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="be8d4-103">Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="be8d4-103">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="be8d4-104">В некоторых случаях количество предикатов, которые нужно применить к исходным элементам в предложении `where`, неизвестно вплоть до времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="be8d4-104">In some cases, you don't know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="be8d4-105">Одним из способов динамического определения сразу нескольких фильтров предикатов служит метод <xref:System.Linq.Enumerable.Contains%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="be8d4-105">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="be8d4-106">Пример конструируется двумя способами.</span><span class="sxs-lookup"><span data-stu-id="be8d4-106">The example is constructed in two ways.</span></span> <span data-ttu-id="be8d4-107">Во-первых, проект запускается в результате применения фильтра к предоставленным в программе значениям.</span><span class="sxs-lookup"><span data-stu-id="be8d4-107">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="be8d4-108">Затем проект запускается снова, когда применяются данные, введенные в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="be8d4-108">Then the project is run again by using input provided at run time.</span></span>

## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="be8d4-109">Фильтрование с помощью метода Contains</span><span class="sxs-lookup"><span data-stu-id="be8d4-109">To filter by using the Contains method</span></span>

1. <span data-ttu-id="be8d4-110">Откройте новое консольное приложение и присвойте ему имя `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-110">Open a new console application and name it `PredicateFilters`.</span></span>

2. <span data-ttu-id="be8d4-111">Скопируйте класс `StudentClass` из окна [Запрос коллекции объектов](query-a-collection-of-objects.md) и вставьте его в пространство имен `PredicateFilters` под классом `Program`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-111">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="be8d4-112">`StudentClass` предоставляет список объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-112">`StudentClass` provides a list of `Student` objects.</span></span>

3. <span data-ttu-id="be8d4-113">Закомментируйте метод `Main` в `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-113">Comment out the `Main` method in `StudentClass`.</span></span>

4. <span data-ttu-id="be8d4-114">Замените класс `Program` на следующий код:</span><span class="sxs-lookup"><span data-stu-id="be8d4-114">Replace class `Program` with the following code:</span></span>

     [!code-csharp[csProgGuideLINQ#26](~/samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]

5. <span data-ttu-id="be8d4-115">Добавьте в метод `Main` в классе `DynamicPredicates` следующую строку под объявлением `ids`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-115">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>

     ```csharp
     QueryById(ids);
     ```

6. <span data-ttu-id="be8d4-116">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="be8d4-116">Run the project.</span></span>

7. <span data-ttu-id="be8d4-117">В консольном окне отобразятся следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="be8d4-117">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="be8d4-118">Гарсия: 114</span><span class="sxs-lookup"><span data-stu-id="be8d4-118">Garcia: 114</span></span>

     <span data-ttu-id="be8d4-119">О'Доннелл: 112</span><span class="sxs-lookup"><span data-stu-id="be8d4-119">O'Donnell: 112</span></span>

     <span data-ttu-id="be8d4-120">Омельченко: 111</span><span class="sxs-lookup"><span data-stu-id="be8d4-120">Omelchenko: 111</span></span>

8. <span data-ttu-id="be8d4-121">Следующим шагом станет повторный запуск проекта, на этот раз с данными, введенными в среде выполнения, а не с массивом `ids`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-121">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="be8d4-122">В методе `Main` измените `QueryByID(ids)` на `QueryByID(args)`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-122">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>

9. <span data-ttu-id="be8d4-123">Запустите проект с аргументами командной строки `122 117 120 115`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-123">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="be8d4-124">Когда проект будет запущен, эти значения станут элементами `args` — параметра метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-124">When the project is run, those values become elements of `args`, the parameter of the `Main` method.</span></span>

10. <span data-ttu-id="be8d4-125">В консольном окне отобразятся следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="be8d4-125">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="be8d4-126">Адамс: 120</span><span class="sxs-lookup"><span data-stu-id="be8d4-126">Adams: 120</span></span>

     <span data-ttu-id="be8d4-127">Фенг: 117</span><span class="sxs-lookup"><span data-stu-id="be8d4-127">Feng: 117</span></span>

     <span data-ttu-id="be8d4-128">Гарсия: 115</span><span class="sxs-lookup"><span data-stu-id="be8d4-128">Garcia: 115</span></span>

     <span data-ttu-id="be8d4-129">Такер: 122</span><span class="sxs-lookup"><span data-stu-id="be8d4-129">Tucker: 122</span></span>

## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="be8d4-130">Фильтрование с помощью оператора switch</span><span class="sxs-lookup"><span data-stu-id="be8d4-130">To filter by using a switch statement</span></span>

1. <span data-ttu-id="be8d4-131">Оператор `switch` позволяет выбрать один из предустановленных альтернативных запросов.</span><span class="sxs-lookup"><span data-stu-id="be8d4-131">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="be8d4-132">В следующем примере `studentQuery` использует другое предложение `where`, в зависимости от того, какой уровень оценок или год указан в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="be8d4-132">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>

2. <span data-ttu-id="be8d4-133">Скопируйте следующий метод и вставьте его в класс `DynamicPredicates`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-133">Copy the following method and paste it into class `DynamicPredicates`.</span></span>

     [!code-csharp[csProgGuideLINQ#27](~/samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]

3. <span data-ttu-id="be8d4-134">В методе `Main` замените вызов `QueryByID` на следующий вызов, который отправляет первый элемент из массива `args` как аргумент: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="be8d4-134">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>

4. <span data-ttu-id="be8d4-135">Запустите проект с помощью аргумента командной строки, выраженного целочисленным значением от 1 до 4.</span><span class="sxs-lookup"><span data-stu-id="be8d4-135">Run the project with a command line argument of an integer value between 1 and 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="be8d4-136">См. также</span><span class="sxs-lookup"><span data-stu-id="be8d4-136">See also</span></span>

- [<span data-ttu-id="be8d4-137">LINQ</span><span class="sxs-lookup"><span data-stu-id="be8d4-137">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="be8d4-138">предложение where</span><span class="sxs-lookup"><span data-stu-id="be8d4-138">where clause</span></span>](../language-reference/keywords/where-clause.md)
