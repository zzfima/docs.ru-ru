---
title: Связи типов в операциях запроса
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: 8c201abef924766d52b1adb084970a24ebea2b50
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350565"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="d7be9-102">Отношения типов в операциях запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7be9-102">Type Relationships in Query Operations (Visual Basic)</span></span>

<span data-ttu-id="d7be9-103">Переменные, используемые в операциях запроса [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], строго типизированы и должны быть совместимы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="d7be9-103">Variables used in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="d7be9-104">Строгая типизация используется в источнике данных, в самом запросе и в выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="d7be9-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="d7be9-105">На следующем рисунке показаны термины, используемые для описания запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7be9-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="d7be9-106">Дополнительные сведения о частях запроса см. в разделе [основные операции запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="d7be9-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>

![Снимок экрана, показывающий запрос на псевдокод с выделенными элементами.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

<span data-ttu-id="d7be9-108">Тип переменной диапазона в запросе должен быть совместим с типом элементов в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="d7be9-108">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="d7be9-109">Тип переменной запроса должен быть совместим с элементом Sequence, определенным в предложении `Select`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-109">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="d7be9-110">Наконец, тип элементов последовательности также должен быть совместим с типом управляющей переменной цикла, которая используется в инструкции `For Each`, выполняющей запрос.</span><span class="sxs-lookup"><span data-stu-id="d7be9-110">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="d7be9-111">Эта строгая типизация облегчает идентификацию ошибок типа во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="d7be9-111">This strong typing facilitates identification of type errors at compile time.</span></span>

<span data-ttu-id="d7be9-112">Visual Basic обеспечивает строгую типизацию, реализуя вывод локального типа, также называемую *неявной типизацией*.</span><span class="sxs-lookup"><span data-stu-id="d7be9-112">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="d7be9-113">Эта функция используется в предыдущем примере, и вы увидите, что она используется во всех [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] образцах и документации.</span><span class="sxs-lookup"><span data-stu-id="d7be9-113">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] samples and documentation.</span></span> <span data-ttu-id="d7be9-114">В Visual Basic вывод локального типа выполняется просто с помощью инструкции `Dim` без предложения `As`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-114">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="d7be9-115">В следующем примере `city` строго типизирован как строка.</span><span class="sxs-lookup"><span data-stu-id="d7be9-115">In the following example, `city` is strongly typed as a string.</span></span>

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="d7be9-116">Локальное определение типа работает только в том случае, если `Option Infer` имеет значение `On`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-116">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="d7be9-117">Дополнительные сведения см. в разделе [оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d7be9-117">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>

