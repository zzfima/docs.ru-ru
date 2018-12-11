---
title: Незапечатанные классы
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: 8d7b1500506ec73a0d33d5352756cb85039358e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153232"
---
# <a name="unsealed-classes"></a><span data-ttu-id="db293-102">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="db293-102">Unsealed Classes</span></span>
<span data-ttu-id="db293-103">Запечатанные классы не может наследоваться от, а также предотвращают расширяемости.</span><span class="sxs-lookup"><span data-stu-id="db293-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="db293-104">В противоположность этому классы, которые могут наследоваться от называются незапечатанные классы.</span><span class="sxs-lookup"><span data-stu-id="db293-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="db293-105">**✓ CONSIDER** использование незапечатанных классов с нет добавить виртуальный или защищенных членов, так как это отличный способ недорогого еще очень полезного расширяемость для платформу.</span><span class="sxs-lookup"><span data-stu-id="db293-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="db293-106">Разработчики часто должно производиться наследование незапечатанные классы таким образом, чтобы добавить членов удобства, таких как пользовательские конструкторы, новые методы или перегрузки метода.</span><span class="sxs-lookup"><span data-stu-id="db293-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="db293-107">Например `System.Messaging.MessageQueue` не запечатан и таким образом позволяет пользователям создавать пользовательские очереди это значение по умолчанию для пути к определенной очереди или добавление пользовательских методов, которые упрощают API для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="db293-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="db293-108">Являются незапечатанных классов по умолчанию в большей части языков программирования, и это также рекомендуемый по умолчанию для большинства классов в платформ.</span><span class="sxs-lookup"><span data-stu-id="db293-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="db293-109">Благодарим вас за пользователями framework и довольно недорого из-за сравнительно мало тестов затраты, связанные с незапечатанных типов, расширяемости, обеспечиваемый незапечатанных типов.</span><span class="sxs-lookup"><span data-stu-id="db293-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="db293-110">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="db293-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="db293-111">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="db293-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db293-112">См. также</span><span class="sxs-lookup"><span data-stu-id="db293-112">See also</span></span>

- [<span data-ttu-id="db293-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="db293-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="db293-114">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="db293-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="db293-115">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="db293-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
