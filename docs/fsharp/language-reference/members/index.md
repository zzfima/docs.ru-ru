---
title: Члены (F#)
description: 'Дополнительные сведения о элементы объекта в языке F #.'
keywords: visual f#, f#, функциональное программирование
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e472f50a-4939-4e62-abbc-471f8f265790
ms.openlocfilehash: ca34c8d073594791ec268a85ad56f50cc6d9e435
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="members"></a><span data-ttu-id="07c8e-104">Члены</span><span class="sxs-lookup"><span data-stu-id="07c8e-104">Members</span></span>

<span data-ttu-id="07c8e-105">Эта статья описывает элементы типов объектов F#.</span><span class="sxs-lookup"><span data-stu-id="07c8e-105">This section describes members of F# object types.</span></span>


## <a name="remarks"></a><span data-ttu-id="07c8e-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="07c8e-106">Remarks</span></span>
<span data-ttu-id="07c8e-107">*Элементы* являются компонентами, которые входят в состав определения типа и объявляются с помощью ключевого слова `member`.</span><span class="sxs-lookup"><span data-stu-id="07c8e-107">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="07c8e-108">Типы объектов F#, такие как записи, классы, размеченные объединения, интерфейсы и структуры, поддерживают элементы.</span><span class="sxs-lookup"><span data-stu-id="07c8e-108">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="07c8e-109">Дополнительные сведения см. в статьях [Записи](../records.md), [Классы](../classes.md), [Размеченные объединения](../discriminated-Unions.md), [Интерфейсы](../interfaces.md) и [Структуры](../structures.md).</span><span class="sxs-lookup"><span data-stu-id="07c8e-109">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="07c8e-110">Обычно элементы составляют открытый интерфейс для типа, поэтому они считаются открытыми, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="07c8e-110">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="07c8e-111">Элементы также можно объявлять как закрытые или внутренние.</span><span class="sxs-lookup"><span data-stu-id="07c8e-111">Members can also be declared private or internal.</span></span> <span data-ttu-id="07c8e-112">Дополнительные сведения см. в статье [Управление доступом](../access-Control.md).</span><span class="sxs-lookup"><span data-stu-id="07c8e-112">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="07c8e-113">Сигнатуры для типов также можно использовать, чтобы предоставлять или не предоставлять определенные элементы типа.</span><span class="sxs-lookup"><span data-stu-id="07c8e-113">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="07c8e-114">Дополнительные сведения см. в статье [Сигнатуры](../signatures.md).</span><span class="sxs-lookup"><span data-stu-id="07c8e-114">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="07c8e-115">Частные поля и привязки `do`, которые используются только с классами, не являются подлинными элементами, так как они никогда входят в состав открытого интерфейса типа и не объявляются с помощью ключевого слова `member`, но они также описаны в этой статье.</span><span class="sxs-lookup"><span data-stu-id="07c8e-115">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>


## <a name="related-topics"></a><span data-ttu-id="07c8e-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="07c8e-116">Related Topics</span></span>


|<span data-ttu-id="07c8e-117">Раздел</span><span class="sxs-lookup"><span data-stu-id="07c8e-117">Topic</span></span>|<span data-ttu-id="07c8e-118">Описание</span><span class="sxs-lookup"><span data-stu-id="07c8e-118">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="07c8e-119">Привязки `let` в классах</span><span class="sxs-lookup"><span data-stu-id="07c8e-119">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)|<span data-ttu-id="07c8e-120">Описывает определение частных полей и функций в классах.</span><span class="sxs-lookup"><span data-stu-id="07c8e-120">Describes the definition of private fields and functions in classes.</span></span>|
|[<span data-ttu-id="07c8e-121">Привязки `do` в классах</span><span class="sxs-lookup"><span data-stu-id="07c8e-121">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)|<span data-ttu-id="07c8e-122">Описывает указание кода инициализации объекта.</span><span class="sxs-lookup"><span data-stu-id="07c8e-122">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="07c8e-123">Свойства</span><span class="sxs-lookup"><span data-stu-id="07c8e-123">Properties</span></span>](properties.md)|<span data-ttu-id="07c8e-124">Описывает элементы свойств в классах и других типах.</span><span class="sxs-lookup"><span data-stu-id="07c8e-124">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="07c8e-125">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="07c8e-125">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="07c8e-126">Описывает массивоподобные свойства в классах и других типах.</span><span class="sxs-lookup"><span data-stu-id="07c8e-126">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="07c8e-127">Методы</span><span class="sxs-lookup"><span data-stu-id="07c8e-127">Methods</span></span>](methods.md)|<span data-ttu-id="07c8e-128">Описывает функции, являющиеся элементами типа.</span><span class="sxs-lookup"><span data-stu-id="07c8e-128">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="07c8e-129">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="07c8e-129">Constructors</span></span>](constructors.md)|<span data-ttu-id="07c8e-130">Описывает специальные функции, инициализирующие объекты типа.</span><span class="sxs-lookup"><span data-stu-id="07c8e-130">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="07c8e-131">Перегрузка операторов</span><span class="sxs-lookup"><span data-stu-id="07c8e-131">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="07c8e-132">Описывает определение настраиваемых операторов для типов.</span><span class="sxs-lookup"><span data-stu-id="07c8e-132">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="07c8e-133">События</span><span class="sxs-lookup"><span data-stu-id="07c8e-133">Events</span></span>](events.md)|<span data-ttu-id="07c8e-134">Описывается определение событий и поддержку обработки событий в F#.</span><span class="sxs-lookup"><span data-stu-id="07c8e-134">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="07c8e-135">Явные поля. Ключевое слово`val`</span><span class="sxs-lookup"><span data-stu-id="07c8e-135">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="07c8e-136">Описывает определение неинициализированных полей в типе.</span><span class="sxs-lookup"><span data-stu-id="07c8e-136">Describes the definition of uninitialized fields in a type.</span></span>|
