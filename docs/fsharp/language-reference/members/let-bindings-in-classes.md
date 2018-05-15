---
title: Привязки let в классах (F#)
description: 'Дополнительные сведения о определять закрытые поля и закрытые функции для классов языка F # с помощью привязок «let» в определении класса.'
ms.date: 05/16/2016
ms.openlocfilehash: 1c17fe0edec14c28c9bdde86d0a2acb7c886cdf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="030da-103">Привязки let в классах</span><span class="sxs-lookup"><span data-stu-id="030da-103">let Bindings in Classes</span></span>

<span data-ttu-id="030da-104">Закрытые поля и закрытые функции для классов языка F # можно определить с помощью `let` привязок в определении класса.</span><span class="sxs-lookup"><span data-stu-id="030da-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>


## <a name="syntax"></a><span data-ttu-id="030da-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="030da-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="030da-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="030da-106">Remarks</span></span>
<span data-ttu-id="030da-107">Предыдущий синтаксис появляется после объявления заголовка и наследование классов, но до определения членов.</span><span class="sxs-lookup"><span data-stu-id="030da-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="030da-108">Синтаксис аналогичен синтаксису `let` привязки вне классов, но имена, определенные в классе имеют область, являющуюся ограничена класса.</span><span class="sxs-lookup"><span data-stu-id="030da-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="030da-109">Объект `let` привязки создает закрытое поле или функцию; для предоставления данных или функций публично, объявить свойство или метод члена.</span><span class="sxs-lookup"><span data-stu-id="030da-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="030da-110">Объект `let` привязки, которая не является статическим называется экземпляр `let` привязки.</span><span class="sxs-lookup"><span data-stu-id="030da-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="030da-111">Экземпляр `let` привязки выполняются при создании объектов.</span><span class="sxs-lookup"><span data-stu-id="030da-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="030da-112">Статические `let` привязки являются частью статический инициализатор для класса, который гарантированно выполняется до первого использования типа.</span><span class="sxs-lookup"><span data-stu-id="030da-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="030da-113">Код в пределах экземпляра `let` привязки можно использовать параметры первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="030da-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="030da-114">Атрибуты и модификаторы доступа не разрешены для `let` привязок в классах.</span><span class="sxs-lookup"><span data-stu-id="030da-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="030da-115">Следующие примеры иллюстрируют типы `let` привязок в классах.</span><span class="sxs-lookup"><span data-stu-id="030da-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="030da-116">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="030da-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="030da-117">Другие способы создания поля</span><span class="sxs-lookup"><span data-stu-id="030da-117">Alternative Ways to Create Fields</span></span>
<span data-ttu-id="030da-118">Можно также использовать `val` ключевое слово для создания закрытого поля.</span><span class="sxs-lookup"><span data-stu-id="030da-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="030da-119">При использовании `val` ключевое слово, поле не имеет значение Если объект создается и инициализируется со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="030da-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="030da-120">Дополнительные сведения см. в разделе [явные поля: val ключевое слово](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="030da-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="030da-121">Закрытые поля можно также определять в классе с помощью определения члена с добавлением ключевого слова `private` к определению.</span><span class="sxs-lookup"><span data-stu-id="030da-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="030da-122">Это может быть полезным, если вы собираетесь изменить доступность члена без изменения кода.</span><span class="sxs-lookup"><span data-stu-id="030da-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="030da-123">Дополнительные сведения см. в статье [Управление доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="030da-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="030da-124">См. также</span><span class="sxs-lookup"><span data-stu-id="030da-124">See Also</span></span>
[<span data-ttu-id="030da-125">Члены</span><span class="sxs-lookup"><span data-stu-id="030da-125">Members</span></span>](index.md)

[<span data-ttu-id="030da-126">Привязки `do` в классах</span><span class="sxs-lookup"><span data-stu-id="030da-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)

[<span data-ttu-id="030da-127">`let` Привязки</span><span class="sxs-lookup"><span data-stu-id="030da-127">`let` Bindings</span></span>](../functions/let-bindings.md)
