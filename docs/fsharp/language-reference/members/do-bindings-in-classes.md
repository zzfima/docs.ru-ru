---
title: Привязки do в классах (F#)
description: Сведения об использовании привязки в определение класса, который выполняет действия, при создании объекта или при первом использовании тип «do» F#.
ms.date: 05/16/2016
ms.openlocfilehash: e54a5bde52bf6973cc338c929ba99e6fd5b53127
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43801545"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="eede1-103">Привязки do в классах</span><span class="sxs-lookup"><span data-stu-id="eede1-103">do Bindings in Classes</span></span>

<span data-ttu-id="eede1-104">Объект `do` привязки в определении класса выполняет действия, при создании объекта или, для статического `do` привязки, когда тип первого использования.</span><span class="sxs-lookup"><span data-stu-id="eede1-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="eede1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eede1-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="eede1-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="eede1-106">Remarks</span></span>

<span data-ttu-id="eede1-107">Объект `do` привязки отображается вместе с параметром, или после `let` привязки, но до определения членов в определении класса.</span><span class="sxs-lookup"><span data-stu-id="eede1-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="eede1-108">Несмотря на то что `do` ключевое слово является необязательным для `do` привязки на уровне модуля, оно является обязательным для `do` привязки в определении класса.</span><span class="sxs-lookup"><span data-stu-id="eede1-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="eede1-109">Для создания всех объектов любого заданного типа к нестатическому `do` привязок и нестатические `let` выполняются в порядке, в котором они появляются в определении класса.</span><span class="sxs-lookup"><span data-stu-id="eede1-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="eede1-110">Несколько `do` привязки может произойти в одном типе.</span><span class="sxs-lookup"><span data-stu-id="eede1-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="eede1-111">Нестатические `let` привязки и нестатические `do` становятся основной первичный конструктор.</span><span class="sxs-lookup"><span data-stu-id="eede1-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="eede1-112">Код в нестатических `do` раздел привязок может ссылаться на первичный конструктор параметров и значений или функций, которые определены в `let` раздел привязок.</span><span class="sxs-lookup"><span data-stu-id="eede1-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="eede1-113">Нестатические `do` привязки можно получить доступ члены класса, если класс имеет собственный идентификатор, определяемый `as` ключевого слова в заголовке класса, а, пока все случаи использования эти члены будут дополнены собственный идентификатор для класса.</span><span class="sxs-lookup"><span data-stu-id="eede1-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="eede1-114">Так как `let` привязки инициализируют закрытые поля класса, это часто бывает необходимо, чтобы обеспечить правильное поведение членов должным образом, `do` привязки обычно помещаются после `let` привязки, так что код в `do` can привязки выполните с полностью инициализированный объект.</span><span class="sxs-lookup"><span data-stu-id="eede1-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="eede1-115">Если пользовательским кодом предпринимается попытка использовать член до завершения инициализации, возникает исключение InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="eede1-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="eede1-116">Статические `do` привязки могут ссылаться на статические члены или поля включающего класса, но не члены или поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="eede1-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="eede1-117">Статические `do` привязки становятся частью статический инициализатор для класса, который гарантированно выполняется до первого использования класса.</span><span class="sxs-lookup"><span data-stu-id="eede1-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="eede1-118">Атрибуты учитываются для `do` привязки в типах.</span><span class="sxs-lookup"><span data-stu-id="eede1-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="eede1-119">Если атрибут является обязательным для кода, который выполняется в `do` привязки, он должен применяться к первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="eede1-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="eede1-120">В следующем коде класс имеет статическое `do` привязки и нестатическую `do` привязки.</span><span class="sxs-lookup"><span data-stu-id="eede1-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="eede1-121">Объект имеет конструктор, который имеет два параметра `a` и `b`, и два закрытых поля определяются в `let` привязки для класса.</span><span class="sxs-lookup"><span data-stu-id="eede1-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="eede1-122">Также определяются два свойства.</span><span class="sxs-lookup"><span data-stu-id="eede1-122">Two properties are also defined.</span></span> <span data-ttu-id="eede1-123">Все они находятся в области в нестатических `do` раздел привязок, как продемонстрировано в строку, которая выводит все эти значения.</span><span class="sxs-lookup"><span data-stu-id="eede1-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="eede1-124">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="eede1-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="eede1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="eede1-125">See also</span></span>

- [<span data-ttu-id="eede1-126">Члены</span><span class="sxs-lookup"><span data-stu-id="eede1-126">Members</span></span>](index.md)
- [<span data-ttu-id="eede1-127">Классы</span><span class="sxs-lookup"><span data-stu-id="eede1-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="eede1-128">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="eede1-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="eede1-129">Привязки `let` в классах</span><span class="sxs-lookup"><span data-stu-id="eede1-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="eede1-130">`do` Привязки</span><span class="sxs-lookup"><span data-stu-id="eede1-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
