---
title: Разработка полей
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: d39c9b95d759902d6d523b028f3db8b8da954336
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709352"
---
# <a name="field-design"></a><span data-ttu-id="3e095-102">Разработка полей</span><span class="sxs-lookup"><span data-stu-id="3e095-102">Field Design</span></span>
<span data-ttu-id="3e095-103">Принцип инкапсуляции является одним из наиболее важных концепций объектно-ориентированного проектирования.</span><span class="sxs-lookup"><span data-stu-id="3e095-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="3e095-104">Этот принцип указывает, что данные, хранящиеся внутри объекта, должны быть доступны только для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="3e095-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="3e095-105">Чтобы интерпретировать принцип, можно сказать, что тип должен быть спроектирован таким образом, чтобы изменения полей этого типа (изменения имени или типа) могли выполняться без нарушения кода, отличного от элементов типа.</span><span class="sxs-lookup"><span data-stu-id="3e095-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="3e095-106">Такая интерпретация немедленно подразумевает, что все поля должны быть частными.</span><span class="sxs-lookup"><span data-stu-id="3e095-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="3e095-107">Мы исключены постоянные и статические поля только для чтения из этого ограниченного ограничения, так как такие поля почти по определению не требуют изменения.</span><span class="sxs-lookup"><span data-stu-id="3e095-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="3e095-108">**X DO NOT** предоставляют открытые или защищенные поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3e095-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="3e095-109">Необходимо предоставить свойства для доступа к полям, не делая их открытыми или защищенными.</span><span class="sxs-lookup"><span data-stu-id="3e095-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="3e095-110">**✓ DO** для констант, которые никогда не изменяются, используйте поля.</span><span class="sxs-lookup"><span data-stu-id="3e095-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="3e095-111">Компилятор записывает значения полей const непосредственно в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="3e095-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="3e095-112">Поэтому константные значения не могут быть изменены без риска нарушения совместимости.</span><span class="sxs-lookup"><span data-stu-id="3e095-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="3e095-113">**✓ DO** использовать открытые статические `readonly` поля для предварительно определенных экземпляров объекта.</span><span class="sxs-lookup"><span data-stu-id="3e095-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="3e095-114">Если имеются предопределенные экземпляры типа, объявите их как открытые статические поля только для чтения самого типа.</span><span class="sxs-lookup"><span data-stu-id="3e095-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="3e095-115">**X DO NOT** назначить экземпляры изменяемых типов для `readonly` поля.</span><span class="sxs-lookup"><span data-stu-id="3e095-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="3e095-116">Изменяемый тип — это тип с экземплярами, которые могут быть изменены после создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3e095-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="3e095-117">Например, массивы, большинство коллекций и потоков являются изменяемыми типами, но <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>и <xref:System.String?displayProperty=nameWithType> являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="3e095-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="3e095-118">Модификатор только для чтения в поле ссылочный тип предотвращает замену экземпляра, хранящегося в поле, но не предотвращает изменение данных экземпляра поля путем вызова членов, изменяющих экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3e095-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="3e095-119">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="3e095-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3e095-120">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="3e095-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e095-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e095-121">See also</span></span>

- [<span data-ttu-id="3e095-122">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="3e095-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="3e095-123">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="3e095-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
