---
title: Привязки let в классах (F#)
description: 'Узнайте, как определять закрытые поля и закрытые функции для классов F # с помощью привязок «let» в определении класса.'
ms.date: 05/16/2016
ms.openlocfilehash: 237eb98a57571a21c9187abf31f05160374cf4fc
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "48033224"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="1f773-103">Привязки let в классах</span><span class="sxs-lookup"><span data-stu-id="1f773-103">let Bindings in Classes</span></span>

<span data-ttu-id="1f773-104">Закрытые поля и закрытые функции для классов F # можно определить с помощью `let` привязок в определении класса.</span><span class="sxs-lookup"><span data-stu-id="1f773-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="1f773-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f773-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="1f773-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f773-106">Remarks</span></span>

<span data-ttu-id="1f773-107">Предыдущий синтаксис появляется после объявления заголовка и наследование классов, но до определения членов.</span><span class="sxs-lookup"><span data-stu-id="1f773-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="1f773-108">Синтаксис аналогичен синтаксису `let` привязки за пределами классов, но имена, определенные в классе имеют область, которая ограничена класса.</span><span class="sxs-lookup"><span data-stu-id="1f773-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="1f773-109">Объект `let` привязки создает закрытое поле или функции; для предоставления данных или функции, объявления свойства или метода-члена.</span><span class="sxs-lookup"><span data-stu-id="1f773-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="1f773-110">Объект `let` привязка, которая не является статическим, вызывается экземпляр `let` привязки.</span><span class="sxs-lookup"><span data-stu-id="1f773-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="1f773-111">Экземпляр `let` привязки выполняются при создании объектов.</span><span class="sxs-lookup"><span data-stu-id="1f773-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="1f773-112">Статические `let` привязки являются частью статический инициализатор для класса, который гарантированно выполняется до первого использования типа.</span><span class="sxs-lookup"><span data-stu-id="1f773-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="1f773-113">Код в пределах экземпляра `let` привязки можно использовать параметры первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="1f773-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="1f773-114">Атрибуты и модификаторы доступа не разрешены для `let` привязок в классах.</span><span class="sxs-lookup"><span data-stu-id="1f773-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="1f773-115">В следующих примерах кода показаны несколько видов `let` привязок в классах.</span><span class="sxs-lookup"><span data-stu-id="1f773-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="1f773-116">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1f773-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="1f773-117">Другие способы создания поля</span><span class="sxs-lookup"><span data-stu-id="1f773-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="1f773-118">Можно также использовать `val` ключевое слово, чтобы создать частное поле.</span><span class="sxs-lookup"><span data-stu-id="1f773-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="1f773-119">При использовании `val` ключевое слово, поле не имеет значения при создании объекта, но инициализируется со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1f773-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="1f773-120">Дополнительные сведения см. в разделе [явные поля: val ключевое слово](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="1f773-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="1f773-121">Закрытые поля можно также определять в классе с помощью определения члена и добавив ключевое слово `private` к определению.</span><span class="sxs-lookup"><span data-stu-id="1f773-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="1f773-122">Это может быть полезно в том случае, если вы собираетесь изменить доступность члена без изменения кода.</span><span class="sxs-lookup"><span data-stu-id="1f773-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="1f773-123">Дополнительные сведения см. в статье [Управление доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="1f773-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1f773-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1f773-124">See also</span></span>

- [<span data-ttu-id="1f773-125">Члены</span><span class="sxs-lookup"><span data-stu-id="1f773-125">Members</span></span>](index.md)
- [<span data-ttu-id="1f773-126">Привязки `do` в классах</span><span class="sxs-lookup"><span data-stu-id="1f773-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="1f773-127">`let` Привязки</span><span class="sxs-lookup"><span data-stu-id="1f773-127">`let` Bindings</span></span>](../functions/let-bindings.md)
