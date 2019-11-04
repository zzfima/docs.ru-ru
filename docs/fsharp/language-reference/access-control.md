---
title: Управление доступом
description: Узнайте, как управлять доступом к программным элементам, таким как типы, методы и функции, на языке F# программирования.
ms.date: 05/16/2016
ms.openlocfilehash: fe204a883a440794fdd033c54d6d8d4fb68e0ce2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425115"
---
# <a name="access-control"></a><span data-ttu-id="40c5e-103">Управление доступом</span><span class="sxs-lookup"><span data-stu-id="40c5e-103">Access Control</span></span>

<span data-ttu-id="40c5e-104">*Контроль доступа* означает объявление того, какие клиенты могут использовать определенные элементы программы, такие как типы, методы и функции.</span><span class="sxs-lookup"><span data-stu-id="40c5e-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="40c5e-105">Основы управления доступом</span><span class="sxs-lookup"><span data-stu-id="40c5e-105">Basics of Access Control</span></span>

<span data-ttu-id="40c5e-106">В F#службах описатели управления доступом `public`, `internal`и `private` могут применяться к модулям, типам, методам, определениям значений, функциям, свойствам и явным полям.</span><span class="sxs-lookup"><span data-stu-id="40c5e-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="40c5e-107">`public` указывает, что доступ к сущности может осуществляться всеми вызывающими объектами.</span><span class="sxs-lookup"><span data-stu-id="40c5e-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="40c5e-108">`internal` указывает, что доступ к сущности можно получить только из той же сборки.</span><span class="sxs-lookup"><span data-stu-id="40c5e-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="40c5e-109">`private` указывает, что доступ к сущности можно получить только из включающего типа или модуля.</span><span class="sxs-lookup"><span data-stu-id="40c5e-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="40c5e-110">Спецификатор доступа `protected` не используется в F#, хотя он приемлем, если вы используете типы, созданные на языках, поддерживающих `protected` доступ.</span><span class="sxs-lookup"><span data-stu-id="40c5e-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="40c5e-111">Поэтому при переопределении защищенного метода метод остается доступным только внутри класса и его потомков.</span><span class="sxs-lookup"><span data-stu-id="40c5e-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="40c5e-112">В общем случае описатель помещается перед именем сущности, за исключением случаев, когда используется спецификатор `mutable` или `inline`, который появляется после описателя контроля доступа.</span><span class="sxs-lookup"><span data-stu-id="40c5e-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="40c5e-113">Если спецификатор доступа не используется, по умолчанию используется `public`, за исключением привязок `let` в типе, которые всегда `private` типу.</span><span class="sxs-lookup"><span data-stu-id="40c5e-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="40c5e-114">Сигнатуры F# в предоставляют еще один механизм управления доступом F# к программным элементам.</span><span class="sxs-lookup"><span data-stu-id="40c5e-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="40c5e-115">Для управления доступом подписи не требуются.</span><span class="sxs-lookup"><span data-stu-id="40c5e-115">Signatures are not required for access control.</span></span> <span data-ttu-id="40c5e-116">Дополнительные сведения см. в статье [Сигнатуры](signature-files.md).</span><span class="sxs-lookup"><span data-stu-id="40c5e-116">For more information, see [Signatures](signature-files.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="40c5e-117">Правила для контроля доступа</span><span class="sxs-lookup"><span data-stu-id="40c5e-117">Rules for Access Control</span></span>

<span data-ttu-id="40c5e-118">Управление доступом подчиняется следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="40c5e-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="40c5e-119">Объявления наследования (то есть использование `inherit` для указания базового класса для класса), объявления интерфейсов (т. е. Указание, что класс реализует интерфейс), а абстрактные элементы всегда имеют тот же уровень доступа, что и включающий тип.</span><span class="sxs-lookup"><span data-stu-id="40c5e-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="40c5e-120">Поэтому в этих конструкциях нельзя использовать описатель управления доступом.</span><span class="sxs-lookup"><span data-stu-id="40c5e-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="40c5e-121">Специальные возможности для отдельных вариантов в размеченного Union определяются уровнем доступности размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="40c5e-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="40c5e-122">То есть конкретный вариант объединения не менее доступен, чем сам союз.</span><span class="sxs-lookup"><span data-stu-id="40c5e-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="40c5e-123">Специальные возможности для отдельных полей типа записи определяются специальными возможностями записи.</span><span class="sxs-lookup"><span data-stu-id="40c5e-123">Accessibility for individual fields of a record type is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="40c5e-124">Это означает, что конкретная метка записи не менее доступна, чем сама запись.</span><span class="sxs-lookup"><span data-stu-id="40c5e-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="40c5e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="40c5e-125">Example</span></span>

<span data-ttu-id="40c5e-126">В следующем коде показано использование описателей управления доступом.</span><span class="sxs-lookup"><span data-stu-id="40c5e-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="40c5e-127">В проекте есть два файла: `Module1.fs` и `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="40c5e-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="40c5e-128">Каждый файл является неявным модулем.</span><span class="sxs-lookup"><span data-stu-id="40c5e-128">Each file is implicitly a module.</span></span> <span data-ttu-id="40c5e-129">Таким образом, существует два модуля: `Module1` и `Module2`.</span><span class="sxs-lookup"><span data-stu-id="40c5e-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="40c5e-130">Частный тип и внутренний тип определяются в `Module1`.</span><span class="sxs-lookup"><span data-stu-id="40c5e-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="40c5e-131">Доступ к закрытому типу из `Module2`невозможен, но внутренний тип может.</span><span class="sxs-lookup"><span data-stu-id="40c5e-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="40c5e-132">Следующий код проверяет доступность типов, созданных в `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="40c5e-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="40c5e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="40c5e-133">See also</span></span>

- [<span data-ttu-id="40c5e-134">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="40c5e-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="40c5e-135">Сигнатуры</span><span class="sxs-lookup"><span data-stu-id="40c5e-135">Signatures</span></span>](signature-files.md)
