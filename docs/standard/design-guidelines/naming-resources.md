---
title: Именование ресурсов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b100366952b1f536d187eb72c6d80c86bb3e572e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="naming-resources"></a><span data-ttu-id="ed91a-102">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="ed91a-102">Naming Resources</span></span>
<span data-ttu-id="ed91a-103">Поскольку локализуемые ресурсы можно ссылаться через определенные объекты, как если бы они были свойства, правилам именования для ресурсов похожи на правила свойств.</span><span class="sxs-lookup"><span data-stu-id="ed91a-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="ed91a-104">**✓ СДЕЛАТЬ** использовать PascalCasing в ключи ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ed91a-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="ed91a-105">**✓ СДЕЛАТЬ** предоставляют описательные, а не короткие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="ed91a-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="ed91a-106">**X не** использовать зарезервированные слова языка основных языков среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ed91a-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="ed91a-107">**✓ СДЕЛАТЬ** использовать только буквы, цифры и знаки подчеркивания, при именовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ed91a-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="ed91a-108">**✓ СДЕЛАТЬ** используется следующее соглашение об именовании ресурсов сообщение исключения.</span><span class="sxs-lookup"><span data-stu-id="ed91a-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="ed91a-109">Идентификатор ресурса должен быть именем типа исключения, а также с коротким идентификатором исключения:</span><span class="sxs-lookup"><span data-stu-id="ed91a-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="ed91a-110">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="ed91a-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ed91a-111">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ed91a-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed91a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ed91a-112">See Also</span></span>  
 [<span data-ttu-id="ed91a-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="ed91a-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="ed91a-114">Правила именования</span><span class="sxs-lookup"><span data-stu-id="ed91a-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
