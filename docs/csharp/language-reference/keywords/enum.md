---
title: Ключевое слово enum. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 639a3a01c9c4da13e0212bd0230acbd2af170b25
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428521"
---
# <a name="enum-c-reference"></a><span data-ttu-id="21085-102">enum (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="21085-102">enum (C# Reference)</span></span>

<span data-ttu-id="21085-103">Ключевое слово `enum` используется для объявления перечисления — отдельного типа, который состоит из набора именованных констант, называемого списком перечислителей.</span><span class="sxs-lookup"><span data-stu-id="21085-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>

<span data-ttu-id="21085-104">Обычно лучше всего определять перечисление непосредственно в пространстве имен, чтобы всем классам в пространстве имен было одинаково удобно обращаться к нему.</span><span class="sxs-lookup"><span data-stu-id="21085-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="21085-105">Однако перечисление также может быть вложенным в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="21085-105">However, an enum can also be nested within a class or struct.</span></span>

<span data-ttu-id="21085-106">По умолчанию первый перечислитель имеет значение 0, и значение каждого последующего перечислителя увеличивается на 1.</span><span class="sxs-lookup"><span data-stu-id="21085-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="21085-107">Например, в следующем перечислении `Sat` — `0`, `Sun` — `1`, `Mon` — `2`и т. д.</span><span class="sxs-lookup"><span data-stu-id="21085-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>

