---
title: Руководство по программированию на C#. Типы указателей
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 81e9a86c4761b329918bf04023dea42d2e1ad6f5
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423527"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="0b28e-102">Типы указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0b28e-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="0b28e-103">В небезопасном контексте тип может быть типом указателя, типом значения или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="0b28e-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="0b28e-104">Объявления типа указателя выполняется одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="0b28e-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="0b28e-105">Тип, указанный до `*` в типе указателя, называется **ссылочным типом**.</span><span class="sxs-lookup"><span data-stu-id="0b28e-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="0b28e-106">Ссылочным может быть любой из указанных ниже типов.</span><span class="sxs-lookup"><span data-stu-id="0b28e-106">Any of the following types may be a referent type:</span></span>

- <span data-ttu-id="0b28e-107">Любой целочисленный тип: [sbyte](../../language-reference/builtin-types/integral-numeric-types.md), [byte](../../language-reference/builtin-types/integral-numeric-types.md), [short](../../language-reference/builtin-types/integral-numeric-types.md), [ushort](../../language-reference/builtin-types/integral-numeric-types.md), [int](../../language-reference/builtin-types/integral-numeric-types.md), [uint](../../language-reference/builtin-types/integral-numeric-types.md), [long](../../language-reference/builtin-types/integral-numeric-types.md), [ulong](../../language-reference/builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-107">Any integral type: [sbyte](../../language-reference/builtin-types/integral-numeric-types.md), [byte](../../language-reference/builtin-types/integral-numeric-types.md), [short](../../language-reference/builtin-types/integral-numeric-types.md), [ushort](../../language-reference/builtin-types/integral-numeric-types.md), [int](../../language-reference/builtin-types/integral-numeric-types.md), [uint](../../language-reference/builtin-types/integral-numeric-types.md), [long](../../language-reference/builtin-types/integral-numeric-types.md), [ulong](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>
- <span data-ttu-id="0b28e-108">Любой тип с плавающей запятой: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-108">Any floating-point type: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span></span>
- <span data-ttu-id="0b28e-109">[char](../../language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-109">[char](../../language-reference/keywords/char.md).</span></span>
- <span data-ttu-id="0b28e-110">[bool](../../language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-110">[bool](../../language-reference/keywords/bool.md).</span></span>
- <span data-ttu-id="0b28e-111">[decimal](../../language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-111">[decimal](../../language-reference/keywords/decimal.md).</span></span>
- <span data-ttu-id="0b28e-112">Любой тип [enum](../../language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-112">Any [enum](../../language-reference/keywords/enum.md) type.</span></span>
- <span data-ttu-id="0b28e-113">Любой тип указателя.</span><span class="sxs-lookup"><span data-stu-id="0b28e-113">Any pointer type.</span></span> <span data-ttu-id="0b28e-114">Это позволяет использовать выражения, такие как `void**`.</span><span class="sxs-lookup"><span data-stu-id="0b28e-114">This allows expressions such as `void**`.</span></span>
- <span data-ttu-id="0b28e-115">Любой пользовательский тип структуры, содержащий поля только неуправляемых типов.</span><span class="sxs-lookup"><span data-stu-id="0b28e-115">Any user-defined struct type that contains fields of unmanaged types only.</span></span>

<span data-ttu-id="0b28e-116">Типы указателей не наследуются от [объекта](../../language-reference/keywords/object.md), а типы указателей не преобразуются в `object`.</span><span class="sxs-lookup"><span data-stu-id="0b28e-116">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="0b28e-117">Кроме того, упаковка-преобразование и распаковка-преобразование не поддерживают указатели.</span><span class="sxs-lookup"><span data-stu-id="0b28e-117">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="0b28e-118">Однако можно выполнять преобразования между различными типами указателей, а также между типами указателей и целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="0b28e-118">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="0b28e-119">При объявлении нескольких указателей в одном объявлении знак \* указывается только с базовым типом; он не используется в качестве префикса для каждого имени указателя.</span><span class="sxs-lookup"><span data-stu-id="0b28e-119">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="0b28e-120">Например:</span><span class="sxs-lookup"><span data-stu-id="0b28e-120">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="0b28e-121">Указатель не может указывать на ссылку или на [структуру](../../language-reference/keywords/struct.md), содержащую ссылки, поскольку ссылка на объект может быть подвергнута сбору мусора, даже если на нее указывает указатель.</span><span class="sxs-lookup"><span data-stu-id="0b28e-121">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="0b28e-122">Сборщик мусора не отслеживает наличие указателей любых типов, указывающих на объекты.</span><span class="sxs-lookup"><span data-stu-id="0b28e-122">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="0b28e-123">Значением переменной-указателя типа `myType*` является адрес переменной типа `myType`.</span><span class="sxs-lookup"><span data-stu-id="0b28e-123">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="0b28e-124">Ниже приведены примеры объявлений типов указателей.</span><span class="sxs-lookup"><span data-stu-id="0b28e-124">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="0b28e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="0b28e-125">Example</span></span>|<span data-ttu-id="0b28e-126">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0b28e-126">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="0b28e-127">`p` — указатель на целое число.</span><span class="sxs-lookup"><span data-stu-id="0b28e-127">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="0b28e-128">`p` — указатель на указатель на целое число.</span><span class="sxs-lookup"><span data-stu-id="0b28e-128">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="0b28e-129">`p` — одномерный массив указателей на целые числа.</span><span class="sxs-lookup"><span data-stu-id="0b28e-129">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="0b28e-130">`p` — указатель на тип char.</span><span class="sxs-lookup"><span data-stu-id="0b28e-130">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="0b28e-131">`p` — указатель на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="0b28e-131">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="0b28e-132">Оператор косвенного обращения указателя \* можно использовать для доступа к содержимому, на которое указывает переменная-указатель.</span><span class="sxs-lookup"><span data-stu-id="0b28e-132">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="0b28e-133">В качестве примера рассмотрим следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="0b28e-133">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="0b28e-134">Выражение `*myVariable` обозначает переменную `int`, находящуюся по адресу, содержащемуся в `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="0b28e-134">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="0b28e-135">Разделы [Оператор fixed](../../language-reference/keywords/fixed-statement.md) и [Преобразования указателей](../../programming-guide/unsafe-code-pointers/pointer-conversions.md) содержат несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="0b28e-135">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span> <span data-ttu-id="0b28e-136">В следующем примере используются ключевое слово `unsafe` и оператор `fixed`, а также демонстрируется способ инкрементирования внутреннего указателя.</span><span class="sxs-lookup"><span data-stu-id="0b28e-136">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="0b28e-137">Этот код можно вставить в функцию Main консольного приложения для его запуска.</span><span class="sxs-lookup"><span data-stu-id="0b28e-137">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="0b28e-138">Эти примеры должны быть скомпилированы с заданным параметром компилятора [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-138">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="0b28e-139">Для указателя типа `void*` использовать оператор косвенного обращения нельзя.</span><span class="sxs-lookup"><span data-stu-id="0b28e-139">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="0b28e-140">Однако можно использовать приведение для преобразования указателя типа void в любой другой тип и наоборот.</span><span class="sxs-lookup"><span data-stu-id="0b28e-140">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="0b28e-141">Указатель может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="0b28e-141">A pointer can be `null`.</span></span> <span data-ttu-id="0b28e-142">При применении оператора косвенного обращения к указателю со значением null результат зависит от конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="0b28e-142">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="0b28e-143">При передаче указателей между методами может возникнуть неопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="0b28e-143">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="0b28e-144">Рекомендуется использовать метод, возвращающий указатель в локальную переменную с помощью параметра `in`, `out` или `ref` либо в виде результата функции.</span><span class="sxs-lookup"><span data-stu-id="0b28e-144">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="0b28e-145">Если указатель был задан в фиксированном блоке, переменная, на которую он указывает, больше не может быть фиксированной.</span><span class="sxs-lookup"><span data-stu-id="0b28e-145">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="0b28e-146">В следующей таблице перечислены операторы, которые можно использовать для указателей в небезопасном контексте.</span><span class="sxs-lookup"><span data-stu-id="0b28e-146">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="0b28e-147">Оператор</span><span class="sxs-lookup"><span data-stu-id="0b28e-147">Operator/Statement</span></span>|<span data-ttu-id="0b28e-148">Использовать</span><span class="sxs-lookup"><span data-stu-id="0b28e-148">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="0b28e-149">Косвенное обращение к указателю.</span><span class="sxs-lookup"><span data-stu-id="0b28e-149">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="0b28e-150">Доступ к члену структуры через указатель.</span><span class="sxs-lookup"><span data-stu-id="0b28e-150">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="0b28e-151">Индексирование указателя.</span><span class="sxs-lookup"><span data-stu-id="0b28e-151">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="0b28e-152">Получение адреса переменной.</span><span class="sxs-lookup"><span data-stu-id="0b28e-152">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="0b28e-153">`++` и `--`</span><span class="sxs-lookup"><span data-stu-id="0b28e-153">`++` and `--`</span></span>|<span data-ttu-id="0b28e-154">Увеличение и уменьшение указателей.</span><span class="sxs-lookup"><span data-stu-id="0b28e-154">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="0b28e-155">`+` и `-`</span><span class="sxs-lookup"><span data-stu-id="0b28e-155">`+` and `-`</span></span>|<span data-ttu-id="0b28e-156">Арифметические действия с указателем.</span><span class="sxs-lookup"><span data-stu-id="0b28e-156">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="0b28e-157">`==`, `!=`, `<`, `>`, `<=` и `>=`</span><span class="sxs-lookup"><span data-stu-id="0b28e-157">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="0b28e-158">Сравнение указателей.</span><span class="sxs-lookup"><span data-stu-id="0b28e-158">Compares pointers.</span></span>|
|[<span data-ttu-id="0b28e-159">Оператор `stackalloc`</span><span class="sxs-lookup"><span data-stu-id="0b28e-159">`stackalloc` operator</span></span>](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="0b28e-160">Выделение памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="0b28e-160">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="0b28e-161">Инструкция `fixed`</span><span class="sxs-lookup"><span data-stu-id="0b28e-161">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="0b28e-162">Временная фиксация переменной, чтобы можно было найти ее адрес.</span><span class="sxs-lookup"><span data-stu-id="0b28e-162">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="0b28e-163">Дополнительные сведения об операторах, связанных с указателем, см. в разделе [Операторы, связанные с указателем](../../language-reference/operators/pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-163">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b28e-164">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0b28e-164">C# language specification</span></span>

<span data-ttu-id="0b28e-165">Дополнительные сведения см. в разделе [Типы указателей](~/_csharplang/spec/unsafe-code.md#pointer-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0b28e-165">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b28e-166">См. также</span><span class="sxs-lookup"><span data-stu-id="0b28e-166">See also</span></span>

- [<span data-ttu-id="0b28e-167">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0b28e-167">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0b28e-168">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="0b28e-168">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="0b28e-169">Преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="0b28e-169">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="0b28e-170">Типы</span><span class="sxs-lookup"><span data-stu-id="0b28e-170">Types</span></span>](../../language-reference/keywords/types.md)
- [<span data-ttu-id="0b28e-171">unsafe</span><span class="sxs-lookup"><span data-stu-id="0b28e-171">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
