---
title: Управление доступом
description: Узнайте, как управлять доступом к программным элементам, таким как типы, методы и функции, на языке F# программирования.
ms.date: 05/16/2016
ms.openlocfilehash: ed77a09cf87aabf9a4134276e89e84aa42abd3c3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629969"
---
# <a name="access-control"></a><span data-ttu-id="36225-103">Управление доступом</span><span class="sxs-lookup"><span data-stu-id="36225-103">Access Control</span></span>

<span data-ttu-id="36225-104">*Контроль доступа* означает объявление того, какие клиенты могут использовать определенные элементы программы, такие как типы, методы и функции.</span><span class="sxs-lookup"><span data-stu-id="36225-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="36225-105">Основы управления доступом</span><span class="sxs-lookup"><span data-stu-id="36225-105">Basics of Access Control</span></span>

<span data-ttu-id="36225-106">В F#службах описатели `public`управления доступом, `internal`и `private` могут применяться к модулям, типам, методам, определениям значений, функциям, свойствам и явным полям.</span><span class="sxs-lookup"><span data-stu-id="36225-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="36225-107">`public`Указывает, что доступ к сущности может осуществляться всеми вызывающими объектами.</span><span class="sxs-lookup"><span data-stu-id="36225-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="36225-108">`internal`Указывает, что доступ к сущности можно получить только из той же сборки.</span><span class="sxs-lookup"><span data-stu-id="36225-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="36225-109">`private`Указывает, что доступ к сущности можно получить только из включающего типа или модуля.</span><span class="sxs-lookup"><span data-stu-id="36225-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="36225-110">Спецификатор `protected` доступа не используется в F#, хотя он допустим при использовании типов, созданных на языках, поддерживающих `protected` доступ.</span><span class="sxs-lookup"><span data-stu-id="36225-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="36225-111">Поэтому при переопределении защищенного метода метод остается доступным только внутри класса и его потомков.</span><span class="sxs-lookup"><span data-stu-id="36225-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="36225-112">В общем случае описатель помещается перед именем сущности, за исключением случаев, когда `mutable` используется описатель или `inline` , который появляется после описателя управления доступом.</span><span class="sxs-lookup"><span data-stu-id="36225-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="36225-113">Если спецификатор доступа не используется, по умолчанию используется `public`значение, `let` за исключением привязок в типе, которые всегда `private` имеют тип.</span><span class="sxs-lookup"><span data-stu-id="36225-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="36225-114">Сигнатуры F# в предоставляют еще один механизм управления доступом F# к программным элементам.</span><span class="sxs-lookup"><span data-stu-id="36225-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="36225-115">Для управления доступом подписи не требуются.</span><span class="sxs-lookup"><span data-stu-id="36225-115">Signatures are not required for access control.</span></span> <span data-ttu-id="36225-116">Дополнительные сведения см. в статье [Сигнатуры](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="36225-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="36225-117">Правила для контроля доступа</span><span class="sxs-lookup"><span data-stu-id="36225-117">Rules for Access Control</span></span>

<span data-ttu-id="36225-118">Управление доступом подчиняется следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="36225-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="36225-119">Объявления наследования (то есть использование `inherit` для указания базового класса для класса), объявления интерфейсов (т. е. Указание, что класс реализует интерфейс), а абстрактные элементы всегда имеют тот же уровень доступности, что и включающий тип.</span><span class="sxs-lookup"><span data-stu-id="36225-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="36225-120">Поэтому в этих конструкциях нельзя использовать описатель управления доступом.</span><span class="sxs-lookup"><span data-stu-id="36225-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="36225-121">Специальные возможности для отдельных вариантов в размеченного Union определяются уровнем доступности размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="36225-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="36225-122">То есть конкретный вариант объединения не менее доступен, чем сам союз.</span><span class="sxs-lookup"><span data-stu-id="36225-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="36225-123">Специальные возможности для отдельных полей типа записи не могут определяться специальными возможностями записи.</span><span class="sxs-lookup"><span data-stu-id="36225-123">Accessibility for individual fields of a record type cannot is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="36225-124">Это означает, что конкретная метка записи не менее доступна, чем сама запись.</span><span class="sxs-lookup"><span data-stu-id="36225-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="36225-125">Пример</span><span class="sxs-lookup"><span data-stu-id="36225-125">Example</span></span>

<span data-ttu-id="36225-126">В следующем коде показано использование описателей управления доступом.</span><span class="sxs-lookup"><span data-stu-id="36225-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="36225-127">В проекте `Module1.fs` есть два файла: и `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="36225-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="36225-128">Каждый файл является неявным модулем.</span><span class="sxs-lookup"><span data-stu-id="36225-128">Each file is implicitly a module.</span></span> <span data-ttu-id="36225-129">Таким образом, существует два модуля `Module1` : и. `Module2`</span><span class="sxs-lookup"><span data-stu-id="36225-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="36225-130">Частный тип и внутренний тип определяются в `Module1`.</span><span class="sxs-lookup"><span data-stu-id="36225-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="36225-131">Доступ к закрытому типу невозможен из `Module2`, но внутренний тип может.</span><span class="sxs-lookup"><span data-stu-id="36225-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="36225-132">Следующий код проверяет доступность типов, созданных в `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="36225-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="36225-133">См. также</span><span class="sxs-lookup"><span data-stu-id="36225-133">See also</span></span>

- [<span data-ttu-id="36225-134">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="36225-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="36225-135">Сигнатуры</span><span class="sxs-lookup"><span data-stu-id="36225-135">Signatures</span></span>](signatures.md)
