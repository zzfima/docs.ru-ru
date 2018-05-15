---
title: Правила разработки членов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c04b431224a1d4f03e85397b854a52856e114e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="member-design-guidelines"></a><span data-ttu-id="e81d4-102">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="e81d4-102">Member Design Guidelines</span></span>
<span data-ttu-id="e81d4-103">Методы, свойства, события, конструкторы и поля называются членами.</span><span class="sxs-lookup"><span data-stu-id="e81d4-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="e81d4-104">Члены могут в конечном счете средства, с помощью которого framework функциональность предоставляется пользователям платформы.</span><span class="sxs-lookup"><span data-stu-id="e81d4-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="e81d4-105">Члены может быть виртуальными или невиртуальные, конкретная или абстрактными, статический метод или экземпляр и может иметь несколько различных областях специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="e81d4-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="e81d4-106">Этот диапазон предоставляет огромный выразительности, но в то же время требует внимания со стороны конструктора framework.</span><span class="sxs-lookup"><span data-stu-id="e81d4-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="e81d4-107">В этой главе предоставляет основные правила, которые следует выполнить при разработке члены любого типа.</span><span class="sxs-lookup"><span data-stu-id="e81d4-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e81d4-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e81d4-108">In This Section</span></span>  
 [<span data-ttu-id="e81d4-109">Перегрузка членов</span><span class="sxs-lookup"><span data-stu-id="e81d4-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="e81d4-110">Разработка свойств</span><span class="sxs-lookup"><span data-stu-id="e81d4-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="e81d4-111">Разработка конструкторов</span><span class="sxs-lookup"><span data-stu-id="e81d4-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="e81d4-112">Разработка событий</span><span class="sxs-lookup"><span data-stu-id="e81d4-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="e81d4-113">Разработка полей</span><span class="sxs-lookup"><span data-stu-id="e81d4-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="e81d4-114">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="e81d4-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="e81d4-115">Перегрузки операторов</span><span class="sxs-lookup"><span data-stu-id="e81d4-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="e81d4-116">Разработка параметров</span><span class="sxs-lookup"><span data-stu-id="e81d4-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="e81d4-117">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e81d4-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e81d4-118">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e81d4-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81d4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e81d4-119">See Also</span></span>  
 [<span data-ttu-id="e81d4-120">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="e81d4-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
