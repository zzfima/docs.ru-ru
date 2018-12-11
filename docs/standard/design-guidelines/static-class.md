---
title: Разработка статичных классов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: KrzysztofCwalina
ms.openlocfilehash: a521842d8c4651984d8d6667b93b0f28a1eba894
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130785"
---
# <a name="static-class-design"></a><span data-ttu-id="03344-102">Разработка статичных классов</span><span class="sxs-lookup"><span data-stu-id="03344-102">Static Class Design</span></span>
<span data-ttu-id="03344-103">Статический класс представляет собой класс, который содержит только статические члены (Конечно, помимо экземпляр членам, унаследованным от <xref:System.Object?displayProperty=nameWithType> и возможно закрытый конструктор).</span><span class="sxs-lookup"><span data-stu-id="03344-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="03344-104">Некоторые языки предоставляют встроенную поддержку для статических классов.</span><span class="sxs-lookup"><span data-stu-id="03344-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="03344-105">В C# 2.0 и более поздних версий когда класс объявлен как статический, это запечатанный, абстрактный, и нет членов экземпляров можно переопределить или объявлен.</span><span class="sxs-lookup"><span data-stu-id="03344-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="03344-106">Статические классы — это компромисс между чисто объектно ориентированного проектирования и простотой.</span><span class="sxs-lookup"><span data-stu-id="03344-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="03344-107">Они часто используются для предоставления ярлыки для других операций (таких как <xref:System.IO.File?displayProperty=nameWithType>), владельцы методы расширения, или функции, для которой полное объектно ориентированную оболочку несанкционированному (такие как <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="03344-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="03344-108">**✓ DO** статические классы предназначены для использования только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="03344-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="03344-109">Статические классы должны использоваться только в качестве вспомогательных классов для объектно-ориентированной платформы.</span><span class="sxs-lookup"><span data-stu-id="03344-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="03344-110">**X DO NOT** используйте статические классы как всевозможных объектов.</span><span class="sxs-lookup"><span data-stu-id="03344-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="03344-111">**X DO NOT** объявления или переопределять члены экземпляра в статических классах.</span><span class="sxs-lookup"><span data-stu-id="03344-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="03344-112">**✓ DO** объявить как запечатанный, абстрактный статических классов и добавьте конструктор закрытого экземпляра, если язык программирования не предусмотрена встроенная поддержка статических классов.</span><span class="sxs-lookup"><span data-stu-id="03344-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="03344-113">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="03344-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="03344-114">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="03344-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03344-115">См. также</span><span class="sxs-lookup"><span data-stu-id="03344-115">See also</span></span>

- [<span data-ttu-id="03344-116">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="03344-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="03344-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="03344-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
