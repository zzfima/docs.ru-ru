---
title: Обычные шаблоны разработки
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
author: KrzysztofCwalina
ms.openlocfilehash: d0b16530863b009010383c8739c9512738dfdffd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026475"
---
# <a name="common-design-patterns"></a><span data-ttu-id="bc68f-102">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="bc68f-102">Common Design Patterns</span></span>
<span data-ttu-id="bc68f-103">Существует большое количество книг на шаблоны программного обеспечения, шаблон языков и антишаблоны, предназначенным для очень обширная тема шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bc68f-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="bc68f-104">Таким образом в этой главе содержатся рекомендации и обсуждения, связанные с очень ограниченный набор шаблонов, которые часто используются в разработке API-интерфейсы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc68f-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc68f-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="bc68f-105">In This Section</span></span>  
 [<span data-ttu-id="bc68f-106">Свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="bc68f-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="bc68f-107">Шаблон ликвидации</span><span class="sxs-lookup"><span data-stu-id="bc68f-107">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)  
 <span data-ttu-id="bc68f-108">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="bc68f-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bc68f-109">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="bc68f-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc68f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bc68f-110">See also</span></span>

- [<span data-ttu-id="bc68f-111">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="bc68f-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
