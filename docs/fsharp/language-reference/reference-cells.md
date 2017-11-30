---
title: "Ссылочные ячейки (F#)"
description: "Узнайте, как ссылочные ячейки F # — это места хранения, которые позволяют создавать изменяющиеся значения с семантикой ссылок."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 09a0b221-ea21-45c4-bae8-5e4a339750c4
ms.openlocfilehash: c7470c9a36cf2cd24dd89ceffcf6e90c6dc4d2dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="reference-cells"></a><span data-ttu-id="770f4-104">Ссылочные ячейки</span><span class="sxs-lookup"><span data-stu-id="770f4-104">Reference Cells</span></span>

<span data-ttu-id="770f4-105">*Ссылочные ячейки* — это места хранения, которые позволяют создавать изменяющиеся значения с семантикой ссылок.</span><span class="sxs-lookup"><span data-stu-id="770f4-105">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="770f4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="770f4-106">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="770f4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="770f4-107">Remarks</span></span>
<span data-ttu-id="770f4-108">Для создания новой ссылочной ячейки, инкапсулирующей значение, перед значением ставится оператор `ref`.</span><span class="sxs-lookup"><span data-stu-id="770f4-108">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="770f4-109">Базовое значение затем можно изменить, так как оно является изменяемым.</span><span class="sxs-lookup"><span data-stu-id="770f4-109">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="770f4-110">Ссылочная ячейка содержит фактическое значение; это не просто адрес.</span><span class="sxs-lookup"><span data-stu-id="770f4-110">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="770f4-111">При создании ссылочной ячейки с помощью оператора `ref` создается копия базового значения в качестве инкапсулированного изменяемого значения.</span><span class="sxs-lookup"><span data-stu-id="770f4-111">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="770f4-112">Разыменовать ссылочную ячейку можно с помощью оператора `!` (восклицательного знака).</span><span class="sxs-lookup"><span data-stu-id="770f4-112">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="770f4-113">Следующий пример кода иллюстрирует объявление и использование ссылочных ячеек.</span><span class="sxs-lookup"><span data-stu-id="770f4-113">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="770f4-114">В результате получается `50`.</span><span class="sxs-lookup"><span data-stu-id="770f4-114">The output is `50`.</span></span>

