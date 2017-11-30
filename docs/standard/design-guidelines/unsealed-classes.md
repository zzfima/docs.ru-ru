---
title: "Незапечатанные классы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f950d8de2681868fe28e09e4b51bd8156cd12e94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="unsealed-classes"></a><span data-ttu-id="1c967-102">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="1c967-102">Unsealed Classes</span></span>
<span data-ttu-id="1c967-103">Невозможно наследовать запечатанные классы и не позволяют расширяемости.</span><span class="sxs-lookup"><span data-stu-id="1c967-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="1c967-104">В противоположность этому классы, которые могут наследоваться от называются незапечатанных классов.</span><span class="sxs-lookup"><span data-stu-id="1c967-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="1c967-105">**✓ Попробуйте** использование незапечатанных классов с нет добавить виртуальный или защищенных членов, так как это отличный способ недорогого еще очень полезного расширяемость для платформу.</span><span class="sxs-lookup"><span data-stu-id="1c967-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="1c967-106">Разработчики часто требуется наследовать от незапечатанных классов таким образом, чтобы добавить членов удобства, например пользовательских конструкторов, новые методы или перегруженных версий метода.</span><span class="sxs-lookup"><span data-stu-id="1c967-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="1c967-107">Например `System.Messaging.MessageQueue` не запечатан, и таким образом позволяет пользователям создавать пользовательские очереди это значение по умолчанию для определенной очереди путь или добавить пользовательские методы, которые упрощают API для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="1c967-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="1c967-108">Являются незапечатанных классов по умолчанию в большей части языков программирования, а кроме того, это рекомендуемое значение по умолчанию для большинства классов платформы.</span><span class="sxs-lookup"><span data-stu-id="1c967-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="1c967-109">Расширяемость, обеспечиваемая незапечатанных типов намного пользователями framework с благодарностью довольно легко создать из-за сравнительно мало тестов затраты, связанные с незапечатанные типы.</span><span class="sxs-lookup"><span data-stu-id="1c967-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="1c967-110">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="1c967-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1c967-111">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="1c967-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c967-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1c967-112">See Also</span></span>  
 [<span data-ttu-id="1c967-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="1c967-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="1c967-114">Разработка для расширяемости</span><span class="sxs-lookup"><span data-stu-id="1c967-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="1c967-115">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="1c967-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
