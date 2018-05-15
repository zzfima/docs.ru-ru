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
ms.openlocfilehash: 99b27615ef16aa69e18d82cb97f4751dc92d2ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="6c9ec-102">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="6c9ec-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="6c9ec-103">Обработка исключений имеет множество преимуществ перед отчеты об ошибках на основе возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="6c9ec-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="6c9ec-104">Хорошей платформы разработки позволяет использовать преимущества исключения разработчик приложения.</span><span class="sxs-lookup"><span data-stu-id="6c9ec-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="6c9ec-105">В этом разделе рассматриваются преимущества исключения и представлены рекомендации по эффективному использованию.</span><span class="sxs-lookup"><span data-stu-id="6c9ec-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c9ec-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6c9ec-106">In This Section</span></span>  
 [<span data-ttu-id="6c9ec-107">Создание исключений</span><span class="sxs-lookup"><span data-stu-id="6c9ec-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="6c9ec-108">Использование исключений стандартных типов</span><span class="sxs-lookup"><span data-stu-id="6c9ec-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="6c9ec-109">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="6c9ec-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="6c9ec-110">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="6c9ec-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6c9ec-111">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6c9ec-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c9ec-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6c9ec-112">See Also</span></span>  
 [<span data-ttu-id="6c9ec-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="6c9ec-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
