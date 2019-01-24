---
title: Разработка полей
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: KrzysztofCwalina
ms.openlocfilehash: 3ab8fe279605c4795bb3a26557d0241b186b273a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690453"
---
# <a name="field-design"></a><span data-ttu-id="69c9d-102">Разработка полей</span><span class="sxs-lookup"><span data-stu-id="69c9d-102">Field Design</span></span>
<span data-ttu-id="69c9d-103">Принцип инкапсуляции является одним из наиболее важные понятия об удостоверении в объектно ориентированного проектирования.</span><span class="sxs-lookup"><span data-stu-id="69c9d-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="69c9d-104">Этот принцип утверждает, что данные, хранящиеся в объекте должен быть доступен только для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="69c9d-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="69c9d-105">Полезный способ интерпретации принцип — скажем, что тип должны разрабатываться таким образом, чтобы изменения поля этого типа (изменения имени или типу) могут выполняться без нарушения кода, отличное от для членов типа.</span><span class="sxs-lookup"><span data-stu-id="69c9d-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="69c9d-106">Эту интерпретацию немедленно подразумевает, что все поля должно быть закрытым.</span><span class="sxs-lookup"><span data-stu-id="69c9d-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="69c9d-107">Мы исключаем константы и статические поля только для чтения из этих ограничений strict, поскольку такие поля практически по определению, никогда не требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="69c9d-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="69c9d-108">**X DO NOT** предоставляют открытые или защищенные поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="69c9d-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="69c9d-109">Необходимо указать свойства для доступа к полям, вместо того, чтобы их открытый или защищенный.</span><span class="sxs-lookup"><span data-stu-id="69c9d-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="69c9d-110">**✓ DO** для констант, которые никогда не изменяются, используйте поля.</span><span class="sxs-lookup"><span data-stu-id="69c9d-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="69c9d-111">Компилятор горит значения const полей непосредственно в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="69c9d-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="69c9d-112">Таким образом значения const не может быть изменено без риска нарушения совместимости.</span><span class="sxs-lookup"><span data-stu-id="69c9d-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="69c9d-113">**✓ DO** использовать открытые статические `readonly` поля для предварительно определенных экземпляров объекта.</span><span class="sxs-lookup"><span data-stu-id="69c9d-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="69c9d-114">Если существуют предварительно определенные экземпляры типа, объявите их как открытые только для чтения статического поля самого типа.</span><span class="sxs-lookup"><span data-stu-id="69c9d-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="69c9d-115">**X DO NOT** назначить экземпляры изменяемых типов для `readonly` поля.</span><span class="sxs-lookup"><span data-stu-id="69c9d-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="69c9d-116">Изменяемый тип является типом с экземплярами, которые могут быть изменены после их создания.</span><span class="sxs-lookup"><span data-stu-id="69c9d-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="69c9d-117">Например, изменяемые типам относятся массивы, большинства коллекций и потоков, но <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, и <xref:System.String?displayProperty=nameWithType> все неизменяемы.</span><span class="sxs-lookup"><span data-stu-id="69c9d-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="69c9d-118">Модификатор "только для чтения" в поле типа ссылки не позволяет экземпляру, хранящиеся в поле замену, но не запрещает данных экземпляра поля изменяется путем вызова участников, изменение экземпляра.</span><span class="sxs-lookup"><span data-stu-id="69c9d-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="69c9d-119">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="69c9d-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="69c9d-120">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="69c9d-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c9d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="69c9d-121">See also</span></span>

- [<span data-ttu-id="69c9d-122">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="69c9d-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="69c9d-123">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="69c9d-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