```csharp
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="21085-108">Перечисления могут использовать инициализаторы для переопределения значений по умолчанию, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="21085-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>

```csharp
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="21085-109">В этом перечислении последовательность элементов принудительно начинается с `1` вместо `0`.</span><span class="sxs-lookup"><span data-stu-id="21085-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="21085-110">Тем не менее рекомендуется включать константу, которая имеет значение "0".</span><span class="sxs-lookup"><span data-stu-id="21085-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="21085-111">Дополнительные сведения см. в разделе [Типы перечислений](../../programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="21085-111">For more information, see [Enumeration Types](../../programming-guide/enumeration-types.md).</span></span>

<span data-ttu-id="21085-112">Каждый тип перечисления имеет базовый тип, который может быть любым [целочисленным типом](../builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="21085-112">Every enumeration type has an underlying type, which can be any [integral numeric type](../builtin-types/integral-numeric-types.md).</span></span> <span data-ttu-id="21085-113">Тип [char](../builtin-types/char.md) не может быть базовым типом перечисления.</span><span class="sxs-lookup"><span data-stu-id="21085-113">The [char](../builtin-types/char.md) type cannot be an underlying type of an enum.</span></span> <span data-ttu-id="21085-114">Базовым типом перечисления элементов по умолчанию является [int](../builtin-types/integral-numeric-types.md). Чтобы объявить перечисление другого целого типа, например [byte](../builtin-types/integral-numeric-types.md), используется двоеточие после идентификатора, за которым следует тип, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="21085-114">The default underlying type of enumeration elements is [int](../builtin-types/integral-numeric-types.md). To declare an enum of another integral type, such as [byte](../builtin-types/integral-numeric-types.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>

```csharp
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="21085-115">Переменной типа "перечисление" может быть присвоено любое значение в диапазоне базового типа. Эти значения не ограничиваются именованными константами.</span><span class="sxs-lookup"><span data-stu-id="21085-115">A variable of an enumeration type can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>

<span data-ttu-id="21085-116">Значение по умолчанию `enum E` является значением, полученным с помощью выражения `(E)0`.</span><span class="sxs-lookup"><span data-stu-id="21085-116">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>

> [!NOTE]
> <span data-ttu-id="21085-117">Перечислитель не может содержать пробелы в имени.</span><span class="sxs-lookup"><span data-stu-id="21085-117">An enumerator cannot contain white space in its name.</span></span>

<span data-ttu-id="21085-118">Базовый тип указывает, какой объем хранилища выделяется для каждого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="21085-118">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="21085-119">Тем не менее необходимо явное приведение, чтобы преобразовывать из типа `enum` в целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="21085-119">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="21085-120">Например, следующий оператор назначает перечислитель `Sun` для переменной типа [int](../builtin-types/integral-numeric-types.md) с помощью приведения, чтобы преобразовать `enum` в `int`.</span><span class="sxs-lookup"><span data-stu-id="21085-120">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](../builtin-types/integral-numeric-types.md) by using a cast to convert from `enum` to `int`.</span></span>

```csharp
int x = (int)Day.Sun;
```

<span data-ttu-id="21085-121">При применении <xref:System.FlagsAttribute?displayProperty=nameWithType> к перечислению, содержащему элементы, которые могут быть объединены с помощью побитовой операции `OR` , атрибут влияет на поведение `enum` при использовании с некоторыми средствами.</span><span class="sxs-lookup"><span data-stu-id="21085-121">When you apply <xref:System.FlagsAttribute?displayProperty=nameWithType> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="21085-122">Эти изменения можно заметить при использовании таких средств, как методы класса <xref:System.Console> и вычислитель выражений.</span><span class="sxs-lookup"><span data-stu-id="21085-122">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="21085-123">(См. третий пример.)</span><span class="sxs-lookup"><span data-stu-id="21085-123">(See the third example.)</span></span>

## <a name="robust-programming"></a><span data-ttu-id="21085-124">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="21085-124">Robust programming</span></span>

<span data-ttu-id="21085-125">Как и в случае с любой другой константой, все ссылки на отдельные значения перечисления преобразуются в числовые литералы во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="21085-125">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="21085-126">Это может создать потенциальные проблемы с управлением версиями, как описано в разделе [Константы](../../programming-guide/classes-and-structs/constants.md).</span><span class="sxs-lookup"><span data-stu-id="21085-126">This can create potential versioning issues as described in [Constants](../../programming-guide/classes-and-structs/constants.md).</span></span>

<span data-ttu-id="21085-127">Назначение дополнительных значений для новых версий перечислений или изменение значений элементов перечислений в новой версии может вызвать проблемы в зависимом исходном коде.</span><span class="sxs-lookup"><span data-stu-id="21085-127">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="21085-128">Значения перечислений часто используются в инструкциях [switсh](switch.md) .</span><span class="sxs-lookup"><span data-stu-id="21085-128">Enum values often are used in [switch](switch.md) statements.</span></span> <span data-ttu-id="21085-129">Если были добавлены дополнительные элементы для типа `enum` , раздел по умолчанию инструкции switch может быть выбран неожиданным образом.</span><span class="sxs-lookup"><span data-stu-id="21085-129">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>

<span data-ttu-id="21085-130">Если другие разработчики используют ваш код, необходимо предоставить рекомендации о том, как их код должен реагировать при добавлении новых элементов к любому типу `enum` .</span><span class="sxs-lookup"><span data-stu-id="21085-130">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>

## <a name="example"></a><span data-ttu-id="21085-131">Пример</span><span class="sxs-lookup"><span data-stu-id="21085-131">Example</span></span>

<span data-ttu-id="21085-132">В следующем примере объявлено перечисление `Day`.</span><span class="sxs-lookup"><span data-stu-id="21085-132">In the following example, an enumeration, `Day`, is declared.</span></span> <span data-ttu-id="21085-133">Два перечислителя явно преобразуются в целое число и назначаются для целочисленных переменных.</span><span class="sxs-lookup"><span data-stu-id="21085-133">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>

[!code-csharp[csrefKeywordsTypes#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#10)]

## <a name="example"></a><span data-ttu-id="21085-134">Пример</span><span class="sxs-lookup"><span data-stu-id="21085-134">Example</span></span>

<span data-ttu-id="21085-135">В следующем примере используется параметр базового типа для объявления `enum` , члены которого имеют тип `long`.</span><span class="sxs-lookup"><span data-stu-id="21085-135">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="21085-136">Обратите внимание, что, даже если базовый тип перечисления является `long`, члены перечисления по-прежнему должны быть явно преобразованы в тип `long` с помощью приведения.</span><span class="sxs-lookup"><span data-stu-id="21085-136">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>

[!code-csharp[csrefKeywordsTypes#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#11)]

## <a name="example"></a><span data-ttu-id="21085-137">Пример</span><span class="sxs-lookup"><span data-stu-id="21085-137">Example</span></span>

<span data-ttu-id="21085-138">В следующем примере кода показано использование и влияние атрибута <xref:System.FlagsAttribute?displayProperty=nameWithType> на объявление `enum` .</span><span class="sxs-lookup"><span data-stu-id="21085-138">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute on an `enum` declaration.</span></span>

[!code-csharp[csrefKeywordsTypes#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#12)]

## <a name="comments"></a><span data-ttu-id="21085-139">Комментарии</span><span class="sxs-lookup"><span data-stu-id="21085-139">Comments</span></span>

<span data-ttu-id="21085-140">Если удалить `Flags`, в примере будут показаны следующие значения.</span><span class="sxs-lookup"><span data-stu-id="21085-140">If you remove `Flags`, the example displays the following values:</span></span>

`5`

`5`

## <a name="c-language-specification"></a><span data-ttu-id="21085-141">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="21085-141">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="21085-142">См. также</span><span class="sxs-lookup"><span data-stu-id="21085-142">See also</span></span>

- [<span data-ttu-id="21085-143">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="21085-143">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="21085-144">Типы перечисления</span><span class="sxs-lookup"><span data-stu-id="21085-144">Enumeration Types</span></span>](../../programming-guide/enumeration-types.md)
- [<span data-ttu-id="21085-145">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="21085-145">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="21085-146">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="21085-146">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="21085-147">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="21085-147">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="21085-148">Соглашения об именовании перечислений</span><span class="sxs-lookup"><span data-stu-id="21085-148">Enum Naming Conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
