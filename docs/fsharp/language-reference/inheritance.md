---
title: Наследование
description: Сведения об указании F# связи наследования с помощью ключевого слова «наследовать».
ms.date: 05/16/2016
ms.openlocfilehash: 2fad2ddafbc0174903d3d24be3ce5412f7e1f9ed
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641823"
---
# <a name="inheritance"></a><span data-ttu-id="656d4-103">Наследование</span><span class="sxs-lookup"><span data-stu-id="656d4-103">Inheritance</span></span>

<span data-ttu-id="656d4-104">Наследование используется для моделирования отношения «is-a», или подтипов в объектно ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="656d4-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="656d4-105">Определение отношений наследования</span><span class="sxs-lookup"><span data-stu-id="656d4-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="656d4-106">Определить отношения наследования с помощью `inherit` ключевое слово в объявлении класса.</span><span class="sxs-lookup"><span data-stu-id="656d4-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="656d4-107">В следующем примере показан базовый синтаксическая форма.</span><span class="sxs-lookup"><span data-stu-id="656d4-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="656d4-108">Класс может иметь не более одного прямого базового класса.</span><span class="sxs-lookup"><span data-stu-id="656d4-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="656d4-109">Если вы не укажете базового класса с помощью `inherit` ключевое слово, неявно наследуется от `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="656d4-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="656d4-110">Унаследованные члены</span><span class="sxs-lookup"><span data-stu-id="656d4-110">Inherited Members</span></span>

<span data-ttu-id="656d4-111">Если класс наследует от другого класса, методы и члены базового класса доступны пользователям производного класса как будто они являются непосредственными членами производного класса.</span><span class="sxs-lookup"><span data-stu-id="656d4-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="656d4-112">Все привязки let и параметры конструктора являются закрытыми для класса и, таким образом, нельзя обращаться из производных классов.</span><span class="sxs-lookup"><span data-stu-id="656d4-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="656d4-113">Ключевое слово `base` доступно в производных классах и относится к экземпляру базового класса.</span><span class="sxs-lookup"><span data-stu-id="656d4-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="656d4-114">Он используется как идентификатор самого себя.</span><span class="sxs-lookup"><span data-stu-id="656d4-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="656d4-115">Виртуальные методы и переопределений</span><span class="sxs-lookup"><span data-stu-id="656d4-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="656d4-116">Виртуальные методы (и свойства) работают немного по-разному в F# по сравнению с другими языками .NET.</span><span class="sxs-lookup"><span data-stu-id="656d4-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="656d4-117">Чтобы объявить новый виртуальный член, следует использовать `abstract` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="656d4-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="656d4-118">Это можно сделать независимо от того, может ли предоставлять реализацию по умолчанию для этого метода.</span><span class="sxs-lookup"><span data-stu-id="656d4-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="656d4-119">Таким образом, полное определение виртуального метода в базовом классе соответствует следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="656d4-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="656d4-120">И в производном классе, переопределение данного виртуального метода соответствует следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="656d4-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="656d4-121">Если опустить реализация по умолчанию в базовом классе, базовый класс становится абстрактным классом.</span><span class="sxs-lookup"><span data-stu-id="656d4-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="656d4-122">В следующем примере кода показано объявление нового виртуального метода `function1` в базовый класс и его переопределении в производном классе.</span><span class="sxs-lookup"><span data-stu-id="656d4-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="656d4-123">Конструкторы и наследование</span><span class="sxs-lookup"><span data-stu-id="656d4-123">Constructors and Inheritance</span></span>

<span data-ttu-id="656d4-124">Необходимо вызвать конструктор базового класса в производном классе.</span><span class="sxs-lookup"><span data-stu-id="656d4-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="656d4-125">Аргументы для конструктора базового класса, отображаются в списке аргументов в `inherit` предложение.</span><span class="sxs-lookup"><span data-stu-id="656d4-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="656d4-126">Значения, которые используются должны определяться из аргументов, предоставляемых конструктором производного класса.</span><span class="sxs-lookup"><span data-stu-id="656d4-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="656d4-127">В следующем коде показано базовый класс и производный класс, где производном классе вызывает конструктор базового класса в выражении inherit:</span><span class="sxs-lookup"><span data-stu-id="656d4-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="656d4-128">В случае несколько конструкторов можно использовать следующий код.</span><span class="sxs-lookup"><span data-stu-id="656d4-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="656d4-129">В первой строке конструкторов производных классов `inherit` предложение, а также поля отображаются как явные поля, объявленные с `val` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="656d4-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="656d4-130">Дополнительные сведения см. в разделе [явные поля: `val` Ключевое слово](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="656d4-130">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="656d4-131">Альтернативы наследованию</span><span class="sxs-lookup"><span data-stu-id="656d4-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="656d4-132">В случаях, где требуется незначительное изменение типа следует использовать выражение объекта вместо наследования.</span><span class="sxs-lookup"><span data-stu-id="656d4-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="656d4-133">Следующий пример иллюстрирует использование выражения объекта в качестве альтернативы созданию нового производного типа:</span><span class="sxs-lookup"><span data-stu-id="656d4-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="656d4-134">Дополнительные сведения о выражениях объектов, см. в разделе [выражения объекта](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="656d4-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="656d4-135">При создании иерархии объектов, рассмотрите возможность использования размеченное объединение вместо наследования.</span><span class="sxs-lookup"><span data-stu-id="656d4-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="656d4-136">Размеченные объединения также могут моделировать изменение поведения различных объектов, которые совместно используют общий тип.</span><span class="sxs-lookup"><span data-stu-id="656d4-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="656d4-137">Использование одного размеченного объединения также порой устраняет потребность в несколько производных классов, которые незначительно отличаются друг от друга.</span><span class="sxs-lookup"><span data-stu-id="656d4-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="656d4-138">Сведения о размеченные объединения, см. в разделе [размеченные объединения](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="656d4-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="656d4-139">См. также</span><span class="sxs-lookup"><span data-stu-id="656d4-139">See also</span></span>

- [<span data-ttu-id="656d4-140">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="656d4-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="656d4-141">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="656d4-141">F# Language Reference</span></span>](index.md)
