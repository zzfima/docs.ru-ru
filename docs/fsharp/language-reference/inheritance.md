---
title: Наследование
description: Узнайте, как указать отношения наследования F,s, используя ключевое слово «наследовать».
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401133"
---
# <a name="inheritance"></a><span data-ttu-id="1ff22-103">Наследование</span><span class="sxs-lookup"><span data-stu-id="1ff22-103">Inheritance</span></span>

<span data-ttu-id="1ff22-104">Наследование используется для моделирования отношений «is-a» или субтипирования в объектно-ориентированном программировании.</span><span class="sxs-lookup"><span data-stu-id="1ff22-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="1ff22-105">Определение отношений к наследству</span><span class="sxs-lookup"><span data-stu-id="1ff22-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="1ff22-106">Вы указываете отношения `inherit` наследования, используя ключевое слово в декларации класса.</span><span class="sxs-lookup"><span data-stu-id="1ff22-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="1ff22-107">Основная синтаксическая форма показана в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1ff22-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="1ff22-108">Класс может иметь не более одного прямого базового класса.</span><span class="sxs-lookup"><span data-stu-id="1ff22-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="1ff22-109">Если вы не указали базовый `inherit` класс с помощью ключевого `System.Object`слова, класс косвенно наследует от .</span><span class="sxs-lookup"><span data-stu-id="1ff22-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="1ff22-110">Унаследованные элементы</span><span class="sxs-lookup"><span data-stu-id="1ff22-110">Inherited Members</span></span>

<span data-ttu-id="1ff22-111">Если класс наследует от другого класса, методы и члены базового класса доступны пользователям производных классов, как если бы они были прямыми членами производного класса.</span><span class="sxs-lookup"><span data-stu-id="1ff22-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="1ff22-112">Любые привязки и параметры конструктора являются частными для класса и, следовательно, не могут быть доступны из производных классов.</span><span class="sxs-lookup"><span data-stu-id="1ff22-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="1ff22-113">Ключевое `base` слово доступно в производных классах и относится к экземпляру базового класса.</span><span class="sxs-lookup"><span data-stu-id="1ff22-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="1ff22-114">Он используется как самоижденитель.</span><span class="sxs-lookup"><span data-stu-id="1ff22-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="1ff22-115">Виртуальные методы и переопределения</span><span class="sxs-lookup"><span data-stu-id="1ff22-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="1ff22-116">Виртуальные методы (и свойства) работают несколько иначе в F-по сравнению с другими языками .NET.</span><span class="sxs-lookup"><span data-stu-id="1ff22-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="1ff22-117">Чтобы объявить нового виртуального `abstract` участника, вы используете ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="1ff22-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="1ff22-118">Вы делаете это независимо от того, предоставляете ли вы реализацию по умолчанию для этого метода.</span><span class="sxs-lookup"><span data-stu-id="1ff22-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="1ff22-119">Таким образом, полное определение виртуального метода в базовом классе следует этому шаблону:</span><span class="sxs-lookup"><span data-stu-id="1ff22-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="1ff22-120">И в производном классе переопределение этого виртуального метода следует этому шаблону:</span><span class="sxs-lookup"><span data-stu-id="1ff22-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="1ff22-121">Если вы не сможете пропустить реализацию по умолчанию в базовом классе, базовый класс становится абстрактным классом.</span><span class="sxs-lookup"><span data-stu-id="1ff22-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="1ff22-122">Следующий пример кода иллюстрирует объявление нового `function1` виртуального метода в базовом классе и способпереть переопределить его в производном классе.</span><span class="sxs-lookup"><span data-stu-id="1ff22-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="1ff22-123">Конструкторы и наследование</span><span class="sxs-lookup"><span data-stu-id="1ff22-123">Constructors and Inheritance</span></span>

<span data-ttu-id="1ff22-124">Конструктор для базового класса должен быть вызван в производный класс.</span><span class="sxs-lookup"><span data-stu-id="1ff22-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="1ff22-125">Аргументы для конструктора базового класса отображаются в списке аргументов в предложении. `inherit`</span><span class="sxs-lookup"><span data-stu-id="1ff22-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="1ff22-126">Используемые значения должны определяться на основе аргументов, поставляемых на выводимый класс.</span><span class="sxs-lookup"><span data-stu-id="1ff22-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="1ff22-127">Следующий код показывает базовый класс и производный класс, где полученный класс называет конструктора базового класса в пункте наследования:</span><span class="sxs-lookup"><span data-stu-id="1ff22-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="1ff22-128">В случае нескольких конструкторов можно использовать следующий код.</span><span class="sxs-lookup"><span data-stu-id="1ff22-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="1ff22-129">Первая строка выводимых конструкторов `inherit` класса — это положение, а поля `val` отображаются как явные поля, объявленные ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="1ff22-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="1ff22-130">Для получения дополнительной информации [см. `val` ](./members/explicit-fields-the-val-keyword.md)</span><span class="sxs-lookup"><span data-stu-id="1ff22-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="1ff22-131">Альтернативы наследованию</span><span class="sxs-lookup"><span data-stu-id="1ff22-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="1ff22-132">В тех случаях, когда требуется незначительное изменение типа, рассмотрите возможность использования выражения объекта в качестве альтернативы наследству.</span><span class="sxs-lookup"><span data-stu-id="1ff22-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="1ff22-133">Следующий пример иллюстрирует использование выражения объекта в качестве альтернативы созданию нового производного типа:</span><span class="sxs-lookup"><span data-stu-id="1ff22-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="1ff22-134">Для получения дополнительной информации [Object Expressions](object-expressions.md)о выражениях объектов см.</span><span class="sxs-lookup"><span data-stu-id="1ff22-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="1ff22-135">При создании иерархии объектов рассмотрите возможность использования дискриминируемого соединения вместо наследования.</span><span class="sxs-lookup"><span data-stu-id="1ff22-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="1ff22-136">Дискриминированные союзы могут также моделировать разнообразное поведение различных объектов, которые имеют общий общий тип.</span><span class="sxs-lookup"><span data-stu-id="1ff22-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="1ff22-137">Один дискриминируемый союз часто может устранить необходимость в ряде производных классов, которые являются незначительными вариациями друг друга.</span><span class="sxs-lookup"><span data-stu-id="1ff22-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="1ff22-138">Для получения информации о дискриминируемых профсоюзах [см.](discriminated-unions.md)</span><span class="sxs-lookup"><span data-stu-id="1ff22-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ff22-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ff22-139">See also</span></span>

- [<span data-ttu-id="1ff22-140">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="1ff22-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="1ff22-141">Ссылка на язык F</span><span class="sxs-lookup"><span data-stu-id="1ff22-141">F# Language Reference</span></span>](index.md)
