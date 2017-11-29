---
title: "Обычные шаблоны разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd2d78e675ebc67cc2e49f5bc7141558d462a3e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="common-design-patterns"></a><span data-ttu-id="963ef-102">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="963ef-102">Common Design Patterns</span></span>
<span data-ttu-id="963ef-103">Существует большое количество книг на шаблонов программного обеспечения, шаблон языки и antipatterns, которые касаются очень широкий субъекта шаблонов.</span><span class="sxs-lookup"><span data-stu-id="963ef-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="963ef-104">Таким образом этот раздел предоставляет рекомендации и относящееся лишь ограниченный набор шаблонов, которые часто используются при разработке API платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="963ef-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="963ef-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="963ef-105">In This Section</span></span>  
 [<span data-ttu-id="963ef-106">Свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="963ef-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="963ef-107">Шаблон удаления</span><span class="sxs-lookup"><span data-stu-id="963ef-107">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)  
 <span data-ttu-id="963ef-108">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="963ef-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="963ef-109">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="963ef-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963ef-110">См. также</span><span class="sxs-lookup"><span data-stu-id="963ef-110">See Also</span></span>  
 [<span data-ttu-id="963ef-111">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="963ef-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
