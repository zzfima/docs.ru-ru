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
ms.openlocfilehash: d1598ac63af38f1ca3e11104bc8e1cd6323d35ed
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190180"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="90d2c-102">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="90d2c-102">Member Design Guidelines</span></span>
<span data-ttu-id="90d2c-103">Методы, свойства, события, конструкторы и поля в совокупности называются членами.</span><span class="sxs-lookup"><span data-stu-id="90d2c-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="90d2c-104">Элементы в конечном счете являются средства, по которому framework функциональность предоставляется конечным пользователям платформы.</span><span class="sxs-lookup"><span data-stu-id="90d2c-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="90d2c-105">Члены могут быть виртуальными или невиртуальные, конкретные или абстрактными, статический или экземпляр и может иметь несколько различных областях специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="90d2c-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="90d2c-106">Такое разнообразие предоставляет невероятно выразительности, но в то же время требует внимания со стороны конструктор framework.</span><span class="sxs-lookup"><span data-stu-id="90d2c-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="90d2c-107">В этой главе предлагает основные рекомендации, которые следует выполнить при разработке члены любого типа.</span><span class="sxs-lookup"><span data-stu-id="90d2c-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90d2c-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="90d2c-108">In This Section</span></span>  
 [<span data-ttu-id="90d2c-109">Перегрузка членов</span><span class="sxs-lookup"><span data-stu-id="90d2c-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="90d2c-110">Разработка свойств</span><span class="sxs-lookup"><span data-stu-id="90d2c-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="90d2c-111">Разработка конструкторов</span><span class="sxs-lookup"><span data-stu-id="90d2c-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="90d2c-112">Разработка событий</span><span class="sxs-lookup"><span data-stu-id="90d2c-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="90d2c-113">Разработка полей</span><span class="sxs-lookup"><span data-stu-id="90d2c-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="90d2c-114">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="90d2c-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="90d2c-115">Перегрузки операторов</span><span class="sxs-lookup"><span data-stu-id="90d2c-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="90d2c-116">Разработка параметров</span><span class="sxs-lookup"><span data-stu-id="90d2c-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="90d2c-117">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="90d2c-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="90d2c-118">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="90d2c-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d2c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="90d2c-119">See also</span></span>

- [<span data-ttu-id="90d2c-120">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="90d2c-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
