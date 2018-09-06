---
title: Незапечатанные классы
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef0f1c4c9b2d1928d6f96d62ab12df9786756498
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891381"
---
# <a name="unsealed-classes"></a><span data-ttu-id="e5135-102">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="e5135-102">Unsealed Classes</span></span>
<span data-ttu-id="e5135-103">Запечатанные классы не может наследоваться от, а также предотвращают расширяемости.</span><span class="sxs-lookup"><span data-stu-id="e5135-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="e5135-104">В противоположность этому классы, которые могут наследоваться от называются незапечатанные классы.</span><span class="sxs-lookup"><span data-stu-id="e5135-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="e5135-105">**✓ CONSIDER** использование незапечатанных классов с нет добавить виртуальный или защищенных членов, так как это отличный способ недорогого еще очень полезного расширяемость для платформу.</span><span class="sxs-lookup"><span data-stu-id="e5135-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="e5135-106">Разработчики часто должно производиться наследование незапечатанные классы таким образом, чтобы добавить членов удобства, таких как пользовательские конструкторы, новые методы или перегрузки метода.</span><span class="sxs-lookup"><span data-stu-id="e5135-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="e5135-107">Например `System.Messaging.MessageQueue` не запечатан и таким образом позволяет пользователям создавать пользовательские очереди это значение по умолчанию для пути к определенной очереди или добавление пользовательских методов, которые упрощают API для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="e5135-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="e5135-108">Являются незапечатанных классов по умолчанию в большей части языков программирования, и это также рекомендуемый по умолчанию для большинства классов в платформ.</span><span class="sxs-lookup"><span data-stu-id="e5135-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="e5135-109">Благодарим вас за пользователями framework и довольно недорого из-за сравнительно мало тестов затраты, связанные с незапечатанных типов, расширяемости, обеспечиваемый незапечатанных типов.</span><span class="sxs-lookup"><span data-stu-id="e5135-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="e5135-110">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e5135-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e5135-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e5135-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5135-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e5135-112">See also</span></span>

- [<span data-ttu-id="e5135-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="e5135-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="e5135-114">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="e5135-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="e5135-115">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="e5135-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
