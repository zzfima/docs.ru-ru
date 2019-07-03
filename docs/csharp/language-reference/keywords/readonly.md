---
title: Справочник по C#. Ключевое слово readonly
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 4a51bb0e854de127c632c28f613a7602bf09f432
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348012"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="cdb2c-102">readonly (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="cdb2c-102">readonly (C# Reference)</span></span>

<span data-ttu-id="cdb2c-103">Ключевое слово `readonly` — это модификатор, который может использоваться в трех контекстах:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="cdb2c-104">В [объявлении поля](#readonly-field-example) `readonly` указывает на то, что присвоение значения полю может происходить только при объявлении или в конструкторе этого класса.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="cdb2c-105">Полю только для чтения можно несколько раз назначить значения в объявлении поля и в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="cdb2c-106">Поле `readonly` нельзя изменять после выхода из конструктора.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-106">A `readonly` field cannot be assigned after the constructor exits.</span></span> <span data-ttu-id="cdb2c-107">Это влечет за собой разные последствия для типов значений и ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-107">That has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="cdb2c-108">Поскольку типы значений содержат данные, поле `readonly` с типом значения является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="cdb2c-109">Ссылочные типы содержат только ссылку на соответствующие данные, а значит поле `readonly` ссылочного типа будет всегда ссылаться на один объект.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="cdb2c-110">Но сам этот объект не является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-110">That object is not immutable.</span></span> <span data-ttu-id="cdb2c-111">Модификатор `readonly` запрещает замену поля другим экземпляром ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="cdb2c-112">Но этот модификатор не препятствует изменению данных экземпляра, на которое ссылается поле только для чтения, в том числе через это поле.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-112">However, the modifier does not prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="cdb2c-113">Видимый извне тип, который содержит видимое извне и доступное только для чтения поле с изменяемым ссылочным типом, может представлять уязвимость и приводить к предупреждению [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types): Не объявляйте изменяющиеся ссылочные типы только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="cdb2c-114">В [определении `readonly struct`](#readonly-struct-example) `readonly` указывает на то, что `struct` является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="cdb2c-115">В [возврате метода](#ref-readonly-return-example) `ref readonly` модификатор `readonly` указывает, что метод возвращает ссылку, и записи для этой ссылки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-115">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="cdb2c-116">Последние два контекста были добавлены в C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-116">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="cdb2c-117">Пример поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="cdb2c-117">Readonly field example</span></span>

<span data-ttu-id="cdb2c-118">В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-118">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="cdb2c-119">Можно присвоить значение полю `readonly` только в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-119">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="cdb2c-120">Когда переменная инициализируется в объявлении, например:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-120">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="cdb2c-121">В конструкторе экземпляра класса, содержащего объявление поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-121">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="cdb2c-122">В статическом конструкторе класса, содержащего объявление статического поля.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-122">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="cdb2c-123">Эти контексты конструктора являются единственными, в которых можно передавать поле `readonly` в качестве параметра [out](out-parameter-modifier.md) или [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="cdb2c-123">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="cdb2c-124">Ключевое слово `readonly` отличается от ключевого слова [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="cdb2c-124">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="cdb2c-125">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-125">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="cdb2c-126">Поле `readonly` может быть назначено несколько раз в объявлении поля и в любом конструкторе.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-126">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="cdb2c-127">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-127">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="cdb2c-128">К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-128">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="cdb2c-129">В предыдущем примере при использовании такого оператора:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-129">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="cdb2c-130">будет отображено сообщение об ошибке компилятора:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-130">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="cdb2c-131">Пример структуры только для чтения</span><span class="sxs-lookup"><span data-stu-id="cdb2c-131">Readonly struct example</span></span>

<span data-ttu-id="cdb2c-132">Модификатор `readonly` в определении `struct` объявляет, что структура является **неизменяемой**.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-132">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="cdb2c-133">Каждое поле экземпляра `struct` должно быть помечено `readonly`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-133">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="cdb2c-134">В предыдущем примере используются [автоматические свойства только для чтения](../../properties.md#read-only) для объявления хранилища.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-134">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="cdb2c-135">Это указывает компилятору на необходимость создания резервных полей `readonly` для этих свойств.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-135">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="cdb2c-136">Можно также объявить поля `readonly` напрямую:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-136">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="cdb2c-137">Добавление поля без отметки `readonly` вызывает ошибку компилятора `CS8340` с информацией о том, что поля экземпляров в структурах только для чтения должны быть доступными только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-137">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="cdb2c-138">Пример возвращаемой ссылки только для чтения</span><span class="sxs-lookup"><span data-stu-id="cdb2c-138">Ref readonly return example</span></span>

<span data-ttu-id="cdb2c-139">Модификатор `readonly` в `ref return` указывает, что возвращаемую ссылку нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-139">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="cdb2c-140">Следующий пример возвращает ссылку на источник.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-140">The following example returns a reference to the origin.</span></span> <span data-ttu-id="cdb2c-141">Он использует модификатор `readonly`, чтобы указать, что вызывающие объекты не могут изменять источник:</span><span class="sxs-lookup"><span data-stu-id="cdb2c-141">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="cdb2c-142">Необязательно должен возвращаться тип `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-142">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="cdb2c-143">Любой тип, возвращаемый из `ref`, может возвращаться из `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-143">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="cdb2c-144">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="cdb2c-144">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cdb2c-145">См. также</span><span class="sxs-lookup"><span data-stu-id="cdb2c-145">See also</span></span>

- [<span data-ttu-id="cdb2c-146">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="cdb2c-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cdb2c-147">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cdb2c-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cdb2c-148">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="cdb2c-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="cdb2c-149">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="cdb2c-149">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="cdb2c-150">const</span><span class="sxs-lookup"><span data-stu-id="cdb2c-150">const</span></span>](const.md)
- [<span data-ttu-id="cdb2c-151">Поля</span><span class="sxs-lookup"><span data-stu-id="cdb2c-151">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
