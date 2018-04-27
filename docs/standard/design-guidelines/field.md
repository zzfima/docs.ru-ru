---
title: Разработка полей
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 102c52a125c3f34dc027d01eecd24f13613e20c6
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="field-design"></a><span data-ttu-id="938db-102">Разработка полей</span><span class="sxs-lookup"><span data-stu-id="938db-102">Field Design</span></span>
<span data-ttu-id="938db-103">Принцип инкапсуляции является одним из наиболее важные понятия в объектно ориентированный проект.</span><span class="sxs-lookup"><span data-stu-id="938db-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="938db-104">Этот принцип состояний, что данные, хранящиеся в объекте должен быть доступен только для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="938db-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="938db-105">Можно сказать, что тип должны разрабатываться таким образом изменения значения этого типа (изменения имени или типа) может быть без нарушения кода, отличных от для элементов типа — удобный способ интерпретации принцип.</span><span class="sxs-lookup"><span data-stu-id="938db-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="938db-106">Эту интерпретацию немедленно подразумевает все поля должны быть закрытым.</span><span class="sxs-lookup"><span data-stu-id="938db-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="938db-107">Мы исключить константы и статические поля только для чтения из этих ограничений strict, поскольку такие поля практически по определению, никогда не требуются для изменения.</span><span class="sxs-lookup"><span data-stu-id="938db-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="938db-108">**X не** предоставляют открытые или защищенные поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="938db-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="938db-109">Для доступа к полям вместо внесения их в открытый или защищенный следует предоставить свойства.</span><span class="sxs-lookup"><span data-stu-id="938db-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="938db-110">**✓ ВЫПОЛНИТЕ** для констант, которые никогда не изменяются, используйте поля.</span><span class="sxs-lookup"><span data-stu-id="938db-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="938db-111">Компилятор горит значения таких полей непосредственно в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="938db-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="938db-112">Таким образом значения-константы не может быть изменено без риска нарушения совместимости.</span><span class="sxs-lookup"><span data-stu-id="938db-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="938db-113">**СДЕЛАТЬ ✓** использовать открытые статические `readonly` поля для предварительно определенных экземпляров объекта.</span><span class="sxs-lookup"><span data-stu-id="938db-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="938db-114">Если существуют предварительно определенные экземпляры типа, объявите их как открытые только для чтения статического поля самого типа.</span><span class="sxs-lookup"><span data-stu-id="938db-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="938db-115">**X не** назначить экземпляры изменяемых типов для `readonly` поля.</span><span class="sxs-lookup"><span data-stu-id="938db-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="938db-116">Изменяемый тип — это тип с экземплярами, которые могут быть изменены после их создания.</span><span class="sxs-lookup"><span data-stu-id="938db-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="938db-117">Массивы, большинства коллекций и потоки, изменяемых типов, но <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, и <xref:System.String?displayProperty=nameWithType> все неизменяемы.</span><span class="sxs-lookup"><span data-stu-id="938db-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="938db-118">Модификатор "только для чтения" в поле типа ссылки предотвращает экземпляра, содержащегося в поле замену, но не запрещает данных экземпляра поля изменяется путем вызова участников изменение экземпляра.</span><span class="sxs-lookup"><span data-stu-id="938db-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="938db-119">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="938db-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="938db-120">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="938db-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938db-121">См. также</span><span class="sxs-lookup"><span data-stu-id="938db-121">See Also</span></span>  
 [<span data-ttu-id="938db-122">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="938db-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="938db-123">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="938db-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
