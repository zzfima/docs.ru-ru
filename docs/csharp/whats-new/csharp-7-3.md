---
title: Что нового в C# 7.3
description: Обзор новых возможностей в C# 7.3
ms.date: 05/16/2018
ms.openlocfilehash: ba4cea302d91b395e88940d087fcaed306920840
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204559"
---
# <a name="whats-new-in-c-73"></a><span data-ttu-id="8da54-103">Что нового в C# 7.3</span><span class="sxs-lookup"><span data-stu-id="8da54-103">What's new in C# 7.3</span></span>

<span data-ttu-id="8da54-104">Новые возможности в выпуске C# 7.3 можно разделить на две основные группы.</span><span class="sxs-lookup"><span data-stu-id="8da54-104">There are two main themes to the C# 7.3 release.</span></span> <span data-ttu-id="8da54-105">Одна из них — набор функций для повышения эффективности безопасного кода до уровня небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="8da54-105">One theme provides features that enable safe code to be as performant as unsafe code.</span></span> <span data-ttu-id="8da54-106">Вторая — постепенные улучшения существующих функций.</span><span class="sxs-lookup"><span data-stu-id="8da54-106">The second theme provides incremental improvements to existing features.</span></span> <span data-ttu-id="8da54-107">Кроме того, в этом выпуске добавлены новые параметры компилятора.</span><span class="sxs-lookup"><span data-stu-id="8da54-107">In addition, new compiler options were added in this release.</span></span>

<span data-ttu-id="8da54-108">В ту группу, которая отвечает за повышение производительности безопасного кода, входят следующие новые возможности:</span><span class="sxs-lookup"><span data-stu-id="8da54-108">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="8da54-109">доступ к полям фиксированной ширины без закрепления;</span><span class="sxs-lookup"><span data-stu-id="8da54-109">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="8da54-110">возможность переназначать локальные переменные `ref`;</span><span class="sxs-lookup"><span data-stu-id="8da54-110">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="8da54-111">возможность использовать инициализаторы для массивов `stackalloc`;</span><span class="sxs-lookup"><span data-stu-id="8da54-111">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="8da54-112">возможность использовать инструкции `fixed` с любым типом, который поддерживает шаблон;</span><span class="sxs-lookup"><span data-stu-id="8da54-112">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="8da54-113">возможность использовать дополнительные универсальные ограничения.</span><span class="sxs-lookup"><span data-stu-id="8da54-113">You can use additional generic constraints.</span></span>

<span data-ttu-id="8da54-114">Для существующих функций предоставлены следующие улучшения:</span><span class="sxs-lookup"><span data-stu-id="8da54-114">The following enhancements were made to existing features:</span></span>

- <span data-ttu-id="8da54-115">возможность проверить `==` и `!=` с типами кортежа;</span><span class="sxs-lookup"><span data-stu-id="8da54-115">You can test `==` and `!=` with tuple types.</span></span>
- <span data-ttu-id="8da54-116">больше мест для использование переменных выражений;</span><span class="sxs-lookup"><span data-stu-id="8da54-116">You can use expression variables in more locations.</span></span>
- <span data-ttu-id="8da54-117">возможность подключить атрибуты к резервному полю автоматически реализуемых свойств;</span><span class="sxs-lookup"><span data-stu-id="8da54-117">You may attach attributes to the backing field of auto-implemented properties.</span></span>
- <span data-ttu-id="8da54-118">улучшенное разрешение методов, аргументы которых отличаются модификатором `in`;</span><span class="sxs-lookup"><span data-stu-id="8da54-118">Method resolution when arguments differ by `in` has been improved.</span></span>
- <span data-ttu-id="8da54-119">стало меньше неоднозначных вариантов при разрешении перегрузок.</span><span class="sxs-lookup"><span data-stu-id="8da54-119">Overload resolution now has fewer ambiguous cases.</span></span>

<span data-ttu-id="8da54-120">Новые параметры компилятора:</span><span class="sxs-lookup"><span data-stu-id="8da54-120">The new compiler options are:</span></span>

