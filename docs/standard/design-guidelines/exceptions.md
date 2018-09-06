---
title: Правила разработки исключений
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51cc5296a7b3f6d75b5e56d6bbc74330fa147848
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43876639"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="fe64f-102">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="fe64f-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="fe64f-103">Обработка исключений имеет множество преимуществ перед отчеты об ошибках на основе возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="fe64f-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="fe64f-104">Хорошей платформы разработки помогает реализовать преимущества исключения разработчик приложения.</span><span class="sxs-lookup"><span data-stu-id="fe64f-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="fe64f-105">В этом разделе описаны преимущества исключения и представлены рекомендации по эффективному использованию.</span><span class="sxs-lookup"><span data-stu-id="fe64f-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe64f-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fe64f-106">In This Section</span></span>  
 [<span data-ttu-id="fe64f-107">Создание исключений</span><span class="sxs-lookup"><span data-stu-id="fe64f-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="fe64f-108">Использование исключений стандартных типов</span><span class="sxs-lookup"><span data-stu-id="fe64f-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="fe64f-109">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="fe64f-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="fe64f-110">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="fe64f-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="fe64f-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="fe64f-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe64f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fe64f-112">See also</span></span>

- [<span data-ttu-id="fe64f-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="fe64f-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
