---
title: Типы указателей (Руководство по программированию на C#)
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 2950d92f877a7e99734267a3071b2bcb25ce1023
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509282"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="4c4a5-102">Типы указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4c4a5-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="4c4a5-103">В небезопасном контексте тип может быть типом указателя, типом значения или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="4c4a5-104">Объявления типа указателя выполняется одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="4c4a5-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="4c4a5-105">Тип, указанный до `*` в типе указателя, называется **ссылочным типом**.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-105">The type specified before the `*` in a pointer type is called the **referrent type**.</span></span> <span data-ttu-id="4c4a5-106">Ссылочным может быть любой из указанных ниже типов.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-106">Any of the following types may be a referrent type:</span></span>

- <span data-ttu-id="4c4a5-107">Любой целочисленный тип: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="4c4a5-107">Any integral type: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span></span>
- <span data-ttu-id="4c4a5-108">Любой тип с плавающей запятой: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="4c4a5-108">Any floating point type: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span></span>
- <span data-ttu-id="4c4a5-109">[char](../../language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="4c4a5-109">[char](../../language-reference/keywords/char.md).</span></span>
- <span data-ttu-id="4c4a5-110">[bool](../../language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="4c4a5-110">[bool](../../language-reference/keywords/bool.md).</span></span>
- <span data-ttu-id="4c4a5-111">[decimal](../../language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="4c4a5-111">[decimal](../../language-reference/keywords/decimal.md).</span></span>
- <span data-ttu-id="4c4a5-112">Любой тип [enum](../../language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="4c4a5-112">Any [enum](../../language-reference/keywords/enum.md) type.</span></span>
- <span data-ttu-id="4c4a5-113">Любой тип указателя.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-113">Any pointer type.</span></span> <span data-ttu-id="4c4a5-114">Это позволяет использовать выражения, такие как `void**`.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-114">This allows expressions such as `void**`.</span></span>
- <span data-ttu-id="4c4a5-115">Любой пользовательский тип структуры, содержащий поля только неуправляемых типов.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-115">Any user-defined struct type that contains fields of unmanaged types only.</span></span>

<span data-ttu-id="4c4a5-116">Типы указателей не наследуются от [объекта](../../language-reference/keywords/object.md), а типы указателей не преобразуются в `object`.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-116">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="4c4a5-117">Кроме того, упаковка-преобразование и распаковка-преобразование не поддерживают указатели.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-117">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="4c4a5-118">Однако можно выполнять преобразования между различными типами указателей, а также между типами указателей и целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-118">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="4c4a5-119">При объявлении нескольких указателей в одном объявлении знак \* указывается только с базовым типом; он не используется в качестве префикса для каждого имени указателя.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-119">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="4c4a5-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="4c4a5-120">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="4c4a5-121">Указатель не может указывать на ссылку или на [структуру](../../language-reference/keywords/struct.md), содержащую ссылки, поскольку ссылка на объект может быть подвергнута сбору мусора, даже если на нее указывает указатель.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-121">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="4c4a5-122">Сборщик мусора не отслеживает наличие указателей любых типов, указывающих на объекты.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-122">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="4c4a5-123">Значением переменной-указателя типа `myType*` является адрес переменной типа `myType`.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-123">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="4c4a5-124">Ниже приведены примеры объявлений типов указателей.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-124">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="4c4a5-125">Пример</span><span class="sxs-lookup"><span data-stu-id="4c4a5-125">Example</span></span>|<span data-ttu-id="4c4a5-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="4c4a5-126">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="4c4a5-127">`p` — указатель на целое число.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-127">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="4c4a5-128">`p` — указатель на указатель на целое число.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-128">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="4c4a5-129">`p` — одномерный массив указателей на целые числа.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-129">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="4c4a5-130">`p` — указатель на тип char.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-130">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="4c4a5-131">`p` — указатель на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-131">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="4c4a5-132">Оператор косвенного обращения указателя \* можно использовать для доступа к содержимому, на которое указывает переменная-указатель.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-132">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="4c4a5-133">В качестве примера рассмотрим следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="4c4a5-133">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="4c4a5-134">Выражение `*myVariable` обозначает переменную `int`, находящуюся по адресу, содержащемуся в `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-134">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="4c4a5-135">Разделы [Оператор fixed](../../language-reference/keywords/fixed-statement.md) и [Преобразования указателей](../../programming-guide/unsafe-code-pointers/pointer-conversions.md) содержат несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-135">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span> <span data-ttu-id="4c4a5-136">В следующем примере используются ключевое слово `unsafe` и оператор `fixed`, а также демонстрируется способ инкрементирования внутреннего указателя.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-136">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="4c4a5-137">Этот код можно вставить в функцию Main консольного приложения для его запуска.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-137">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="4c4a5-138">Эти примеры должны быть скомпилированы с заданным параметром компилятора [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4c4a5-138">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="4c4a5-139">Для указателя типа `void*` использовать оператор косвенного обращения нельзя.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-139">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="4c4a5-140">Однако можно использовать приведение для преобразования указателя типа void в любой другой тип и наоборот.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-140">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="4c4a5-141">Указатель может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-141">A pointer can be `null`.</span></span> <span data-ttu-id="4c4a5-142">При применении оператора косвенного обращения к указателю со значением null результат зависит от конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-142">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="4c4a5-143">При передаче указателей между методами может возникнуть неопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-143">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="4c4a5-144">Рекомендуется использовать метод, возвращающий указатель в локальную переменную с помощью параметра `in`, `out` или `ref` либо в виде результата функции.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-144">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="4c4a5-145">Если указатель был задан в фиксированном блоке, переменная, на которую он указывает, больше не может быть фиксированной.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-145">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="4c4a5-146">В следующей таблице перечислены операторы, которые можно использовать для указателей в небезопасном контексте.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-146">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="4c4a5-147">Оператор</span><span class="sxs-lookup"><span data-stu-id="4c4a5-147">Operator/Statement</span></span>|<span data-ttu-id="4c4a5-148">Использовать</span><span class="sxs-lookup"><span data-stu-id="4c4a5-148">Use</span></span>|
|-------------------------|---------|
|*|<span data-ttu-id="4c4a5-149">Косвенное обращение к указателю.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-149">Performs pointer indirection.</span></span>|
|->|<span data-ttu-id="4c4a5-150">Доступ к члену структуры через указатель.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-150">Accesses a member of a struct through a pointer.</span></span>|
|<span data-ttu-id="4c4a5-151">[]</span><span class="sxs-lookup"><span data-stu-id="4c4a5-151">[]</span></span>|<span data-ttu-id="4c4a5-152">Индексирование указателя.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-152">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="4c4a5-153">Получение адреса переменной.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-153">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="4c4a5-154">++ и --</span><span class="sxs-lookup"><span data-stu-id="4c4a5-154">++ and --</span></span>|<span data-ttu-id="4c4a5-155">Увеличение и уменьшение указателей.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-155">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="4c4a5-156">+ и -</span><span class="sxs-lookup"><span data-stu-id="4c4a5-156">+ and -</span></span>|<span data-ttu-id="4c4a5-157">Арифметические действия с указателем.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-157">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="4c4a5-158">==, !=, \<, >, \<= и >=</span><span class="sxs-lookup"><span data-stu-id="4c4a5-158">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="4c4a5-159">Сравнение указателей.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-159">Compares pointers.</span></span>|
|`stackalloc`|<span data-ttu-id="4c4a5-160">Выделение памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-160">Allocates memory on the stack.</span></span>|
|<span data-ttu-id="4c4a5-161">Оператор `fixed`</span><span class="sxs-lookup"><span data-stu-id="4c4a5-161">`fixed` statement</span></span>|<span data-ttu-id="4c4a5-162">Временная фиксация переменной, чтобы можно было найти ее адрес.</span><span class="sxs-lookup"><span data-stu-id="4c4a5-162">Temporarily fixes a variable so that its address may be found.</span></span>|

## <a name="c-language-specification"></a><span data-ttu-id="4c4a5-163">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4c4a5-163">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4c4a5-164">См. также</span><span class="sxs-lookup"><span data-stu-id="4c4a5-164">See Also</span></span>

- [<span data-ttu-id="4c4a5-165">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4c4a5-165">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="4c4a5-166">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="4c4a5-166">Unsafe Code and Pointers</span></span>](index.md)  
- [<span data-ttu-id="4c4a5-167">Преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="4c4a5-167">Pointer Conversions</span></span>](pointer-conversions.md)  
- [<span data-ttu-id="4c4a5-168">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="4c4a5-168">Pointer Expressions</span></span>](pointer-expressions.md)  
- [<span data-ttu-id="4c4a5-169">Типы</span><span class="sxs-lookup"><span data-stu-id="4c4a5-169">Types</span></span>](../../language-reference/keywords/types.md)  
- [<span data-ttu-id="4c4a5-170">unsafe</span><span class="sxs-lookup"><span data-stu-id="4c4a5-170">unsafe</span></span>](../../language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="4c4a5-171">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="4c4a5-171">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="4c4a5-172">stackalloc</span><span class="sxs-lookup"><span data-stu-id="4c4a5-172">stackalloc</span></span>](../../language-reference/keywords/stackalloc.md)  
- [<span data-ttu-id="4c4a5-173">Упаковка-преобразование и распаковка-преобразование</span><span class="sxs-lookup"><span data-stu-id="4c4a5-173">Boxing and Unboxing</span></span>](../types/boxing-and-unboxing.md)