- <span data-ttu-id="8da54-121">`-publicsign` позволяет включить подписывание сборок как программного обеспечения с открытым кодом;</span><span class="sxs-lookup"><span data-stu-id="8da54-121">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="8da54-122">`-pathmap` позволяет предоставить сопоставление для исходных каталогов.</span><span class="sxs-lookup"><span data-stu-id="8da54-122">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="8da54-123">В оставшейся части этой статьи представлены дополнительные сведения и ссылки по каждому из перечисленных улучшений.</span><span class="sxs-lookup"><span data-stu-id="8da54-123">The remainder of this article provides details and links to learn more about each of the improvements.</span></span> <span data-ttu-id="8da54-124">Эти функции можно изучить в своей среде с помощью глобального средства `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="8da54-124">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="8da54-125">Установите глобальное средство [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="8da54-125">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="8da54-126">Клонируйте репозиторий [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="8da54-126">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="8da54-127">Для репозитория *try-samples* установите в качестве текущего каталога подкаталог *csharp7*.</span><span class="sxs-lookup"><span data-stu-id="8da54-127">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="8da54-128">Запустите `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="8da54-128">Run `dotnet try`.</span></span>

## <a name="enabling-more-efficient-safe-code"></a><span data-ttu-id="8da54-129">Повышение эффективности безопасного кода</span><span class="sxs-lookup"><span data-stu-id="8da54-129">Enabling more efficient safe code</span></span>

<span data-ttu-id="8da54-130">Теперь вы сможете создавать безопасный код C#, который выполняется не хуже небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="8da54-130">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="8da54-131">Безопасный код позволяет избежать ошибок некоторых типов, таких как переполнение буфера, свободные указатели и другие ошибки доступа к памяти.</span><span class="sxs-lookup"><span data-stu-id="8da54-131">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="8da54-132">Новые функции расширяют возможности гарантированно безопасного кода.</span><span class="sxs-lookup"><span data-stu-id="8da54-132">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="8da54-133">Старайтесь как можно большую часть кода создавать из безопасных конструкций.</span><span class="sxs-lookup"><span data-stu-id="8da54-133">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="8da54-134">Благодаря новым возможностям это станет проще.</span><span class="sxs-lookup"><span data-stu-id="8da54-134">These features make that easier.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="8da54-135">Индексирование полей `fixed` не требует закрепления</span><span class="sxs-lookup"><span data-stu-id="8da54-135">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="8da54-136">Давайте рассмотрим такую структуру:</span><span class="sxs-lookup"><span data-stu-id="8da54-136">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="8da54-137">В более ранних версиях C# переменную необходимо закрепить, чтобы получить доступ к целым числам, входящим в `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="8da54-137">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="8da54-138">Теперь приведенный ниже код компилируется без закрепления переменной `p` внутри отдельного оператора `fixed`:</span><span class="sxs-lookup"><span data-stu-id="8da54-138">Now, the following code compiles without pinning the variable `p` inside a separate `fixed` statement:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="8da54-139">Переменная `p` обращается к одному элементу в `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="8da54-139">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="8da54-140">Для этого не нужно объявлять отдельную переменную `int*`.</span><span class="sxs-lookup"><span data-stu-id="8da54-140">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="8da54-141">Обратите внимание, что контекст `unsafe` по-прежнему является обязательным.</span><span class="sxs-lookup"><span data-stu-id="8da54-141">Note that you still need an `unsafe` context.</span></span> <span data-ttu-id="8da54-142">В более ранних версиях C# необходимо объявить второй фиксированный указатель:</span><span class="sxs-lookup"><span data-stu-id="8da54-142">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="8da54-143">Дополнительные сведения см. в статье, посвященной [инструкции `fixed`](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8da54-143">For more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="ref-local-variables-may-be-reassigned"></a><span data-ttu-id="8da54-144">Локальные переменные `ref` могут быть переназначены</span><span class="sxs-lookup"><span data-stu-id="8da54-144">`ref` local variables may be reassigned</span></span>

