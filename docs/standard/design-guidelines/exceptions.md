---
title: Правила разработки исключений
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6dcd29f96ce32f1b2602af5d844339fe33c0ed7b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="92ae4-102">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="92ae4-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="92ae4-103">Обработка исключений имеет множество преимуществ перед отчеты об ошибках на основе возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="92ae4-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="92ae4-104">Хорошей платформы разработки позволяет использовать преимущества исключения разработчик приложения.</span><span class="sxs-lookup"><span data-stu-id="92ae4-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="92ae4-105">В этом разделе рассматриваются преимущества исключения и представлены рекомендации по эффективному использованию.</span><span class="sxs-lookup"><span data-stu-id="92ae4-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92ae4-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="92ae4-106">In This Section</span></span>  
 [<span data-ttu-id="92ae4-107">Создание исключений</span><span class="sxs-lookup"><span data-stu-id="92ae4-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="92ae4-108">Использование исключений стандартных типов</span><span class="sxs-lookup"><span data-stu-id="92ae4-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="92ae4-109">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="92ae4-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="92ae4-110">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="92ae4-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="92ae4-111">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="92ae4-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ae4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="92ae4-112">See Also</span></span>  
 [<span data-ttu-id="92ae4-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="92ae4-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
