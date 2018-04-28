---
title: Управление доступом (F#)
description: 'Узнайте, как для управления доступом к элементов программирования, таких как типы, методы и функции в языке F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: fee5f719904b61c3082d56f73448defdea39f472
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="access-control"></a><span data-ttu-id="bced8-103">Управление доступом</span><span class="sxs-lookup"><span data-stu-id="bced8-103">Access Control</span></span>

<span data-ttu-id="bced8-104">*Контроль доступа* понимается объявление того, какие клиенты могут использовать определенные элементы программы, например типы, методы и функции.</span><span class="sxs-lookup"><span data-stu-id="bced8-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="bced8-105">Основы управления доступом</span><span class="sxs-lookup"><span data-stu-id="bced8-105">Basics of Access Control</span></span>
<span data-ttu-id="bced8-106">В языке F # описатели управления доступом `public`, `internal`, и `private` может применяться к модули, типы, методы, определений значений, функций, свойств и явные поля.</span><span class="sxs-lookup"><span data-stu-id="bced8-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="bced8-107">`public` Указывает, что сущность может осуществляться все вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="bced8-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="bced8-108">`internal` Указывает, что сущность может осуществляться только из той же сборки.</span><span class="sxs-lookup"><span data-stu-id="bced8-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="bced8-109">`private` Указывает, что сущность может осуществляться только из включающего ее типа или модуля.</span><span class="sxs-lookup"><span data-stu-id="bced8-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="bced8-110">Спецификатор доступа `protected` не используется в F #, хотя это приемлемо, если при использовании типов, созданных на языках, которые поддерживают `protected` доступа.</span><span class="sxs-lookup"><span data-stu-id="bced8-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="bced8-111">Таким образом Если переопределить защищенный метод, этот метод будет доступен только в пределах класса и его потомков.</span><span class="sxs-lookup"><span data-stu-id="bced8-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="bced8-112">Как правило, описатель размещается перед именем сущности, за исключением случаев `mutable` или `inline` используется спецификатор, которые записываются после описателя управления доступом.</span><span class="sxs-lookup"><span data-stu-id="bced8-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="bced8-113">Если используется спецификатор доступа, значение по умолчанию — `public`, за исключением `let` привязок в типе, которые всегда являются `private` типу.</span><span class="sxs-lookup"><span data-stu-id="bced8-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="bced8-114">Подписи в F # предоставляют еще один механизм для управления доступом к элементам программы на F #.</span><span class="sxs-lookup"><span data-stu-id="bced8-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="bced8-115">Подписи не являются обязательными для управления доступом.</span><span class="sxs-lookup"><span data-stu-id="bced8-115">Signatures are not required for access control.</span></span> <span data-ttu-id="bced8-116">Дополнительные сведения см. в статье [Сигнатуры](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="bced8-116">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="bced8-117">Правила управления доступом</span><span class="sxs-lookup"><span data-stu-id="bced8-117">Rules for Access Control</span></span>
<span data-ttu-id="bced8-118">Управление доступом — это применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="bced8-118">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="bced8-119">Объявления наследования (то есть, использование `inherit` для указания базового класса для класса), объявления интерфейсов (Указание того, что класс реализует интерфейс) и абстрактные члены всегда имеют тот же уровень доступа, включающего их типа.</span><span class="sxs-lookup"><span data-stu-id="bced8-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="bced8-120">Таким образом спецификатора контроля доступа не может использоваться на этих конструкций.</span><span class="sxs-lookup"><span data-stu-id="bced8-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="bced8-121">Отдельные варианты в размеченного объединения не может иметь собственные модификаторы управления доступом, отдельно от типа объединения.</span><span class="sxs-lookup"><span data-stu-id="bced8-121">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="bced8-122">Отдельные поля типа записи не может иметь свои собственные модификаторы управления доступом, отдельные от типа записи.</span><span class="sxs-lookup"><span data-stu-id="bced8-122">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="bced8-123">Пример</span><span class="sxs-lookup"><span data-stu-id="bced8-123">Example</span></span>
<span data-ttu-id="bced8-124">Следующий код иллюстрирует использование описателей управления доступом.</span><span class="sxs-lookup"><span data-stu-id="bced8-124">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="bced8-125">Существуют два файла в проекте `Module1.fs` и `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="bced8-125">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="bced8-126">Каждый файл неявно представляет собой модуль.</span><span class="sxs-lookup"><span data-stu-id="bced8-126">Each file is implicitly a module.</span></span> <span data-ttu-id="bced8-127">Таким образом, есть два модуля `Module1` и `Module2`.</span><span class="sxs-lookup"><span data-stu-id="bced8-127">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="bced8-128">Закрытый тип и внутренний тип определяются в `Module1`.</span><span class="sxs-lookup"><span data-stu-id="bced8-128">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="bced8-129">Закрытый тип нельзя получить доступ из `Module2`, но внутреннему типу.</span><span class="sxs-lookup"><span data-stu-id="bced8-129">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="bced8-130">Следующий код проверяет доступность типов, созданных в `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="bced8-130">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="bced8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="bced8-131">See Also</span></span>
[<span data-ttu-id="bced8-132">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="bced8-132">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="bced8-133">Сигнатуры</span><span class="sxs-lookup"><span data-stu-id="bced8-133">Signatures</span></span>](signatures.md)
