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
ms.openlocfilehash: 672d36c6b888ee9a89a76d5d417a7a7e92dd8f36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571665"
---
# <a name="unsealed-classes"></a><span data-ttu-id="59793-102">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="59793-102">Unsealed Classes</span></span>
<span data-ttu-id="59793-103">Невозможно наследовать запечатанные классы и не позволяют расширяемости.</span><span class="sxs-lookup"><span data-stu-id="59793-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="59793-104">В противоположность этому классы, которые могут наследоваться от называются незапечатанных классов.</span><span class="sxs-lookup"><span data-stu-id="59793-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="59793-105">**✓ CONSIDER** использование незапечатанных классов с нет добавить виртуальный или защищенных членов, так как это отличный способ недорогого еще очень полезного расширяемость для платформу.</span><span class="sxs-lookup"><span data-stu-id="59793-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="59793-106">Разработчики часто требуется наследовать от незапечатанных классов таким образом, чтобы добавить членов удобства, например пользовательских конструкторов, новые методы или перегруженных версий метода.</span><span class="sxs-lookup"><span data-stu-id="59793-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="59793-107">Например `System.Messaging.MessageQueue` не запечатан, и таким образом позволяет пользователям создавать пользовательские очереди это значение по умолчанию для определенной очереди путь или добавить пользовательские методы, которые упрощают API для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="59793-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="59793-108">Являются незапечатанных классов по умолчанию в большей части языков программирования, а кроме того, это рекомендуемое значение по умолчанию для большинства классов платформы.</span><span class="sxs-lookup"><span data-stu-id="59793-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="59793-109">Расширяемость, обеспечиваемая незапечатанных типов намного пользователями framework с благодарностью довольно легко создать из-за сравнительно мало тестов затраты, связанные с незапечатанные типы.</span><span class="sxs-lookup"><span data-stu-id="59793-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="59793-110">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="59793-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="59793-111">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="59793-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59793-112">См. также</span><span class="sxs-lookup"><span data-stu-id="59793-112">See Also</span></span>  
 [<span data-ttu-id="59793-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="59793-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="59793-114">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="59793-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="59793-115">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="59793-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
