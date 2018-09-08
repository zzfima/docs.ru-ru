---
title: Именование ресурсов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b53fc383e6fc9a5f056bab4eabde9979cd734b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44186179"
---
# <a name="naming-resources"></a><span data-ttu-id="50e0a-102">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="50e0a-102">Naming Resources</span></span>
<span data-ttu-id="50e0a-103">Так как локализуемые ресурсы можно ссылаться с помощью определенных объектов, как если бы они были свойства, рекомендации по именованию для ресурсов похожи на правила свойств.</span><span class="sxs-lookup"><span data-stu-id="50e0a-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="50e0a-104">**✓ DO** использовать PascalCasing в ключи ресурсов.</span><span class="sxs-lookup"><span data-stu-id="50e0a-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="50e0a-105">**✓ DO** предоставляют описательные, а не короткие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="50e0a-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="50e0a-106">**X DO NOT** использовать зарезервированные слова языка основных языков среды CLR.</span><span class="sxs-lookup"><span data-stu-id="50e0a-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="50e0a-107">**✓ DO** использовать только буквы, цифры и знаки подчеркивания, при именовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="50e0a-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="50e0a-108">**✓ DO** используется следующее соглашение об именовании ресурсов сообщение исключения.</span><span class="sxs-lookup"><span data-stu-id="50e0a-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="50e0a-109">Идентификатор ресурса должен быть именем типа исключения, а также краткого идентификатора исключения:</span><span class="sxs-lookup"><span data-stu-id="50e0a-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="50e0a-110">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="50e0a-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="50e0a-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="50e0a-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e0a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="50e0a-112">See also</span></span>

- [<span data-ttu-id="50e0a-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="50e0a-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="50e0a-114">Правила именования</span><span class="sxs-lookup"><span data-stu-id="50e0a-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
