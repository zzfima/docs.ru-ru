---
title: Разработка структур
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: b6d06bc8a1e8535f1452af0726138abaebfd4951
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743611"
---
# <a name="struct-design"></a><span data-ttu-id="da685-102">Разработка структур</span><span class="sxs-lookup"><span data-stu-id="da685-102">Struct Design</span></span>
<span data-ttu-id="da685-103">Тип значения общего назначения чаще всего называется структурой и C# ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="da685-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="da685-104">В этом разделе приводятся рекомендации по проектированию общих структур.</span><span class="sxs-lookup"><span data-stu-id="da685-104">This section provides guidelines for general struct design.</span></span>

 <span data-ttu-id="da685-105">❌ не предоставляют конструктор без параметров для структуры.</span><span class="sxs-lookup"><span data-stu-id="da685-105">❌ DO NOT provide a parameterless constructor for a struct.</span></span>

 <span data-ttu-id="da685-106">После этого правила можно создавать массивы структур без необходимости запуска конструктора для каждого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="da685-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="da685-107">Обратите C# внимание, что не разрешает структурам использовать конструкторы без параметров.</span><span class="sxs-lookup"><span data-stu-id="da685-107">Notice that C# does not allow structs to have parameterless constructors.</span></span>

 <span data-ttu-id="da685-108">❌ не определяют изменяемые типы значений.</span><span class="sxs-lookup"><span data-stu-id="da685-108">❌ DO NOT define mutable value types.</span></span>

 <span data-ttu-id="da685-109">У изменяемых типов значений есть несколько проблем.</span><span class="sxs-lookup"><span data-stu-id="da685-109">Mutable value types have several problems.</span></span> <span data-ttu-id="da685-110">Например, когда метод считывания свойства возвращает тип значения, вызывающий объект получает копию.</span><span class="sxs-lookup"><span data-stu-id="da685-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="da685-111">Поскольку копия создается неявным образом, разработчики могут не знать, что они изменяют копию, а не исходное значение.</span><span class="sxs-lookup"><span data-stu-id="da685-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="da685-112">Кроме того, некоторые языки (динамические языки, в частности) имеют проблемы с использованием изменяемых типов значений, так как даже локальные переменные при разыменовании приводят к созданию копии.</span><span class="sxs-lookup"><span data-stu-id="da685-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>

 <span data-ttu-id="da685-113">✔️ обеспечить допустимость состояния, в котором все данные экземпляра имеют нулевое значение, false или null (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="da685-113">✔️ DO ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>

 <span data-ttu-id="da685-114">Это предотвращает случайное создание недопустимых экземпляров при создании массива структур.</span><span class="sxs-lookup"><span data-stu-id="da685-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>

 <span data-ttu-id="da685-115">✔️ реализовать <xref:System.IEquatable%601> для типов значений.</span><span class="sxs-lookup"><span data-stu-id="da685-115">✔️ DO implement <xref:System.IEquatable%601> on value types.</span></span>

 <span data-ttu-id="da685-116">Метод <xref:System.Object.Equals%2A?displayProperty=nameWithType> для типов значений приводит к тому, что упаковка и реализация по умолчанию не очень эффективны, поскольку в ней используется отражение.</span><span class="sxs-lookup"><span data-stu-id="da685-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="da685-117"><xref:System.IEquatable%601.Equals%2A> могут иметь гораздо более высокую производительность и могут быть реализованы таким образом, чтобы не вызывать упаковку-преобразование.</span><span class="sxs-lookup"><span data-stu-id="da685-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>

 <span data-ttu-id="da685-118">❌ не следует явно расширять <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="da685-118">❌ DO NOT explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="da685-119">На самом деле, большинство языков препятствуют этому.</span><span class="sxs-lookup"><span data-stu-id="da685-119">In fact, most languages prevent this.</span></span>

 <span data-ttu-id="da685-120">Как правило, структуры могут быть очень полезными, но их следует использовать только для небольших, однострочных неизменяемых значений, которые не будут часто выдаваться в штучной упаковке.</span><span class="sxs-lookup"><span data-stu-id="da685-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>

 <span data-ttu-id="da685-121">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="da685-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="da685-122">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="da685-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="da685-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="da685-123">See also</span></span>

- [<span data-ttu-id="da685-124">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="da685-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="da685-125">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="da685-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="da685-126">Выбор между классом и структурой</span><span class="sxs-lookup"><span data-stu-id="da685-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
