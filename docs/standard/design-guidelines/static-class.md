---
title: "Разработка статичных классов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8c36bf5790d033eddb6bb7e0d910482143a9bcac
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="static-class-design"></a><span data-ttu-id="ce3f7-102">Разработка статичных классов</span><span class="sxs-lookup"><span data-stu-id="ce3f7-102">Static Class Design</span></span>
<span data-ttu-id="ce3f7-103">Статический класс был определен как класс, который содержит только статические члены (Разумеется, помимо экземпляр члены, унаследованные от <xref:System.Object?displayProperty=nameWithType> и возможно закрытый конструктор).</span><span class="sxs-lookup"><span data-stu-id="ce3f7-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="ce3f7-104">Некоторые языки предоставляют встроенную поддержку для статических классов.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="ce3f7-105">В C# 2.0 и более поздних версиях при объявлении класса статический Это запечатанный, абстрактный и нет членов экземпляра может быть переопределено или объявлен.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="ce3f7-106">Статические классы — это компромисс между чисто объектно ориентированный проект и простота.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="ce3f7-107">Они часто используются для предоставления ярлыки для других операций (таких как <xref:System.IO.File?displayProperty=nameWithType>), владельцы методы расширения, или функции, для которой полное объектно ориентированную оболочку несанкционированному (такие как <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="ce3f7-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="ce3f7-108">**✓ СДЕЛАТЬ** статические классы предназначены для использования только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="ce3f7-109">Статические классы должны использоваться только в качестве вспомогательных классов для объектно-ориентированной платформы.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="ce3f7-110">**X не** используйте статические классы как всевозможных объектов.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="ce3f7-111">**X не** объявления или переопределять члены экземпляра в статических классах.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="ce3f7-112">**✓ СДЕЛАТЬ** объявить как запечатанный, абстрактный статических классов и добавьте конструктор закрытого экземпляра, если язык программирования не предусмотрена встроенная поддержка статических классов.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="ce3f7-113">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="ce3f7-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ce3f7-114">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ce3f7-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3f7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ce3f7-115">See Also</span></span>  
 [<span data-ttu-id="ce3f7-116">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="ce3f7-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="ce3f7-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="ce3f7-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
