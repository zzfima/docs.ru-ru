---
title: Абстрактные классы (F#)
description: 'Дополнительные сведения о F # абстрактные классы, которые оставляют некоторые или все члены не требует дополнительных инструментов и представляют общие функции широкого набора типов объектов.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0d7ca996de89c44a5cfb9197c1b515741a2303df
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="abstract-classes"></a><span data-ttu-id="773bb-103">Абстрактные классы</span><span class="sxs-lookup"><span data-stu-id="773bb-103">Abstract Classes</span></span>

<span data-ttu-id="773bb-104">*Абстрактные классы* — это классы, которые оставляют некоторые или все члены не требует дополнительных инструментов, которых могут быть предоставлены реализации производных классов.</span><span class="sxs-lookup"><span data-stu-id="773bb-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="773bb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="773bb-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="773bb-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="773bb-106">Remarks</span></span>
<span data-ttu-id="773bb-107">В объектно ориентированном программировании абстрактный класс используется как базовый класс иерархии и представляющим общую функциональность широкого набора типов объектов.</span><span class="sxs-lookup"><span data-stu-id="773bb-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="773bb-108">Имя «abstract» указывает на то, абстрактные классы часто не соответствуют непосредственно на конкретных объектов в определенной области.</span><span class="sxs-lookup"><span data-stu-id="773bb-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="773bb-109">Тем не менее они представляют, что множества разных конкретных объектов являются общими.</span><span class="sxs-lookup"><span data-stu-id="773bb-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="773bb-110">Абстрактные классы должны иметь `AbstractClass` атрибута.</span><span class="sxs-lookup"><span data-stu-id="773bb-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="773bb-111">Может реализован и нереализованные члены.</span><span class="sxs-lookup"><span data-stu-id="773bb-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="773bb-112">Использование термина *абстрактный* при применении к класс является таким же, как и в других языках .NET; тем не менее, использование термина *абстрактный* при применении к методам (и свойства), немного отличается в языке F # из его Используйте в других языках .NET.</span><span class="sxs-lookup"><span data-stu-id="773bb-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="773bb-113">В языке F #, если метод, помеченный атрибутом `abstract` ключевое слово, это означает, что член имеет вход, известный как *виртуальная ячейка отправки*, во внутренней таблице виртуальных функций этого типа.</span><span class="sxs-lookup"><span data-stu-id="773bb-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="773bb-114">Другими словами, метод является виртуальным, несмотря на то что `virtual` ключевое слово не используется в языке F #.</span><span class="sxs-lookup"><span data-stu-id="773bb-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="773bb-115">Ключевое слово `abstract` используется для виртуальных методов, независимо от того, что метод реализуется.</span><span class="sxs-lookup"><span data-stu-id="773bb-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="773bb-116">Объявление виртуальная ячейка отправки отделен от определение метода для него диспетчеризации.</span><span class="sxs-lookup"><span data-stu-id="773bb-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="773bb-117">Таким образом, F # эквивалентом виртуальный метод объявление и определение в другом языке .NET является сочетание объявления абстрактного метода и отдельного определения с помощью `default` ключевое слово или `override` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="773bb-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="773bb-118">Дополнительные сведения и примеры см. в разделе [методы](members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="773bb-118">For more information and examples, see [Methods](members/methods.md).</span></span>

<span data-ttu-id="773bb-119">Класс считается абстрактным, только если имеются абстрактные методы, которые объявлены, но не определен.</span><span class="sxs-lookup"><span data-stu-id="773bb-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="773bb-120">Таким образом классы, имеющие абстрактные методы не обязательно абстрактные классы.</span><span class="sxs-lookup"><span data-stu-id="773bb-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="773bb-121">Если класс имеет неопределенные абстрактные методы, не используйте **AbstractClass** атрибута.</span><span class="sxs-lookup"><span data-stu-id="773bb-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="773bb-122">В предыдущем синтаксисе *модификатор доступа* может быть `public`, `private` или `internal`.</span><span class="sxs-lookup"><span data-stu-id="773bb-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="773bb-123">Дополнительные сведения см. в статье [Управление доступом](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="773bb-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="773bb-124">Как и в случае с другими типами, абстрактные классы могут иметь базовый класс и один или несколько базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="773bb-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="773bb-125">Каждый базовый класс или интерфейс отображается на отдельной строке вместе с `inherit` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="773bb-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="773bb-126">Определение типа абстрактного класса может содержать полностью определенных членов, но он также может содержать абстрактные члены.</span><span class="sxs-lookup"><span data-stu-id="773bb-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="773bb-127">В предыдущем синтаксисе отдельно показан синтаксис для абстрактных членов.</span><span class="sxs-lookup"><span data-stu-id="773bb-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="773bb-128">В этом синтаксисе *сигнатура типа* элемента в список, содержащий типы параметров, в порядке и возвращаемые типы отделяется `->` маркеры и/или `*` маркеры соответствующим образом для каррированные и включать в кортежи параметры.</span><span class="sxs-lookup"><span data-stu-id="773bb-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="773bb-129">Синтаксис сигнатур типов абстрактных членов совпадает со значением, используемые в файлах подписи и которая отображается IntelliSense в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="773bb-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="773bb-130">Следующий код иллюстрирует абстрактный класс фигуры, который имеет два неабстрактных производных классов, квадратные и круг.</span><span class="sxs-lookup"><span data-stu-id="773bb-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="773bb-131">В примере показано использование абстрактных классов, методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="773bb-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="773bb-132">В примере абстрактный класс Shape представляет общие элементы конкретных объектов круг и квадрат.</span><span class="sxs-lookup"><span data-stu-id="773bb-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="773bb-133">Общие функции всех фигур (в двухмерной системе координат) абстрактно класс Shape: положение на сетке, угол поворота и свойства области и периметра.</span><span class="sxs-lookup"><span data-stu-id="773bb-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="773bb-134">Они могут быть переопределены, за исключением положения, поведение которого невозможно изменить отдельных фигур.</span><span class="sxs-lookup"><span data-stu-id="773bb-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="773bb-135">Можно переопределить метод поворота, как в классе Circle его инвариантом вращения.</span><span class="sxs-lookup"><span data-stu-id="773bb-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="773bb-136">Поэтому в классе Circle метод поворота заменяется на метод, который не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="773bb-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="773bb-137">**Выходные данные:**</span><span class="sxs-lookup"><span data-stu-id="773bb-137">**Output:**</span></span>

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="773bb-138">См. также</span><span class="sxs-lookup"><span data-stu-id="773bb-138">See Also</span></span>
[<span data-ttu-id="773bb-139">Классы</span><span class="sxs-lookup"><span data-stu-id="773bb-139">Classes</span></span>](classes.md)

[<span data-ttu-id="773bb-140">Члены</span><span class="sxs-lookup"><span data-stu-id="773bb-140">Members</span></span>](members/index.md)

[<span data-ttu-id="773bb-141">Методы</span><span class="sxs-lookup"><span data-stu-id="773bb-141">Methods</span></span>](members/methods.md)

[<span data-ttu-id="773bb-142">Свойства</span><span class="sxs-lookup"><span data-stu-id="773bb-142">Properties</span></span>](members/Properties.md)
