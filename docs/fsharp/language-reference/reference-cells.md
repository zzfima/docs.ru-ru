---
title: Ссылочные ячейки (F#)
description: 'Узнайте, как ссылочные ячейки F # — это места хранения, которые позволяют создавать изменяющиеся значения с семантикой ссылок.'
ms.date: 05/16/2016
ms.openlocfilehash: 133aec6b162a13306a05c9afa172f859890565eb
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43892429"
---
# <a name="reference-cells"></a><span data-ttu-id="187df-103">Ссылочные ячейки</span><span class="sxs-lookup"><span data-stu-id="187df-103">Reference Cells</span></span>

<span data-ttu-id="187df-104">*Ссылочные ячейки* — это места хранения, которые позволяют создавать изменяющиеся значения с семантикой ссылок.</span><span class="sxs-lookup"><span data-stu-id="187df-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="187df-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="187df-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="187df-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="187df-106">Remarks</span></span>

<span data-ttu-id="187df-107">Для создания новой ссылочной ячейки, инкапсулирующей значение, перед значением ставится оператор `ref`.</span><span class="sxs-lookup"><span data-stu-id="187df-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="187df-108">Базовое значение затем можно изменить, так как оно является изменяемым.</span><span class="sxs-lookup"><span data-stu-id="187df-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="187df-109">Ссылочная ячейка содержит фактическое значение; это не просто адрес.</span><span class="sxs-lookup"><span data-stu-id="187df-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="187df-110">При создании ссылочной ячейки с помощью оператора `ref` создается копия базового значения в качестве инкапсулированного изменяемого значения.</span><span class="sxs-lookup"><span data-stu-id="187df-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="187df-111">Разыменовать ссылочную ячейку можно с помощью оператора `!` (восклицательного знака).</span><span class="sxs-lookup"><span data-stu-id="187df-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="187df-112">Следующий пример кода иллюстрирует объявление и использование ссылочных ячеек.</span><span class="sxs-lookup"><span data-stu-id="187df-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="187df-113">В результате получается `50`.</span><span class="sxs-lookup"><span data-stu-id="187df-113">The output is `50`.</span></span>

<span data-ttu-id="187df-114">Ссылочные ячейки являются экземплярами универсального типа записей `Ref`, который объявляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="187df-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="187df-115">Тип `'a ref` является синонимом `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="187df-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="187df-116">В интегрированной среде разработки в компиляторе и в IntelliSense отображается первое обозначение данного типа, однако базовым определением является второе.</span><span class="sxs-lookup"><span data-stu-id="187df-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="187df-117">Оператор `ref` создает новую ссылочную ячейку.</span><span class="sxs-lookup"><span data-stu-id="187df-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="187df-118">Следующий код представляет собой объявление оператора `ref`.</span><span class="sxs-lookup"><span data-stu-id="187df-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="187df-119">В следующей таблице перечислены возможности, доступные для ссылочной ячейки.</span><span class="sxs-lookup"><span data-stu-id="187df-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="187df-120">Оператор, член или поле</span><span class="sxs-lookup"><span data-stu-id="187df-120">Operator, member, or field</span></span>|<span data-ttu-id="187df-121">Описание</span><span class="sxs-lookup"><span data-stu-id="187df-121">Description</span></span>|<span data-ttu-id="187df-122">Тип</span><span class="sxs-lookup"><span data-stu-id="187df-122">Type</span></span>|<span data-ttu-id="187df-123">Определение</span><span class="sxs-lookup"><span data-stu-id="187df-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="187df-124">`!` (оператор разыменования)</span><span class="sxs-lookup"><span data-stu-id="187df-124">`!` (dereference operator)</span></span>|<span data-ttu-id="187df-125">Возвращает базовое значение.</span><span class="sxs-lookup"><span data-stu-id="187df-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="187df-126">`:=` (оператор присваивания)</span><span class="sxs-lookup"><span data-stu-id="187df-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="187df-127">Изменяет базовое значение.</span><span class="sxs-lookup"><span data-stu-id="187df-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="187df-128">`ref` (оператор)</span><span class="sxs-lookup"><span data-stu-id="187df-128">`ref` (operator)</span></span>|<span data-ttu-id="187df-129">Инкапсулирует значение в новую ссылочную ячейку.</span><span class="sxs-lookup"><span data-stu-id="187df-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="187df-130">`Value` (свойство)</span><span class="sxs-lookup"><span data-stu-id="187df-130">`Value` (property)</span></span>|<span data-ttu-id="187df-131">Получает или задает базовое значение.</span><span class="sxs-lookup"><span data-stu-id="187df-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="187df-132">`contents` (поле записи)</span><span class="sxs-lookup"><span data-stu-id="187df-132">`contents` (record field)</span></span>|<span data-ttu-id="187df-133">Получает или задает базовое значение.</span><span class="sxs-lookup"><span data-stu-id="187df-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="187df-134">Существует несколько способов доступа к базовому значению.</span><span class="sxs-lookup"><span data-stu-id="187df-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="187df-135">Значение, возвращаемое оператором разыменования (`!`), не является присваиваемым значением.</span><span class="sxs-lookup"><span data-stu-id="187df-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="187df-136">Следовательно, при изменении базового значения нужно вместо этого оператора использовать оператор присваивания (`:=`).</span><span class="sxs-lookup"><span data-stu-id="187df-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="187df-137">И свойство `Value`, и поле `contents` являются присваиваемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="187df-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="187df-138">Следовательно, их можно использовать для доступа к базовому значению или его изменения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="187df-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="187df-139">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="187df-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="187df-140">Поле `contents` предусмотрено для совместимости с другими версиями языка ML, и его наличие приводит к выводу предупреждения в процессе компиляции.</span><span class="sxs-lookup"><span data-stu-id="187df-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="187df-141">Для отключения этого предупреждения используется параметр компилятора `--mlcompatibility`.</span><span class="sxs-lookup"><span data-stu-id="187df-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="187df-142">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="187df-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="187df-143">Следующий код иллюстрирует использование ссылочных ячеек при передаче параметров.</span><span class="sxs-lookup"><span data-stu-id="187df-143">The following code illustrates the use of reference cells in parameter passing.</span></span> <span data-ttu-id="187df-144">Тип Incrementor имеет метод приращения, который принимает параметр, включающий byref в типе параметра.</span><span class="sxs-lookup"><span data-stu-id="187df-144">The Incrementor type has a method Increment that takes a parameter that includes byref in the parameter type.</span></span> <span data-ttu-id="187df-145">Byref в типе параметра указывает, что вызывающие объекты должны передавать ссылочную ячейку или адрес обычной переменной заданного типа, в этом вариантов int. Оставшийся код иллюстрирует вызов метода инкремента с обоими этими типами аргументов, а также показано использование оператора ссылки на переменную для создания ссылочной ячейки (ref myDelta1).</span><span class="sxs-lookup"><span data-stu-id="187df-145">The byref in the parameter type indicates that callers must pass a reference cell or the address of a typical variable of the specified type, in this case int. The remaining code illustrates how to call Increment with both of these types of arguments, and shows the use of the ref operator on a variable to create a reference cell (ref myDelta1).</span></span> <span data-ttu-id="187df-146">Затем показано использование оператора взятия адреса (&amp;) для формирования соответствующего аргумента.</span><span class="sxs-lookup"><span data-stu-id="187df-146">It then shows the use of the address-of operator (&amp;) to generate an appropriate argument.</span></span> <span data-ttu-id="187df-147">Наконец метод Increment вызывается снова путем использования ссылочной ячейки, объявленной с помощью привязки let.</span><span class="sxs-lookup"><span data-stu-id="187df-147">Finally, the Increment method is called again by using a reference cell that is declared by using a let binding.</span></span> <span data-ttu-id="187df-148">В последней строке кода демонстрируется использование!</span><span class="sxs-lookup"><span data-stu-id="187df-148">The final line of code demonstrates the use of the !</span></span> <span data-ttu-id="187df-149">оператор разыменования ссылочной ячейки для печати.</span><span class="sxs-lookup"><span data-stu-id="187df-149">operator to dereference the reference cell for printing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

<span data-ttu-id="187df-150">Дополнительные сведения о передаче по ссылке см. в разделе [параметры и аргументы](parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="187df-150">For more information about how to pass by reference, see [Parameters and Arguments](parameters-and-arguments.md).</span></span>

>[!NOTE]
<span data-ttu-id="187df-151">Программистам на C# следует знать, что этот ref работает по-разному в F #, чем в C#.</span><span class="sxs-lookup"><span data-stu-id="187df-151">C# programmers should know that ref works differently in F# than it does in C#.</span></span> <span data-ttu-id="187df-152">Например использование ref при передаче аргумента имеет тот же эффект в F # как в C#.</span><span class="sxs-lookup"><span data-stu-id="187df-152">For example, the use of ref when you pass an argument does not have the same effect in F# as it does in C#.</span></span>

>[!NOTE]
<span data-ttu-id="187df-153">`mutable` переменные могут быть автоматически повышена до `'a ref` Если отслеживается замыкание; см. в разделе [значения](values/index.md).</span><span class="sxs-lookup"><span data-stu-id="187df-153">`mutable` variables may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="consuming-c-ref-returns"></a><span data-ttu-id="187df-154">Использование C# `ref` возвращает</span><span class="sxs-lookup"><span data-stu-id="187df-154">Consuming C# `ref` returns</span></span>

<span data-ttu-id="187df-155">Начиная с версии F # 4.1, можно использовать `ref` возвращает, созданный на языке C#.</span><span class="sxs-lookup"><span data-stu-id="187df-155">Starting with F# 4.1, you can consume `ref` returns generated in C#.</span></span>  <span data-ttu-id="187df-156">Результатом такой вызов является `byref<_>` указатель.</span><span class="sxs-lookup"><span data-stu-id="187df-156">The result of such a call is a `byref<_>` pointer.</span></span>

<span data-ttu-id="187df-157">Следующий метод C#:</span><span class="sxs-lookup"><span data-stu-id="187df-157">The following C# method:</span></span>

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

<span data-ttu-id="187df-158">Можно прозрачно использовать с F # с никакой специальный синтаксис:</span><span class="sxs-lookup"><span data-stu-id="187df-158">Can be transparently called by F# with no special syntax:</span></span>

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

<span data-ttu-id="187df-159">Можно также объявить функции, которые занимают `ref` возвращают в качестве входных данных, например:</span><span class="sxs-lookup"><span data-stu-id="187df-159">You can also declare functions which could take a `ref` return as input, for example:</span></span>

```fsharp
let f (x: byref<int>) = &x
```

<span data-ttu-id="187df-160">В настоящее время нет способа для создания `ref` возвращаемого значения в F #, который можно использовать в C#.</span><span class="sxs-lookup"><span data-stu-id="187df-160">There is currently no way to generate a `ref` return in F# which could be consumed in C#.</span></span>

## <a name="see-also"></a><span data-ttu-id="187df-161">См. также</span><span class="sxs-lookup"><span data-stu-id="187df-161">See also</span></span>

- [<span data-ttu-id="187df-162">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="187df-162">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="187df-163">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="187df-163">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="187df-164">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="187df-164">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
- [<span data-ttu-id="187df-165">Значения</span><span class="sxs-lookup"><span data-stu-id="187df-165">Values</span></span>](values/index.md)
