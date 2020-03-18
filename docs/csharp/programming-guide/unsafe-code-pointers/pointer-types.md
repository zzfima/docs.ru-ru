---
title: Руководство по программированию на C#. Типы указателей
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: dc03744559a87a2548c5bee9452c22cd20f337b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627714"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="7dbe7-102">Типы указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="7dbe7-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="7dbe7-103">В небезопасном контексте тип может быть типом указателя, типом значения или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="7dbe7-104">Объявления типа указателя выполняется одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="7dbe7-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="7dbe7-105">Тип, указанный до `*` в типе указателя, называется **ссылочным типом**.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="7dbe7-106">Ссылочным типом может быть только [неуправляемый тип](../../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="7dbe7-106">Only an [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md) can be a referent type.</span></span>

<span data-ttu-id="7dbe7-107">Типы указателей не наследуются от [объекта](../../language-reference/builtin-types/reference-types.md), а типы указателей не преобразуются в `object`.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-107">Pointer types do not inherit from [object](../../language-reference/builtin-types/reference-types.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="7dbe7-108">Кроме того, упаковка-преобразование и распаковка-преобразование не поддерживают указатели.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-108">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="7dbe7-109">Однако можно выполнять преобразования между различными типами указателей, а также между типами указателей и целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-109">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="7dbe7-110">При объявлении нескольких указателей в одном объявлении знак \* указывается только с базовым типом; он не используется в качестве префикса для каждого имени указателя.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-110">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="7dbe7-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="7dbe7-111">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="7dbe7-112">Указатель не может указывать на ссылку или на [структуру](../../language-reference/builtin-types/struct.md), содержащую ссылки, поскольку ссылка на объект может быть подвергнута сбору мусора, даже если на нее указывает указатель.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-112">A pointer cannot point to a reference or to a [struct](../../language-reference/builtin-types/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="7dbe7-113">Сборщик мусора не отслеживает наличие указателей любых типов, указывающих на объекты.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-113">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="7dbe7-114">Значением переменной-указателя типа `myType*` является адрес переменной типа `myType`.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-114">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="7dbe7-115">Ниже приведены примеры объявлений типов указателей.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-115">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="7dbe7-116">Пример</span><span class="sxs-lookup"><span data-stu-id="7dbe7-116">Example</span></span>|<span data-ttu-id="7dbe7-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="7dbe7-117">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="7dbe7-118">`p` — указатель на целое число.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-118">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="7dbe7-119">`p` — указатель на указатель на целое число.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-119">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="7dbe7-120">`p` — одномерный массив указателей на целые числа.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-120">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="7dbe7-121">`p` — указатель на тип char.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-121">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="7dbe7-122">`p` — указатель на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-122">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="7dbe7-123">Оператор косвенного обращения указателя \* можно использовать для доступа к содержимому, на которое указывает переменная-указатель.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-123">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="7dbe7-124">В качестве примера рассмотрим следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="7dbe7-124">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="7dbe7-125">Выражение `*myVariable` обозначает переменную `int`, находящуюся по адресу, содержащемуся в `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-125">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="7dbe7-126">Разделы [Оператор fixed](../../language-reference/keywords/fixed-statement.md) и [Преобразования указателей](./pointer-conversions.md) содержат несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-126">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](./pointer-conversions.md).</span></span> <span data-ttu-id="7dbe7-127">В следующем примере используются ключевое слово `unsafe` и оператор `fixed`, а также демонстрируется способ инкрементирования внутреннего указателя.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-127">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="7dbe7-128">Этот код можно вставить в функцию Main консольного приложения для его запуска.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-128">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="7dbe7-129">Эти примеры должны быть скомпилированы с заданным параметром компилятора [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="7dbe7-129">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="7dbe7-130">Для указателя типа `void*` использовать оператор косвенного обращения нельзя.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-130">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="7dbe7-131">Однако можно использовать приведение для преобразования указателя типа void в любой другой тип и наоборот.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-131">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="7dbe7-132">Указатель может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-132">A pointer can be `null`.</span></span> <span data-ttu-id="7dbe7-133">При применении оператора косвенного обращения к указателю со значением null результат зависит от конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-133">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="7dbe7-134">При передаче указателей между методами может возникнуть неопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-134">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="7dbe7-135">Рекомендуется использовать метод, возвращающий указатель в локальную переменную с помощью параметра `in`, `out` или `ref` либо в виде результата функции.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-135">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="7dbe7-136">Если указатель был задан в фиксированном блоке, переменная, на которую он указывает, больше не может быть фиксированной.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-136">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="7dbe7-137">В следующей таблице перечислены операторы, которые можно использовать для указателей в небезопасном контексте.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-137">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="7dbe7-138">Оператор</span><span class="sxs-lookup"><span data-stu-id="7dbe7-138">Operator/Statement</span></span>|<span data-ttu-id="7dbe7-139">Использование</span><span class="sxs-lookup"><span data-stu-id="7dbe7-139">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="7dbe7-140">Косвенное обращение к указателю.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-140">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="7dbe7-141">Доступ к члену структуры через указатель.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-141">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="7dbe7-142">Индексирование указателя.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-142">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="7dbe7-143">Получение адреса переменной.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-143">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="7dbe7-144">`++` и `--`.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-144">`++` and `--`</span></span>|<span data-ttu-id="7dbe7-145">Увеличение и уменьшение указателей.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-145">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="7dbe7-146">`+` и `-`.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-146">`+` and `-`</span></span>|<span data-ttu-id="7dbe7-147">Арифметические действия с указателем.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-147">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="7dbe7-148">`==`, `!=`, `<`, `>`, `<=` и `>=`</span><span class="sxs-lookup"><span data-stu-id="7dbe7-148">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="7dbe7-149">Сравнение указателей.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-149">Compares pointers.</span></span>|
|[<span data-ttu-id="7dbe7-150">Оператор `stackalloc`</span><span class="sxs-lookup"><span data-stu-id="7dbe7-150">`stackalloc` operator</span></span>](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="7dbe7-151">Выделение памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-151">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="7dbe7-152">Инструкция `fixed`</span><span class="sxs-lookup"><span data-stu-id="7dbe7-152">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="7dbe7-153">Временная фиксация переменной, чтобы можно было найти ее адрес.</span><span class="sxs-lookup"><span data-stu-id="7dbe7-153">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="7dbe7-154">Дополнительные сведения об операторах, связанных с указателем, см. в разделе [Операторы, связанные с указателем](../../language-reference/operators/pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="7dbe7-154">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7dbe7-155">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7dbe7-155">C# language specification</span></span>

<span data-ttu-id="7dbe7-156">Дополнительные сведения см. в разделе [Типы указателей](~/_csharplang/spec/unsafe-code.md#pointer-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7dbe7-156">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7dbe7-157">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7dbe7-157">See also</span></span>

- [<span data-ttu-id="7dbe7-158">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7dbe7-158">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7dbe7-159">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="7dbe7-159">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="7dbe7-160">Преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="7dbe7-160">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="7dbe7-161">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="7dbe7-161">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="7dbe7-162">Типы значений</span><span class="sxs-lookup"><span data-stu-id="7dbe7-162">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="7dbe7-163">unsafe</span><span class="sxs-lookup"><span data-stu-id="7dbe7-163">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
