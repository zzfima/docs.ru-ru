---
title: Справочник по C#. Ключевое слово readonly
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: f9fa6f893e7f999564c4dcb43d40755547d3c793
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713122"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="a1bb0-102">readonly (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a1bb0-102">readonly (C# Reference)</span></span>

<span data-ttu-id="a1bb0-103">Ключевое слово `readonly` — это модификатор, который может использоваться в четырех контекстах:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="a1bb0-104">В [объявлении поля](#readonly-field-example)`readonly` указывает на то, что присвоение значения полю может происходить только при объявлении или в конструкторе этого класса.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="a1bb0-105">Полю только для чтения можно несколько раз назначить значения в объявлении поля и в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="a1bb0-106">Поле `readonly` нельзя изменять после выхода из конструктора.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="a1bb0-107">Это правило влечет за собой разные последствия для типов значений и ссылочных типов:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="a1bb0-108">Поскольку типы значений содержат данные, поле `readonly` с типом значения является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="a1bb0-109">Ссылочные типы содержат только ссылку на соответствующие данные, а значит поле `readonly` ссылочного типа будет всегда ссылаться на один объект.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="a1bb0-110">Но сам этот объект не является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-110">That object isn't immutable.</span></span> <span data-ttu-id="a1bb0-111">Модификатор `readonly` запрещает замену поля другим экземпляром ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="a1bb0-112">Но этот модификатор не препятствует изменению данных экземпляра, на которое ссылается поле только для чтения, в том числе через это поле.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="a1bb0-113">Видимый извне тип, который содержит видимое извне и доступное только для чтения поле с изменяемым ссылочным типом, может представлять уязвимость и приводить к предупреждению [CA2104](/visualstudio/code-quality/ca2104): Не объявляйте изменяющиеся ссылочные типы только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="a1bb0-114">В [определении `readonly struct`](#readonly-struct-example)`readonly` указывает на то, что `struct` является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="a1bb0-115">В [определения элемента `readonly`](#readonly-member-examples)`readonly` указывает, что элемент `struct` не изменяет внутреннее состояние структуры.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-115">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="a1bb0-116">В [возврате метода `ref readonly`](#ref-readonly-return-example) модификатор `readonly` указывает, что метод возвращает ссылку, и записи для этой ссылки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-116">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="a1bb0-117">Контексты `readonly struct` и `ref readonly` были добавлены в C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-117">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="a1bb0-118">Члены структуры `readonly` добавлены в C# 8.0</span><span class="sxs-lookup"><span data-stu-id="a1bb0-118">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="a1bb0-119">Пример поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="a1bb0-119">Readonly field example</span></span>

<span data-ttu-id="a1bb0-120">В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-120">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="a1bb0-121">Можно присвоить значение полю `readonly` только в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-121">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="a1bb0-122">Когда переменная инициализируется в объявлении, например:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-122">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="a1bb0-123">В конструкторе экземпляра класса, содержащего объявление поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-123">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="a1bb0-124">В статическом конструкторе класса, содержащего объявление статического поля.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-124">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="a1bb0-125">Эти контексты конструктора являются единственными, в которых можно передавать поле `readonly` в качестве параметра [out](out-parameter-modifier.md) или [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="a1bb0-125">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="a1bb0-126">Ключевое слово `readonly` отличается от ключевого слова [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="a1bb0-126">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="a1bb0-127">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-127">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="a1bb0-128">Поле `readonly` может быть назначено несколько раз в объявлении поля и в любом конструкторе.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-128">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="a1bb0-129">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-129">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="a1bb0-130">К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-130">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="a1bb0-131">В предыдущем примере при использовании такого оператора:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-131">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="a1bb0-132">будет отображено сообщение об ошибке компилятора:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-132">you'll get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="a1bb0-133">Пример структуры только для чтения</span><span class="sxs-lookup"><span data-stu-id="a1bb0-133">Readonly struct example</span></span>

<span data-ttu-id="a1bb0-134">Модификатор `readonly` в определении `struct` объявляет, что структура является **неизменяемой**.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-134">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="a1bb0-135">Каждое поле экземпляра `struct` должно быть помечено `readonly`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-135">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="a1bb0-136">В предыдущем примере используются [автоматические свойства только для чтения](../../properties.md#read-only) для объявления хранилища.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-136">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="a1bb0-137">Это указывает компилятору на необходимость создания резервных полей `readonly` для этих свойств.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-137">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="a1bb0-138">Можно также объявить поля `readonly` напрямую:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-138">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="a1bb0-139">Добавление поля без отметки `readonly` вызывает ошибку компилятора `CS8340` с информацией о том, что поля экземпляров в структурах только для чтения должны быть доступными только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-139">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="a1bb0-140">Примеры членов только для чтения</span><span class="sxs-lookup"><span data-stu-id="a1bb0-140">Readonly member examples</span></span>

<span data-ttu-id="a1bb0-141">В других случаях вы можете создать структуру, которая поддерживает изменения.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-141">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="a1bb0-142">В таких случаях некоторые члены экземпляров, вероятно, не изменят внутреннее состояние структуры.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-142">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="a1bb0-143">Эти члены экземпляра можно объявить с помощью модификатора `readonly`.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-143">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="a1bb0-144">Компилятор применяет ваше намерение.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-144">The compiler enforces your intent.</span></span> <span data-ttu-id="a1bb0-145">Если этот член изменяет состояние напрямую или обращается к члену, который также не объявлен с модификатором `readonly`, результатом является ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-145">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="a1bb0-146">Модификатор `readonly` является допустимым для членов `struct`, а не объявлений членов `class` или `interface`.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-146">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="a1bb0-147">Вы получаете два преимущества, применяя модификатор `readonly` к применимым методам `struct`.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-147">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="a1bb0-148">Самое важное — компилятор применяет ваше намерение.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-148">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="a1bb0-149">Код, который изменяет состояние, не является допустимым в методе `readonly`.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-149">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="a1bb0-150">Компилятор также может использовать модификатор `readonly` для включения оптимизации производительности.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-150">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="a1bb0-151">Когда большие типы `struct` передаются по ссылке `in`, компилятор должен создать защитную копию, если состояние структуры можно изменить.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-151">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="a1bb0-152">Если доступ осуществляется только к членам `readonly`, компилятор может не создавать защитную копию.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-152">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="a1bb0-153">Модификатор `readonly` является допустимым для большинства членов `struct`, включая методы, которые переопределяют методы, объявленные в <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-153">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a1bb0-154">Существуют некоторые ограничения:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-154">There are some restrictions:</span></span>

- <span data-ttu-id="a1bb0-155">Нельзя объявлять статические методы или свойства `readonly`.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-155">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="a1bb0-156">Нельзя объявлять конструкторы `readonly`.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-156">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="a1bb0-157">Можно добавить модификатор `readonly` к объявлению свойства или индексатора:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-157">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="a1bb0-158">Можно также добавить модификатор `readonly` к отдельным методам доступа `get` или `set` свойства или индексатора:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-158">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="a1bb0-159">Нельзя добавить модификатор `readonly` одновременно к свойству и к одному или нескольким методам доступа этого свойства.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-159">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="a1bb0-160">Это же ограничение применяется к индексаторам.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-160">That same restriction applies to indexers.</span></span>

<span data-ttu-id="a1bb0-161">Компилятор неявно применяет модификатор `readonly` к автоматически реализуемым свойствам, в которых код, реализованный компилятором, не изменяет состояние.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-161">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="a1bb0-162">Это эквивалентно следующим объявлениям:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-162">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
``` 

<span data-ttu-id="a1bb0-163">Вы можете добавить модификатор `readonly` в эти места, но это не будет иметь никакого эффекта.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-163">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="a1bb0-164">Нельзя добавить модификатор `readonly` к методу задания автоматически реализуемого свойства или к автоматически реализуемому свойству, доступному для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-164">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="a1bb0-165">Пример возвращаемой ссылки только для чтения</span><span class="sxs-lookup"><span data-stu-id="a1bb0-165">Ref readonly return example</span></span>

<span data-ttu-id="a1bb0-166">Модификатор `readonly` в `ref return` указывает, что возвращаемую ссылку нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-166">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="a1bb0-167">Следующий пример возвращает ссылку на источник.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-167">The following example returns a reference to the origin.</span></span> <span data-ttu-id="a1bb0-168">Он использует модификатор `readonly`, чтобы указать, что вызывающие объекты не могут изменять источник:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-168">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="a1bb0-169">Необязательно должен возвращаться тип `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-169">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="a1bb0-170">Любой тип, возвращаемый из `ref`, может возвращаться из `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="a1bb0-170">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a1bb0-171">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a1bb0-171">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="a1bb0-172">Вы также можете ознакомиться с предложениями языковых спецификаций:</span><span class="sxs-lookup"><span data-stu-id="a1bb0-172">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="a1bb0-173">Ссылка и структура readonly</span><span class="sxs-lookup"><span data-stu-id="a1bb0-173">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="a1bb0-174">Члены структуры readonly</span><span class="sxs-lookup"><span data-stu-id="a1bb0-174">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="a1bb0-175">См. также</span><span class="sxs-lookup"><span data-stu-id="a1bb0-175">See also</span></span>

- [<span data-ttu-id="a1bb0-176">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a1bb0-176">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a1bb0-177">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a1bb0-177">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a1bb0-178">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a1bb0-178">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a1bb0-179">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="a1bb0-179">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a1bb0-180">const</span><span class="sxs-lookup"><span data-stu-id="a1bb0-180">const</span></span>](const.md)
- [<span data-ttu-id="a1bb0-181">Поля</span><span class="sxs-lookup"><span data-stu-id="a1bb0-181">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
