---
title: "Привязки let в классах (F#)"
description: "Дополнительные сведения о определять закрытые поля и закрытые функции для классов языка F # с помощью привязок «let» в определении класса."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9d3710f5-68b1-4e4c-b02b-27fe018f20e8
ms.openlocfilehash: 1337cc0794e366e8c39745f5c45065362c9c38c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="c2e1d-104">Привязки let в классах</span><span class="sxs-lookup"><span data-stu-id="c2e1d-104">let Bindings in Classes</span></span>

<span data-ttu-id="c2e1d-105">Закрытые поля и закрытые функции для классов языка F # можно определить с помощью `let` привязок в определении класса.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-105">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>


## <a name="syntax"></a><span data-ttu-id="c2e1d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2e1d-106">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="c2e1d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2e1d-107">Remarks</span></span>
<span data-ttu-id="c2e1d-108">Предыдущий синтаксис появляется после объявления заголовка и наследование классов, но до определения членов.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-108">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="c2e1d-109">Синтаксис аналогичен синтаксису `let` привязки вне классов, но имена, определенные в классе имеют область, являющуюся ограничена класса.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-109">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="c2e1d-110">Объект `let` привязки создает закрытое поле или функцию; для предоставления данных или функций публично, объявить свойство или метод члена.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-110">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="c2e1d-111">Объект `let` привязки, которая не является статическим называется экземпляр `let` привязки.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-111">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="c2e1d-112">Экземпляр `let` привязки выполняются при создании объектов.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-112">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="c2e1d-113">Статические `let` привязки являются частью статический инициализатор для класса, который гарантированно выполняется до первого использования типа.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-113">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="c2e1d-114">Код в пределах экземпляра `let` привязки можно использовать параметры первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-114">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="c2e1d-115">Атрибуты и модификаторы доступа не разрешены для `let` привязок в классах.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-115">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="c2e1d-116">Следующие примеры иллюстрируют типы `let` привязок в классах.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-116">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="c2e1d-117">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-117">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="c2e1d-118">Другие способы создания поля</span><span class="sxs-lookup"><span data-stu-id="c2e1d-118">Alternative Ways to Create Fields</span></span>
<span data-ttu-id="c2e1d-119">Можно также использовать `val` ключевое слово для создания закрытого поля.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-119">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="c2e1d-120">При использовании `val` ключевое слово, поле не имеет значение Если объект создается и инициализируется со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-120">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="c2e1d-121">Дополнительные сведения см. в разделе [явные поля: val ключевое слово](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="c2e1d-121">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="c2e1d-122">Закрытые поля можно также определять в классе с помощью определения члена с добавлением ключевого слова `private` к определению.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-122">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="c2e1d-123">Это может быть полезным, если вы собираетесь изменить доступность члена без изменения кода.</span><span class="sxs-lookup"><span data-stu-id="c2e1d-123">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="c2e1d-124">Дополнительные сведения см. в статье [Управление доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="c2e1d-124">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c2e1d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c2e1d-125">See Also</span></span>
[<span data-ttu-id="c2e1d-126">Члены</span><span class="sxs-lookup"><span data-stu-id="c2e1d-126">Members</span></span>](index.md)

[<span data-ttu-id="c2e1d-127">Привязки `do` в классах</span><span class="sxs-lookup"><span data-stu-id="c2e1d-127">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)

[<span data-ttu-id="c2e1d-128">`let`Привязки</span><span class="sxs-lookup"><span data-stu-id="c2e1d-128">`let` Bindings</span></span>](../functions/let-bindings.md)