<span data-ttu-id="d7be9-118">Однако даже если в запросе используется определение локального типа, то одни и те же связи типов существуют между переменными в источнике данных, переменной запроса и циклом выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="d7be9-118">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="d7be9-119">При написании [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов или работе с образцами и примерами кода в документации полезно иметь базовое понимание этих отношений типов.</span><span class="sxs-lookup"><span data-stu-id="d7be9-119">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, or working with the samples and code examples in the documentation.</span></span>

<span data-ttu-id="d7be9-120">Может потребоваться указать явный тип для переменной диапазона, которая не соответствует типу, возвращаемому источником данных.</span><span class="sxs-lookup"><span data-stu-id="d7be9-120">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="d7be9-121">Тип переменной диапазона можно указать с помощью предложения `As`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-121">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="d7be9-122">Однако это приводит к ошибке, если преобразование является [узким преобразованием](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) , а `Option Strict` имеет значение `On`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-122">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="d7be9-123">Поэтому рекомендуется выполнить преобразование для значений, полученных из источника данных.</span><span class="sxs-lookup"><span data-stu-id="d7be9-123">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="d7be9-124">Можно преобразовать значения из источника данных в явный тип переменной диапазона с помощью метода <xref:System.Linq.Enumerable.Cast%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7be9-124">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="d7be9-125">Можно также привести значения, выбранные в предложении `Select`, к явному типу, отличному от типа переменной диапазона.</span><span class="sxs-lookup"><span data-stu-id="d7be9-125">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="d7be9-126">Эти моменты показаны в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="d7be9-126">These points are illustrated in the following code.</span></span>

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="d7be9-127">Запросы, возвращающие все элементы исходных данных</span><span class="sxs-lookup"><span data-stu-id="d7be9-127">Queries That Return Entire Elements of the Source Data</span></span>

<span data-ttu-id="d7be9-128">В следующем примере показана [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] операция запроса, возвращающая последовательность элементов, выбранных из исходных данных.</span><span class="sxs-lookup"><span data-stu-id="d7be9-128">The following example shows a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="d7be9-129">Источник, `names`, содержит массив строк, а выходные данные запроса представляют собой последовательность, содержащую строки, начинающиеся с буквы M.</span><span class="sxs-lookup"><span data-stu-id="d7be9-129">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

<span data-ttu-id="d7be9-130">Это эквивалентно следующему коду, но гораздо короче и проще в написании.</span><span class="sxs-lookup"><span data-stu-id="d7be9-130">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="d7be9-131">Использовать определение локального типа в запросах является предпочтительным стилем в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d7be9-131">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

<span data-ttu-id="d7be9-132">В обоих приведенных выше примерах кода существуют следующие связи, независимо от того, определены типы как неявно или явно.</span><span class="sxs-lookup"><span data-stu-id="d7be9-132">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>

1. <span data-ttu-id="d7be9-133">Тип элементов в источнике данных, `names`, является типом переменной диапазона, `name`в запросе.</span><span class="sxs-lookup"><span data-stu-id="d7be9-133">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>

2. <span data-ttu-id="d7be9-134">Тип объекта, выбранного `name`, определяет тип переменной запроса `mNames`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-134">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="d7be9-135">Здесь `name` является строкой, поэтому переменная запроса является IEnumerable (Of String) в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d7be9-135">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>

3. <span data-ttu-id="d7be9-136">Запрос, определенный в `mNames`, выполняется в цикле `For Each`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-136">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="d7be9-137">Цикл выполняет итерацию результата выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="d7be9-137">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="d7be9-138">Поскольку при выполнении `mNames`возвращается последовательность строк, переменная итерации цикла, `nm`, также является строкой.</span><span class="sxs-lookup"><span data-stu-id="d7be9-138">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>

## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="d7be9-139">Запросы, возвращающие одно поле из выбранных элементов</span><span class="sxs-lookup"><span data-stu-id="d7be9-139">Queries That Return One Field from Selected Elements</span></span>

<span data-ttu-id="d7be9-140">В следующем примере показана [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] операция запроса, возвращающая последовательность, содержащую только одну часть каждого элемента, выбранного из источника данных.</span><span class="sxs-lookup"><span data-stu-id="d7be9-140">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="d7be9-141">Запрос принимает коллекцию объектов `Customer` в качестве источника данных и проецирует только свойство `Name` в результате.</span><span class="sxs-lookup"><span data-stu-id="d7be9-141">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="d7be9-142">Поскольку имя клиента является строкой, запрос создает последовательность строк в качестве выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d7be9-142">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim custNames = From cust In customers
                Where cust.City = "London"
                Select cust.Name

For Each custName In custNames
    Console.WriteLine(custName)
Next
```

<span data-ttu-id="d7be9-143">Связи между переменными, как и в более простом примере.</span><span class="sxs-lookup"><span data-stu-id="d7be9-143">The relationships between variables are like those in the simpler example.</span></span>

1. <span data-ttu-id="d7be9-144">Тип элементов в источнике данных, `customers`, является типом переменной диапазона, `cust`в запросе.</span><span class="sxs-lookup"><span data-stu-id="d7be9-144">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="d7be9-145">В этом примере этот тип `Customer`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-145">In this example, that type is `Customer`.</span></span>

2. <span data-ttu-id="d7be9-146">Оператор `Select` возвращает свойство `Name` для каждого объекта `Customer`, а не весь объект.</span><span class="sxs-lookup"><span data-stu-id="d7be9-146">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="d7be9-147">Поскольку `Name` является строкой, переменная запроса `custNames`, снова будет IEnumerable (Of String), а не `Customer`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-147">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>

3. <span data-ttu-id="d7be9-148">Поскольку `custNames` представляет последовательность строк, переменная итерации цикла `For Each`, `custName`, должна быть строкой.</span><span class="sxs-lookup"><span data-stu-id="d7be9-148">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>

<span data-ttu-id="d7be9-149">Без локального определения типа предыдущий пример был бы более громоздким для написания и понимания, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d7be9-149">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()
 Dim custNames As IEnumerable(Of String) =
     From cust As Customer In customers
     Where cust.City = "London"
     Select cust.Name

 For Each custName As String In custNames
     Console.WriteLine(custName)
 Next
```

## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="d7be9-150">Запросы, для которых требуются анонимные типы</span><span class="sxs-lookup"><span data-stu-id="d7be9-150">Queries That Require Anonymous Types</span></span>

<span data-ttu-id="d7be9-151">В следующем примере показана более сложная ситуация.</span><span class="sxs-lookup"><span data-stu-id="d7be9-151">The following example shows a more complex situation.</span></span> <span data-ttu-id="d7be9-152">В предыдущем примере было неудобно указывать типы для всех переменных явным образом.</span><span class="sxs-lookup"><span data-stu-id="d7be9-152">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="d7be9-153">В этом примере это невозможно.</span><span class="sxs-lookup"><span data-stu-id="d7be9-153">In this example, it is impossible.</span></span> <span data-ttu-id="d7be9-154">Вместо выбора целых `Customer` элементов из источника данных или одного поля из каждого элемента, предложение `Select` в этом запросе возвращает два свойства исходного объекта `Customer`: `Name` и `City`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-154">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="d7be9-155">В ответ на предложение `Select` компилятор определяет анонимный тип, содержащий эти два свойства.</span><span class="sxs-lookup"><span data-stu-id="d7be9-155">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="d7be9-156">Результатом выполнения `nameCityQuery` в цикле `For Each` является коллекция экземпляров нового анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="d7be9-156">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="d7be9-157">Так как анонимный тип не имеет имени для использования, нельзя указать тип `nameCityQuery` или `custInfo` явным образом.</span><span class="sxs-lookup"><span data-stu-id="d7be9-157">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="d7be9-158">То есть анонимный тип не имеет имени типа, используемого вместо `String` в `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-158">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="d7be9-159">Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="d7be9-159">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim nameCityQuery = From cust In customers
                    Where cust.City = "London"
                    Select cust.Name, cust.City

For Each custInfo In nameCityQuery
    Console.WriteLine(custInfo.Name)
Next
```

<span data-ttu-id="d7be9-160">Хотя невозможно указать типы для всех переменных в предыдущем примере, связи остаются неизменными.</span><span class="sxs-lookup"><span data-stu-id="d7be9-160">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>

1. <span data-ttu-id="d7be9-161">Тип элементов в источнике данных опять является типом переменной диапазона в запросе.</span><span class="sxs-lookup"><span data-stu-id="d7be9-161">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="d7be9-162">В этом примере `cust` является экземпляром `Customer`.</span><span class="sxs-lookup"><span data-stu-id="d7be9-162">In this example, `cust` is an instance of `Customer`.</span></span>

2. <span data-ttu-id="d7be9-163">Поскольку оператор `Select` создает анонимный тип, переменная запроса `nameCityQuery`должна быть неявно типизирована как анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="d7be9-163">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="d7be9-164">Анонимный тип не имеет имени и поэтому не может быть указан явным образом.</span><span class="sxs-lookup"><span data-stu-id="d7be9-164">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>

3. <span data-ttu-id="d7be9-165">Тип переменной итерации в цикле `For Each` — это анонимный тип, созданный на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="d7be9-165">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="d7be9-166">Поскольку тип не имеет пригодного для использования имени, тип переменной итерации цикла должен быть определен неявно.</span><span class="sxs-lookup"><span data-stu-id="d7be9-166">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7be9-167">См. также</span><span class="sxs-lookup"><span data-stu-id="d7be9-167">See also</span></span>

- [<span data-ttu-id="d7be9-168">Приступая к работе с LINQ в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7be9-168">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="d7be9-169">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="d7be9-169">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="d7be9-170">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="d7be9-170">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- <span data-ttu-id="d7be9-171">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7be9-171">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="d7be9-172">LINQ</span><span class="sxs-lookup"><span data-stu-id="d7be9-172">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="d7be9-173">Запросы</span><span class="sxs-lookup"><span data-stu-id="d7be9-173">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
