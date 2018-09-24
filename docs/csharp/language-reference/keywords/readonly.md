---
title: Ключевое слово readonly (справочник по C#)
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d09ce4ea972a3064298eebdf0b8b80999ee8441e
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46586533"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="f399a-102">readonly (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f399a-102">readonly (C# Reference)</span></span>

<span data-ttu-id="f399a-103">Ключевое слово `readonly` — это модификатор, который может использоваться в трех контекстах:</span><span class="sxs-lookup"><span data-stu-id="f399a-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="f399a-104">В [объявлении поля](#readonly-field-example) `readonly` указывает на то, что присвоение значения полю может происходить только при объявлении или в конструкторе этого класса.</span><span class="sxs-lookup"><span data-stu-id="f399a-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span>
- <span data-ttu-id="f399a-105">В [определении `readonly struct`](#readonly-struct-example) `readonly` указывает на то, что `struct` является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="f399a-105">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="f399a-106">В [возврате метода](#ref-readonly-return-example) `ref readonly` модификатор `readonly` указывает, что метод возвращает ссылку, и записи для этой ссылки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="f399a-106">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="f399a-107">Последние два контекста были добавлены в C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="f399a-107">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="f399a-108">Пример поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="f399a-108">Readonly field example</span></span>

<span data-ttu-id="f399a-109">В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="f399a-109">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="f399a-110">Можно присвоить значение полю `readonly` только в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="f399a-110">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="f399a-111">Когда переменная инициализируется в объявлении, например:</span><span class="sxs-lookup"><span data-stu-id="f399a-111">When the variable is initialized in the declaration, for example:</span></span>

```csharp
public readonly int y = 5;
```

- <span data-ttu-id="f399a-112">В конструкторе экземпляра класса, содержащего объявление поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f399a-112">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="f399a-113">В статическом конструкторе класса, содержащего объявление статического поля.</span><span class="sxs-lookup"><span data-stu-id="f399a-113">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="f399a-114">Эти контексты конструктора являются единственными, в которых можно передавать поле `readonly` в качестве параметра [out](out-parameter-modifier.md) или [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="f399a-114">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="f399a-115">Ключевое слово `readonly` отличается от ключевого слова [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="f399a-115">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="f399a-116">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="f399a-116">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="f399a-117">Поле `readonly` может быть инициализировано при объявлении или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="f399a-117">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="f399a-118">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="f399a-118">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="f399a-119">К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f399a-119">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="f399a-120">В предыдущем примере при использовании такого оператора:</span><span class="sxs-lookup"><span data-stu-id="f399a-120">In the preceding example, if you use a statement like the following example:</span></span>

`p2.y = 66;        // Error`

<span data-ttu-id="f399a-121">будет отображено сообщение об ошибке компилятора:</span><span class="sxs-lookup"><span data-stu-id="f399a-121">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="f399a-122">Пример структуры только для чтения</span><span class="sxs-lookup"><span data-stu-id="f399a-122">Readonly struct example</span></span>

<span data-ttu-id="f399a-123">Модификатор `readonly` в определении `struct` объявляет, что структура является **неизменяемой**.</span><span class="sxs-lookup"><span data-stu-id="f399a-123">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="f399a-124">Каждое поле экземпляра `struct` должно быть помечено `readonly`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f399a-124">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="f399a-125">В предыдущем примере используются [автоматические свойства только для чтения](../../properties.md#read-only) для объявления хранилища.</span><span class="sxs-lookup"><span data-stu-id="f399a-125">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="f399a-126">Это указывает компилятору на необходимость создания резервных полей `readonly` для этих свойств.</span><span class="sxs-lookup"><span data-stu-id="f399a-126">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="f399a-127">Можно также объявить поля `readonly` напрямую:</span><span class="sxs-lookup"><span data-stu-id="f399a-127">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="f399a-128">При добавлении поля без пометки `readonly` возникает ошибка компилятора `CS8340`: "Поля экземпляров структур только для чтения должны быть только для чтения".</span><span class="sxs-lookup"><span data-stu-id="f399a-128">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="f399a-129">Пример возвращаемой ссылки только для чтения</span><span class="sxs-lookup"><span data-stu-id="f399a-129">Ref readonly return example</span></span>

<span data-ttu-id="f399a-130">Модификатор `readonly` в `ref return` указывает, что возвращаемую ссылку нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="f399a-130">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="f399a-131">Следующий пример возвращает ссылку на источник.</span><span class="sxs-lookup"><span data-stu-id="f399a-131">The following example returns a reference to the origin.</span></span> <span data-ttu-id="f399a-132">Он использует модификатор `readonly`, чтобы указать, что вызывающие объекты не могут изменять источник:</span><span class="sxs-lookup"><span data-stu-id="f399a-132">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="f399a-133">Необязательно должен возвращаться тип `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="f399a-133">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="f399a-134">Любой тип, возвращаемый `ref`, может возвращаться `ref readonly`</span><span class="sxs-lookup"><span data-stu-id="f399a-134">Any type that can be returned by `ref` can be returned by `ref readonly`</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f399a-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f399a-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f399a-136">См. также</span><span class="sxs-lookup"><span data-stu-id="f399a-136">See also</span></span>

- [<span data-ttu-id="f399a-137">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f399a-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f399a-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f399a-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f399a-139">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f399a-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f399a-140">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="f399a-140">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="f399a-141">const</span><span class="sxs-lookup"><span data-stu-id="f399a-141">const</span></span>](const.md)
- [<span data-ttu-id="f399a-142">Поля</span><span class="sxs-lookup"><span data-stu-id="f399a-142">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