<span data-ttu-id="8da54-145">Теперь локальные переменные `ref` можно переназначить другим экземплярам после инициализации.</span><span class="sxs-lookup"><span data-stu-id="8da54-145">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="8da54-146">Следующая команда теперь успешно компилируется:</span><span class="sxs-lookup"><span data-stu-id="8da54-146">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="8da54-147">Дополнительные сведения см. в статье о возвращаемых значениях [`ref` и локальных переменных `ref`](../programming-guide/classes-and-structs/ref-returns.md), а также в статье [`foreach`](../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="8da54-147">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="8da54-148">Массивы `stackalloc` поддерживают инициализаторы</span><span class="sxs-lookup"><span data-stu-id="8da54-148">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="8da54-149">Раньше вы могли задавать значения для элементов массива при его инициализации:</span><span class="sxs-lookup"><span data-stu-id="8da54-149">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="8da54-150">Теперь такой же синтаксис можно применять к массивам, в объявлении которых есть `stackalloc`:</span><span class="sxs-lookup"><span data-stu-id="8da54-150">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="8da54-151">Дополнительные сведения см. в статье [Оператор `stackalloc`](../language-reference/operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="8da54-151">For more information, see the [`stackalloc` operator](../language-reference/operators/stackalloc.md) article.</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="8da54-152">Больше типов поддерживают инструкцию `fixed`</span><span class="sxs-lookup"><span data-stu-id="8da54-152">More types support the `fixed` statement</span></span>

<span data-ttu-id="8da54-153">Инструкция `fixed` ранее поддерживала лишь ограниченный набор типов.</span><span class="sxs-lookup"><span data-stu-id="8da54-153">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="8da54-154">Начиная с C# 7.3 любой тип, содержащий метод `GetPinnableReference()`, который возвращает `ref T` или `ref readonly T`, может иметь инструкцию `fixed`.</span><span class="sxs-lookup"><span data-stu-id="8da54-154">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="8da54-155">Добавление этой возможности означает, что `fixed` можно применять для <xref:System.Span%601?displayProperty=nameWithType> и связанных типов.</span><span class="sxs-lookup"><span data-stu-id="8da54-155">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="8da54-156">Дополнительные сведения см. в статье [об инструкции `fixed`](../language-reference/keywords/fixed-statement.md) в справочнике по языку.</span><span class="sxs-lookup"><span data-stu-id="8da54-156">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="8da54-157">Расширенные универсальные ограничения</span><span class="sxs-lookup"><span data-stu-id="8da54-157">Enhanced generic constraints</span></span>

<span data-ttu-id="8da54-158">Теперь вы можете указать тип <xref:System.Enum?displayProperty=nameWithType> или <xref:System.Delegate?displayProperty=nameWithType> в качестве ограничения базового класса для параметра типа.</span><span class="sxs-lookup"><span data-stu-id="8da54-158">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="8da54-159">Вы также можете использовать новое ограничение `unmanaged`, чтобы указать, что параметр типа должен быть [неуправляемым типом](../language-reference/builtin-types/unmanaged-types.md), не допускающим значения NULL.</span><span class="sxs-lookup"><span data-stu-id="8da54-159">You can also use the new `unmanaged` constraint, to specify that a type parameter must be a non-nullable [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span>

<span data-ttu-id="8da54-160">Дополнительные сведения см. в статьях [об универсальных ограничениях `where`](../language-reference/keywords/where-generic-type-constraint.md) и [ограничениях параметров типа](../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="8da54-160">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="8da54-161">Добавление этих ограничений в существующие типы — это [несовместимое изменение](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="8da54-161">Adding these constraints to existing types is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="8da54-162">Закрытые универсальные типы не будут соответствовать подобным ограничениям.</span><span class="sxs-lookup"><span data-stu-id="8da54-162">Closed generic types may no longer meet these new constraints.</span></span>

## <a name="make-existing-features-better"></a><span data-ttu-id="8da54-163">Улучшение существующих функций</span><span class="sxs-lookup"><span data-stu-id="8da54-163">Make existing features better</span></span>

<span data-ttu-id="8da54-164">Во второй группе представлены улучшения существующих возможностей языка.</span><span class="sxs-lookup"><span data-stu-id="8da54-164">The second theme provides improvements to features in the language.</span></span> <span data-ttu-id="8da54-165">Эти возможности повышают производительность при создании кода на C#.</span><span class="sxs-lookup"><span data-stu-id="8da54-165">These features improve productivity when writing C#.</span></span>

### <a name="tuples-support--and-"></a><span data-ttu-id="8da54-166">Поддержка `==` и `!=` для кортежей</span><span class="sxs-lookup"><span data-stu-id="8da54-166">Tuples support `==` and `!=`</span></span>

<span data-ttu-id="8da54-167">Типы кортежей в C# теперь поддерживают `==` и `!=`.</span><span class="sxs-lookup"><span data-stu-id="8da54-167">The C# tuple types now support `==` and `!=`.</span></span> <span data-ttu-id="8da54-168">Дополнительные сведения см. в разделе о [равенстве](../tuples.md#equality-and-tuples) в статье о [кортежах](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="8da54-168">For more information, see the section covering [equality](../tuples.md#equality-and-tuples) in the article on [tuples](../tuples.md).</span></span>

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a><span data-ttu-id="8da54-169">Подключение атрибутов к резервным полям для автоматически реализуемых свойств</span><span class="sxs-lookup"><span data-stu-id="8da54-169">Attach attributes to the backing fields for auto-implemented properties</span></span>

<span data-ttu-id="8da54-170">Теперь поддерживается такой синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8da54-170">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="8da54-171">Атрибут `SomeThingAboutFieldAttribute` применяется к резервному полю, созданному компилятором для `SomeProperty`.</span><span class="sxs-lookup"><span data-stu-id="8da54-171">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="8da54-172">Дополнительные сведения см. в статье об [атрибутах](../programming-guide/concepts/attributes/index.md) в руководстве по программированию на C#.</span><span class="sxs-lookup"><span data-stu-id="8da54-172">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

### <a name="in-method-overload-resolution-tiebreaker"></a><span data-ttu-id="8da54-173">Критерии для разрешения перегрузки метода `in`</span><span class="sxs-lookup"><span data-stu-id="8da54-173">`in` method overload resolution tiebreaker</span></span>

<span data-ttu-id="8da54-174">При добавлении модификатора аргумента `in` следующие два метода создавали неоднозначность:</span><span class="sxs-lookup"><span data-stu-id="8da54-174">When the `in` argument modifier was added, these two methods would cause an ambiguity:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="8da54-175">Теперь перегрузка по значению (первая в предыдущем примере) считается лучше, чем перегрузка по атрибуту "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="8da54-175">Now, the by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="8da54-176">Чтобы вызвать версию со ссылочным аргументом "только для чтения", необходимо при вызове метода указать модификатор `in`.</span><span class="sxs-lookup"><span data-stu-id="8da54-176">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

> [!NOTE]
> <span data-ttu-id="8da54-177">Эта возможность реализована как исправление ошибки.</span><span class="sxs-lookup"><span data-stu-id="8da54-177">This was implemented as a bug fix.</span></span> <span data-ttu-id="8da54-178">Теперь эта ситуация не создает неоднозначности, даже если установлена версия языка 7.2.</span><span class="sxs-lookup"><span data-stu-id="8da54-178">This no longer is ambiguous even with the language version set to "7.2".</span></span>

<span data-ttu-id="8da54-179">Дополнительные сведения см. в статье, посвященной [модификатору параметра `in`](../language-reference/keywords/in-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="8da54-179">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="extend-expression-variables-in-initializers"></a><span data-ttu-id="8da54-180">Расширение переменных выражений в инициализаторах</span><span class="sxs-lookup"><span data-stu-id="8da54-180">Extend expression variables in initializers</span></span>

<span data-ttu-id="8da54-181">Синтаксис, который с версии C# 7.0 позволяет объявлять переменные `out`, теперь также поддерживает инициализаторы полей, инициализаторы свойств, инициализаторы конструктора и предложения запроса.</span><span class="sxs-lookup"><span data-stu-id="8da54-181">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="8da54-182">Он позволяет создать такой код, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8da54-182">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a><span data-ttu-id="8da54-183">Улучшенный отбор потенциальных перегрузок</span><span class="sxs-lookup"><span data-stu-id="8da54-183">Improved overload candidates</span></span>

<span data-ttu-id="8da54-184">В каждом выпуске обновляются правила разрешения перегрузок для устранения ситуаций, где неоднозначный вызов методов можно решить "очевидным" способом.</span><span class="sxs-lookup"><span data-stu-id="8da54-184">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="8da54-185">В этот выпуск добавлены три новых правила, которые помогают компилятору выбрать очевидный вариант.</span><span class="sxs-lookup"><span data-stu-id="8da54-185">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="8da54-186">Если группа методов содержит элементы экземпляра и статические элементы, компилятор отклоняет все элементы экземпляра при вызове метода без экземпляра-получателя и вне контекста экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8da54-186">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="8da54-187">Компилятор отклоняет статические элементы, если метод был вызван с экземпляром-получателем.</span><span class="sxs-lookup"><span data-stu-id="8da54-187">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="8da54-188">Если получатель не указан, компилятор включает в статический контекст только статические элементы, а в противном случае — статические элементы и элементы экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8da54-188">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="8da54-189">Если получатель невозможно однозначно определить как экземпляр или тип, компилятор включает и те, и другие элементы.</span><span class="sxs-lookup"><span data-stu-id="8da54-189">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="8da54-190">В статический контекст, в котором невозможно использовать неявный экземпляр-получатель `this`, включается текст тех элементов, для которых не определено `this`, например статические элементы, а также все места, где не может использоваться `this`, такие как инициализаторы полей и конструкторы-инициализаторы.</span><span class="sxs-lookup"><span data-stu-id="8da54-190">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="8da54-191">Если группа методов содержит некоторые универсальные методы, у которых аргументы типа не удовлетворяют ограничениям, такие элементы удаляются из набора кандидатов.</span><span class="sxs-lookup"><span data-stu-id="8da54-191">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="8da54-192">При преобразовании группы методов из набора удаляются методы-кандидаты, у которых возвращаемый тип не соответствует возвращаемому типу делегата.</span><span class="sxs-lookup"><span data-stu-id="8da54-192">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="8da54-193">Это изменение проявится только тем, что вы реже будете встречать ошибки компилятора о неоднозначной перегрузке методов в тех ситуациях, когда вы точно уверены в выборе лучшего метода.</span><span class="sxs-lookup"><span data-stu-id="8da54-193">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="8da54-194">Новые параметры компилятора</span><span class="sxs-lookup"><span data-stu-id="8da54-194">New compiler options</span></span>

<span data-ttu-id="8da54-195">Новые параметры компилятора поддерживают сценарии сборки и DevOps для программ на C#.</span><span class="sxs-lookup"><span data-stu-id="8da54-195">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="8da54-196">Подписывание открытым ключом или с открытым исходным кодом</span><span class="sxs-lookup"><span data-stu-id="8da54-196">Public or Open Source signing</span></span>

<span data-ttu-id="8da54-197">Параметр компилятора `-publicsign` указывает, что сборку нужно подписать открытым ключом.</span><span class="sxs-lookup"><span data-stu-id="8da54-197">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="8da54-198">Такая сборка будет помечена как подписанная, но подпись для нее берется из открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="8da54-198">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="8da54-199">Этот параметр позволяет создавать подписанные сборки из проектов с открытым кодом с помощью открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="8da54-199">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="8da54-200">Дополнительные сведения см. в статье [о параметре компилятора -publicsign](../language-reference/compiler-options/publicsign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="8da54-200">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="8da54-201">pathmap</span><span class="sxs-lookup"><span data-stu-id="8da54-201">pathmap</span></span>

<span data-ttu-id="8da54-202">Параметр компилятора `-pathmap` указывает, что исходные пути в среде создания следует заменить сопоставленными исходными путями.</span><span class="sxs-lookup"><span data-stu-id="8da54-202">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="8da54-203">Параметр `-pathmap` управляет исходными путями, которые компилятор записывает в PDB-файлы или для <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8da54-203">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="8da54-204">Дополнительные сведения см. в статье [о параметре компилятора -pathmap](../language-reference/compiler-options/pathmap-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="8da54-204">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>