<span data-ttu-id="770f4-115">Ссылочные ячейки являются экземплярами универсального типа записей `Ref`, который объявляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="770f4-115">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="770f4-116">Тип `'a ref` является синонимом `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="770f4-116">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="770f4-117">В интегрированной среде разработки в компиляторе и в IntelliSense отображается первое обозначение данного типа, однако базовым определением является второе.</span><span class="sxs-lookup"><span data-stu-id="770f4-117">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="770f4-118">Оператор `ref` создает новую ссылочную ячейку.</span><span class="sxs-lookup"><span data-stu-id="770f4-118">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="770f4-119">Следующий код представляет собой объявление оператора `ref`.</span><span class="sxs-lookup"><span data-stu-id="770f4-119">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="770f4-120">В следующей таблице перечислены возможности, доступные для ссылочной ячейки.</span><span class="sxs-lookup"><span data-stu-id="770f4-120">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="770f4-121">Оператор, член или поле</span><span class="sxs-lookup"><span data-stu-id="770f4-121">Operator, member, or field</span></span>|<span data-ttu-id="770f4-122">Описание</span><span class="sxs-lookup"><span data-stu-id="770f4-122">Description</span></span>|<span data-ttu-id="770f4-123">Тип</span><span class="sxs-lookup"><span data-stu-id="770f4-123">Type</span></span>|<span data-ttu-id="770f4-124">Определение</span><span class="sxs-lookup"><span data-stu-id="770f4-124">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="770f4-125">`!` (оператор разыменования)</span><span class="sxs-lookup"><span data-stu-id="770f4-125">`!` (dereference operator)</span></span>|<span data-ttu-id="770f4-126">Возвращает базовое значение.</span><span class="sxs-lookup"><span data-stu-id="770f4-126">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="770f4-127">`:=` (оператор присваивания)</span><span class="sxs-lookup"><span data-stu-id="770f4-127">`:=` (assignment operator)</span></span>|<span data-ttu-id="770f4-128">Изменяет базовое значение.</span><span class="sxs-lookup"><span data-stu-id="770f4-128">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="770f4-129">`ref` (оператор)</span><span class="sxs-lookup"><span data-stu-id="770f4-129">`ref` (operator)</span></span>|<span data-ttu-id="770f4-130">Инкапсулирует значение в новую ссылочную ячейку.</span><span class="sxs-lookup"><span data-stu-id="770f4-130">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="770f4-131">`Value` (свойство)</span><span class="sxs-lookup"><span data-stu-id="770f4-131">`Value` (property)</span></span>|<span data-ttu-id="770f4-132">Получает или задает базовое значение.</span><span class="sxs-lookup"><span data-stu-id="770f4-132">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="770f4-133">`contents` (поле записи)</span><span class="sxs-lookup"><span data-stu-id="770f4-133">`contents` (record field)</span></span>|<span data-ttu-id="770f4-134">Получает или задает базовое значение.</span><span class="sxs-lookup"><span data-stu-id="770f4-134">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="770f4-135">Существует несколько способов доступа к базовому значению.</span><span class="sxs-lookup"><span data-stu-id="770f4-135">There are several ways to access the underlying value.</span></span> <span data-ttu-id="770f4-136">Значение, возвращаемое оператором разыменования (`!`), не является присваиваемым значением.</span><span class="sxs-lookup"><span data-stu-id="770f4-136">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="770f4-137">Следовательно, при изменении базового значения нужно вместо этого оператора использовать оператор присваивания (`:=`).</span><span class="sxs-lookup"><span data-stu-id="770f4-137">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="770f4-138">И свойство `Value`, и поле `contents` являются присваиваемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="770f4-138">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="770f4-139">Следовательно, их можно использовать для доступа к базовому значению или его изменения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="770f4-139">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="770f4-140">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="770f4-140">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="770f4-141">Поле `contents` предусмотрено для совместимости с другими версиями языка ML, и его наличие приводит к выводу предупреждения в процессе компиляции.</span><span class="sxs-lookup"><span data-stu-id="770f4-141">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="770f4-142">Для отключения этого предупреждения используется параметр компилятора `--mlcompatibility`.</span><span class="sxs-lookup"><span data-stu-id="770f4-142">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="770f4-143">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="770f4-143">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="770f4-144">Следующий код иллюстрирует использование ссылочных ячеек при передаче параметров.</span><span class="sxs-lookup"><span data-stu-id="770f4-144">The following code illustrates the use of reference cells in parameter passing.</span></span> <span data-ttu-id="770f4-145">Тип Incrementor имеет метод шаг приращения, принимает параметр, включающий byref в типе параметра.</span><span class="sxs-lookup"><span data-stu-id="770f4-145">The Incrementor type has a method Increment that takes a parameter that includes byref in the parameter type.</span></span> <span data-ttu-id="770f4-146">Byref в типе параметра указывает, что вызывающие объекты должны передавать ссылочную ячейку или адрес обычной переменной заданного типа в этом вариантов int. Остальная часть кода иллюстрирует вызов метода приращения с обоими этими типами аргументов и показано, как использовать оператор ref в переменной для создания ссылочной ячейки (ref myDelta1).</span><span class="sxs-lookup"><span data-stu-id="770f4-146">The byref in the parameter type indicates that callers must pass a reference cell or the address of a typical variable of the specified type, in this case int. The remaining code illustrates how to call Increment with both of these types of arguments, and shows the use of the ref operator on a variable to create a reference cell (ref myDelta1).</span></span> <span data-ttu-id="770f4-147">Затем показано использование оператора взятия адреса (&amp;) для формирования соответствующего аргумента.</span><span class="sxs-lookup"><span data-stu-id="770f4-147">It then shows the use of the address-of operator (&amp;) to generate an appropriate argument.</span></span> <span data-ttu-id="770f4-148">Наконец метод Increment вызывается снова путем использования ссылочной ячейки, объявленной с помощью привязки let.</span><span class="sxs-lookup"><span data-stu-id="770f4-148">Finally, the Increment method is called again by using a reference cell that is declared by using a let binding.</span></span> <span data-ttu-id="770f4-149">В последней строке кода демонстрируется использование!</span><span class="sxs-lookup"><span data-stu-id="770f4-149">The final line of code demonstrates the use of the !</span></span> <span data-ttu-id="770f4-150">оператор разыменования ссылочной ячейки для печати.</span><span class="sxs-lookup"><span data-stu-id="770f4-150">operator to dereference the reference cell for printing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

<span data-ttu-id="770f4-151">Дополнительные сведения о передаче по ссылке см. в разделе [параметры и аргументы](parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="770f4-151">For more information about how to pass by reference, see [Parameters and Arguments](parameters-and-arguments.md).</span></span>

>[!NOTE]
<span data-ttu-id="770f4-152">Программистам на C# следует знать, что этой ссылки по-разному работает в языке F #, чем в C#.</span><span class="sxs-lookup"><span data-stu-id="770f4-152">C# programmers should know that ref works differently in F# than it does in C#.</span></span> <span data-ttu-id="770f4-153">Например использование ref при передаче аргумента имеет тот же эффект в языке F #, нежели в C#.</span><span class="sxs-lookup"><span data-stu-id="770f4-153">For example, the use of ref when you pass an argument does not have the same effect in F# as it does in C#.</span></span>

## <a name="consuming-c-ref-returns"></a><span data-ttu-id="770f4-154">Использование C# `ref` возвращает</span><span class="sxs-lookup"><span data-stu-id="770f4-154">Consuming C# `ref` returns</span></span>

<span data-ttu-id="770f4-155">Начиная с версии 4.1 F #, можно будет использовать `ref` возвращает созданный в C#.</span><span class="sxs-lookup"><span data-stu-id="770f4-155">Starting with F# 4.1, you can consume `ref` returns generated in C#.</span></span>  <span data-ttu-id="770f4-156">Результат такого вызова — `byref<_>` указателя.</span><span class="sxs-lookup"><span data-stu-id="770f4-156">The result of such a call is a `byref<_>` pointer.</span></span>

<span data-ttu-id="770f4-157">Следующий метод C#:</span><span class="sxs-lookup"><span data-stu-id="770f4-157">The following C# method:</span></span>

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

<span data-ttu-id="770f4-158">Может прозрачно вызываться F # с не специальный синтаксис:</span><span class="sxs-lookup"><span data-stu-id="770f4-158">Can be transparently called by F# with no special syntax:</span></span>

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

<span data-ttu-id="770f4-159">Можно также объявить функции, которые занимают `ref` возвращают в качестве входных данных, например:</span><span class="sxs-lookup"><span data-stu-id="770f4-159">You can also declare functions which could take a `ref` return as input, for example:</span></span>

```fsharp
let f (x: byref<int>) = &x
```

<span data-ttu-id="770f4-160">В настоящее время нет возможности для создания `ref` возврата в F #, который может использоваться в C#.</span><span class="sxs-lookup"><span data-stu-id="770f4-160">There is currently no way to generate a `ref` return in F# which could be consumed in C#.</span></span>

## <a name="see-also"></a><span data-ttu-id="770f4-161">См. также</span><span class="sxs-lookup"><span data-stu-id="770f4-161">See Also</span></span>
[<span data-ttu-id="770f4-162">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="770f4-162">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="770f4-163">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="770f4-163">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="770f4-164">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="770f4-164">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
