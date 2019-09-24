---
title: Привязки let в классах
description: Узнайте, как определить закрытые поля и закрытые F# функции для классов с помощью привязок let в определении класса.
ms.date: 05/16/2016
ms.openlocfilehash: 1366ab8f1f4f606fe5947a8fc4df10de49346b3e
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216528"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="63713-103">Привязки let в классах</span><span class="sxs-lookup"><span data-stu-id="63713-103">let Bindings in Classes</span></span>

<span data-ttu-id="63713-104">Закрытые поля и закрытые функции для F# классов можно определить с `let` помощью привязок в определении класса.</span><span class="sxs-lookup"><span data-stu-id="63713-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="63713-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63713-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="63713-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="63713-106">Remarks</span></span>

<span data-ttu-id="63713-107">Предыдущий синтаксис отображается после объявления класса и объявлений наследования, но перед определениями элементов.</span><span class="sxs-lookup"><span data-stu-id="63713-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="63713-108">Синтаксис выглядит так же, `let` как в привязках за пределами классов, но имена, определенные в классе, имеют область, ограниченную классом.</span><span class="sxs-lookup"><span data-stu-id="63713-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="63713-109">`let` Привязка создает закрытое поле или функцию; чтобы предоставить доступ к данным или функциям, объявите свойство или метод члена.</span><span class="sxs-lookup"><span data-stu-id="63713-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="63713-110">Привязка, которая не является статической, называется привязкой `let`экземпляра. `let`</span><span class="sxs-lookup"><span data-stu-id="63713-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="63713-111">Привязки `let` экземпляров выполняются при создании объектов.</span><span class="sxs-lookup"><span data-stu-id="63713-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="63713-112">Статические `let` привязки являются частью статического инициализатора класса, который гарантированно выполняется перед первым использованием типа.</span><span class="sxs-lookup"><span data-stu-id="63713-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="63713-113">Код в привязках `let` экземпляров может использовать параметры первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="63713-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="63713-114">Атрибуты и модификаторы доступности не разрешены в `let` привязках в классах.</span><span class="sxs-lookup"><span data-stu-id="63713-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="63713-115">В следующих примерах кода показано несколько типов `let` привязок в классах.</span><span class="sxs-lookup"><span data-stu-id="63713-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="63713-116">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="63713-116">The output is as follows.</span></span>

```console
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="63713-117">Альтернативные способы создания полей</span><span class="sxs-lookup"><span data-stu-id="63713-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="63713-118">Для создания закрытого поля `val` также можно использовать ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="63713-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="63713-119">При использовании `val` ключевого слова поле не получает значение при создании объекта, а инициализируется со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="63713-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="63713-120">Дополнительные сведения см. в [разделе явные поля: Ключевое слово](explicit-fields-the-val-keyword.md)Val.</span><span class="sxs-lookup"><span data-stu-id="63713-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="63713-121">Можно также определить закрытые поля в классе, используя определение элемента и добавив ключевое слово `private` в определение.</span><span class="sxs-lookup"><span data-stu-id="63713-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="63713-122">Это может быть полезно, если вы планируете изменить доступность члена, не переписывая код.</span><span class="sxs-lookup"><span data-stu-id="63713-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="63713-123">Дополнительные сведения см. в статье [Управление доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="63713-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="63713-124">См. также</span><span class="sxs-lookup"><span data-stu-id="63713-124">See also</span></span>

- [<span data-ttu-id="63713-125">Члены</span><span class="sxs-lookup"><span data-stu-id="63713-125">Members</span></span>](index.md)
- [<span data-ttu-id="63713-126">Привязки `do` в классах</span><span class="sxs-lookup"><span data-stu-id="63713-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="63713-127">`let`Привязки</span><span class="sxs-lookup"><span data-stu-id="63713-127">`let` Bindings</span></span>](../functions/let-bindings.md)
