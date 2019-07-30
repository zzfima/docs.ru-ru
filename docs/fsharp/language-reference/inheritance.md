---
title: Наследование
description: Узнайте, как указать F# отношения наследования с помощью ключевого слова inherit.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627662"
---
# <a name="inheritance"></a><span data-ttu-id="7e650-103">Наследование</span><span class="sxs-lookup"><span data-stu-id="7e650-103">Inheritance</span></span>

<span data-ttu-id="7e650-104">Наследование используется для моделирования связи «является-a» или подтипов в объектно-ориентированном программировании.</span><span class="sxs-lookup"><span data-stu-id="7e650-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="7e650-105">Указание отношений наследования</span><span class="sxs-lookup"><span data-stu-id="7e650-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="7e650-106">Отношения наследования указываются с помощью `inherit` ключевого слова в объявлении класса.</span><span class="sxs-lookup"><span data-stu-id="7e650-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="7e650-107">В следующем примере показана базовая синтаксическая форма.</span><span class="sxs-lookup"><span data-stu-id="7e650-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="7e650-108">Класс может иметь не более одного прямого базового класса.</span><span class="sxs-lookup"><span data-stu-id="7e650-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="7e650-109">Если базовый класс не указан с помощью `inherit` ключевого слова, класс неявно наследует от. `System.Object`</span><span class="sxs-lookup"><span data-stu-id="7e650-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="7e650-110">Унаследованные члены</span><span class="sxs-lookup"><span data-stu-id="7e650-110">Inherited Members</span></span>

<span data-ttu-id="7e650-111">Если класс наследуется от другого класса, методы и члены базового класса становятся доступными для пользователей производного класса, как если бы они были прямыми членами производного класса.</span><span class="sxs-lookup"><span data-stu-id="7e650-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="7e650-112">Все привязки let и параметры конструктора являются закрытыми для класса, поэтому к ним нельзя получить доступ из производных классов.</span><span class="sxs-lookup"><span data-stu-id="7e650-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="7e650-113">Ключевое `base` слово доступно в производных классах и ссылается на экземпляр базового класса.</span><span class="sxs-lookup"><span data-stu-id="7e650-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="7e650-114">Он используется как идентификатор Self.</span><span class="sxs-lookup"><span data-stu-id="7e650-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="7e650-115">Виртуальные методы и переопределения</span><span class="sxs-lookup"><span data-stu-id="7e650-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="7e650-116">Виртуальные методы (и свойства) работают несколько иначе F# по сравнению с другими языками .NET.</span><span class="sxs-lookup"><span data-stu-id="7e650-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="7e650-117">Для объявления нового виртуального члена используется `abstract` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7e650-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="7e650-118">Это делается независимо от того, предоставляется ли реализация по умолчанию для этого метода.</span><span class="sxs-lookup"><span data-stu-id="7e650-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="7e650-119">Таким образом, полное определение виртуального метода в базовом классе соответствует следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="7e650-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="7e650-120">В производном классе переопределение этого виртуального метода выполняется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7e650-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="7e650-121">Если опустить реализацию по умолчанию в базовом классе, базовый класс станет абстрактным классом.</span><span class="sxs-lookup"><span data-stu-id="7e650-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="7e650-122">В следующем примере кода показано объявление нового виртуального метода `function1` в базовом классе и его переопределение в производном классе.</span><span class="sxs-lookup"><span data-stu-id="7e650-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="7e650-123">Конструкторы и наследование</span><span class="sxs-lookup"><span data-stu-id="7e650-123">Constructors and Inheritance</span></span>

<span data-ttu-id="7e650-124">Конструктор для базового класса должен вызываться в производном классе.</span><span class="sxs-lookup"><span data-stu-id="7e650-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="7e650-125">Аргументы для конструктора базового класса появятся в списке аргументов в `inherit` предложении.</span><span class="sxs-lookup"><span data-stu-id="7e650-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="7e650-126">Используемые значения должны быть определены из аргументов, передаваемых конструктору производного класса.</span><span class="sxs-lookup"><span data-stu-id="7e650-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="7e650-127">В следующем коде показан базовый класс и производный класс, где производный класс вызывает конструктор базового класса в предложении inherit:</span><span class="sxs-lookup"><span data-stu-id="7e650-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="7e650-128">В случае с несколькими конструкторами можно использовать следующий код.</span><span class="sxs-lookup"><span data-stu-id="7e650-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="7e650-129">Первая строка конструкторов производного класса является `inherit` предложением, а поля отображаются как явные поля, объявленные `val` с ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="7e650-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="7e650-130">Дополнительные сведения см. в [разделе явные поля: Ключевое](./members/explicit-fields-the-val-keyword.md)слово. `val`</span><span class="sxs-lookup"><span data-stu-id="7e650-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="7e650-131">Альтернативы наследованию</span><span class="sxs-lookup"><span data-stu-id="7e650-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="7e650-132">В случаях, когда требуется незначительное изменение типа, рассмотрите возможность использования выражения объекта в качестве альтернативы наследованию.</span><span class="sxs-lookup"><span data-stu-id="7e650-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="7e650-133">В следующем примере показано использование выражения объекта в качестве альтернативы созданию нового производного типа:</span><span class="sxs-lookup"><span data-stu-id="7e650-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="7e650-134">Дополнительные сведения о выражениях объектов см. в разделе [выражения объекта](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7e650-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="7e650-135">При создании иерархий объектов рассмотрите возможность использования размеченного объединения вместо наследования.</span><span class="sxs-lookup"><span data-stu-id="7e650-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="7e650-136">Размеченные объединения могут также моделировать поведение различных объектов, совместно использующих общий тип.</span><span class="sxs-lookup"><span data-stu-id="7e650-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="7e650-137">Одно размеченное объединение часто может устранить необходимость в ряде производных классов, которые являются незначительными вариантами друг друга.</span><span class="sxs-lookup"><span data-stu-id="7e650-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="7e650-138">Сведения о размеченных объединениях см. в разделе [Размеченные объединения](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="7e650-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e650-139">См. также</span><span class="sxs-lookup"><span data-stu-id="7e650-139">See also</span></span>

- [<span data-ttu-id="7e650-140">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="7e650-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="7e650-141">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="7e650-141">F# Language Reference</span></span>](index.md)
