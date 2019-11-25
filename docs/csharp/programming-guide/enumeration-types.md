---
title: Руководство по программированию на C#. Типы перечислений
ms.custom: seodec18
ms.date: 09/10/2017
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
ms.openlocfilehash: 3573959a1e10b475a9867631767de5d10a08b9ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969766"
---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="cf719-102">Типы перечислений (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="cf719-102">Enumeration types (C# Programming Guide)</span></span>

<span data-ttu-id="cf719-103">Тип перечисления (называемый также перечислением) предоставляет эффективный способ определения набора именованных целочисленных констант, который можно назначить переменной.</span><span class="sxs-lookup"><span data-stu-id="cf719-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="cf719-104">Например, предположим, что нужно определить переменную, значение которого должно представлять день недели.</span><span class="sxs-lookup"><span data-stu-id="cf719-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="cf719-105">Имеется только семь имеющих смысл значений, которые может принимать переменная.</span><span class="sxs-lookup"><span data-stu-id="cf719-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="cf719-106">Для определения этих значений можно использовать тип перечисления, который объявлен с помощью ключевого слова [enum](../language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="cf719-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../language-reference/keywords/enum.md) keyword.</span></span>

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

<span data-ttu-id="cf719-107">По умолчанию базовым типом каждого элемента перечисления является [int](../language-reference/builtin-types/integral-numeric-types.md). Можно задать другой целочисленный тип, используя двоеточие, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="cf719-107">By default the underlying type of each element in the enum is [int](../language-reference/builtin-types/integral-numeric-types.md). You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="cf719-108">Полный список возможных типов см. в разделе [enum (справочник по C#)](../language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="cf719-108">For a full list of possible types, see [enum (C# Reference)](../language-reference/keywords/enum.md).</span></span>

<span data-ttu-id="cf719-109">Чтобы проверить основные числовые значения путем приведения в базовый тип, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="cf719-109">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

<span data-ttu-id="cf719-110">Далее указаны преимущества использования enum вместо числового типа.</span><span class="sxs-lookup"><span data-stu-id="cf719-110">The following are advantages of using an enum instead of a numeric type:</span></span>

- <span data-ttu-id="cf719-111">Для клиентского кода ясно задается, какие значения допустимы для переменной.</span><span class="sxs-lookup"><span data-stu-id="cf719-111">You clearly specify for client code which values are valid for the variable.</span></span>

- <span data-ttu-id="cf719-112">В Visual Studio IntelliSense выводит список определенных значений.</span><span class="sxs-lookup"><span data-stu-id="cf719-112">In Visual Studio, IntelliSense lists the defined values.</span></span>

<span data-ttu-id="cf719-113">Если не указать значения этих элементов в списке перечислителя, значения будут автоматически увеличиваться на 1.</span><span class="sxs-lookup"><span data-stu-id="cf719-113">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="cf719-114">В предыдущем примере `Day.Sunday` имеет значение 0, `Day.Monday` имеет значение 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="cf719-114">In the previous example, `Day.Sunday` has a value of 0, `Day.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="cf719-115">Когда создается новый объект `Day`, он будет иметь значение по умолчанию `Day.Sunday` (0), только ему явно не присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="cf719-115">When you create a new `Day` object, it will have a default value of `Day.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="cf719-116">При создании перечисления выберите наиболее логичное используемое по умолчанию значение и присвойте ему значение нуль.</span><span class="sxs-lookup"><span data-stu-id="cf719-116">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="cf719-117">В результате этого все перечисления, если при их создании им явно не задать значение, будут иметь по умолчанию это значение.</span><span class="sxs-lookup"><span data-stu-id="cf719-117">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>

<span data-ttu-id="cf719-118">Если переменная `meetingDay` имеет тип `Day`, ей можно (без явного приведения) присвоить только одно из значений, определенных в `Day`.</span><span class="sxs-lookup"><span data-stu-id="cf719-118">If the variable `meetingDay` is of type `Day`, then (without an explicit cast) you can only assign it one of the values defined by `Day`.</span></span> <span data-ttu-id="cf719-119">И если день встречи изменяется, можно назначить новое значение из `Day` переменной `meetingDay`:</span><span class="sxs-lookup"><span data-stu-id="cf719-119">And if the meeting day changes, you can assign a new value from `Day` to `meetingDay`:</span></span>

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> <span data-ttu-id="cf719-120">Переменной `meetingDay` можно присвоить любое произвольное целое значение.</span><span class="sxs-lookup"><span data-stu-id="cf719-120">It's possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="cf719-121">Например, эта строка кода не создает ошибку: `meetingDay = (Day) 42`.</span><span class="sxs-lookup"><span data-stu-id="cf719-121">For example, this line of code does not produce an error: `meetingDay = (Day) 42`.</span></span> <span data-ttu-id="cf719-122">Но этого делать нельзя, поскольку неявно ожидается, что переменная перечисления принимает одно из значений, определяемых перечислением.</span><span class="sxs-lookup"><span data-stu-id="cf719-122">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="cf719-123">Присвоение переменной типа перечисления произвольного значения связано с большим риском возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="cf719-123">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>

<span data-ttu-id="cf719-124">Элементам списка перечислителя типа перечисления можно присвоить любые значения, и можно также использовать вычисленные значения:</span><span class="sxs-lookup"><span data-stu-id="cf719-124">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="cf719-125">Типы перечислений как битовые флаги</span><span class="sxs-lookup"><span data-stu-id="cf719-125">Enumeration types as bit flags</span></span>

<span data-ttu-id="cf719-126">Тип перечисления можно использовать для определения битовых флагов, благодаря чему экземпляр типа перечисления может хранить любую комбинацию значений, определенных в списке перечислителя.</span><span class="sxs-lookup"><span data-stu-id="cf719-126">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="cf719-127">(Конечно, некоторые комбинации могут не иметь смысла или быть недопустимы в коде программы.)</span><span class="sxs-lookup"><span data-stu-id="cf719-127">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>

<span data-ttu-id="cf719-128">Чтобы создать перечисление битовых флагов, нужно применить атрибут <xref:System.FlagsAttribute?displayProperty=nameWithType> и определить значения так, чтобы для них могли выполняться битовые операции `AND`, `OR`, `NOT` и `XOR`.</span><span class="sxs-lookup"><span data-stu-id="cf719-128">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="cf719-129">В перечисление битовых флагов включите именованную константу с нулевым значением, что означает "флаги не установлены".</span><span class="sxs-lookup"><span data-stu-id="cf719-129">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="cf719-130">Не придавайте флагу нулевое значение, если оно не означает "флаги не установлены".</span><span class="sxs-lookup"><span data-stu-id="cf719-130">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>

<span data-ttu-id="cf719-131">В следующем примере определена другая версия перечисления `Day`, которая называется `Days`.</span><span class="sxs-lookup"><span data-stu-id="cf719-131">In the following example, another version of the `Day` enum, which is named `Days`, is defined.</span></span> <span data-ttu-id="cf719-132">У `Days` имеется атрибут `Flags`, и каждому значению присваивается следующая степень числа 2.</span><span class="sxs-lookup"><span data-stu-id="cf719-132">`Days` has the `Flags` attribute, and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="cf719-133">Это позволяет создать переменную `Days` со значением `Days.Tuesday | Days.Thursday`.</span><span class="sxs-lookup"><span data-stu-id="cf719-133">This enables you to create a `Days` variable whose value is `Days.Tuesday | Days.Thursday`.</span></span>

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

<span data-ttu-id="cf719-134">Чтобы установить флаг на перечислении, используйте побитовый оператор `OR`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cf719-134">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

<span data-ttu-id="cf719-135">Чтобы определить, установлен ли конкретный флаг, используйте побитовый оператор `AND`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cf719-135">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

<span data-ttu-id="cf719-136">Дополнительные сведения о том, что необходимо учитывать при определении типов перечислений при помощи атрибута <xref:System.FlagsAttribute?displayProperty=nameWithType>, см. в статье <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cf719-136">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="cf719-137">Использование методов System.Enum для получения и обработки значений перечисления</span><span class="sxs-lookup"><span data-stu-id="cf719-137">Using the System.Enum methods to discover and manipulate enum values</span></span>

<span data-ttu-id="cf719-138">Все перечисления являются экземплярами типа <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cf719-138">All enums are instances of the <xref:System.Enum?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="cf719-139">Нельзя унаследовать новые классы от класса <xref:System.Enum?displayProperty=nameWithType>, но можно использовать его методы для получения и изменения данных об экземпляре перечисления.</span><span class="sxs-lookup"><span data-stu-id="cf719-139">You cannot derive new classes from <xref:System.Enum?displayProperty=nameWithType>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

<span data-ttu-id="cf719-140">Дополнительные сведения можно найти по адресу: <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cf719-140">For more information, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="cf719-141">Можно также создать для перечисления новый метод, используя метод расширения.</span><span class="sxs-lookup"><span data-stu-id="cf719-141">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="cf719-142">Дополнительные сведения см. в разделе [Практическое руководство. Создание нового метода для перечисления](./classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="cf719-142">For more information, see [How to create a new method for an enumeration](./classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf719-143">См. также</span><span class="sxs-lookup"><span data-stu-id="cf719-143">See also</span></span>

- <xref:System.Enum?displayProperty=nameWithType>
- [<span data-ttu-id="cf719-144">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cf719-144">C# Programming Guide</span></span>](./index.md)
- [<span data-ttu-id="cf719-145">enum</span><span class="sxs-lookup"><span data-stu-id="cf719-145">enum</span></span>](../language-reference/keywords/enum.md)
