---
title: Именование ресурсов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: b64a3ef6e12f8ea1abf7efd9c22f2f4333dda5c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709170"
---
# <a name="naming-resources"></a><span data-ttu-id="dfa1c-102">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="dfa1c-102">Naming Resources</span></span>
<span data-ttu-id="dfa1c-103">Так как на локализуемые ресурсы можно ссылаться через определенные объекты, как если бы они были свойствами, рекомендации по именованию ресурсов похожи на правила свойств.</span><span class="sxs-lookup"><span data-stu-id="dfa1c-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="dfa1c-104">**✓ DO** использовать PascalCasing в ключи ресурсов.</span><span class="sxs-lookup"><span data-stu-id="dfa1c-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="dfa1c-105">**✓ DO** предоставляют описательные, а не короткие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="dfa1c-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="dfa1c-106">**X DO NOT** использовать зарезервированные слова языка основных языков среды CLR.</span><span class="sxs-lookup"><span data-stu-id="dfa1c-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="dfa1c-107">**✓ DO** использовать только буквы, цифры и знаки подчеркивания, при именовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="dfa1c-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="dfa1c-108">**✓ DO** используется следующее соглашение об именовании ресурсов сообщение исключения.</span><span class="sxs-lookup"><span data-stu-id="dfa1c-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="dfa1c-109">Идентификатор ресурса должен быть именем типа исключения и коротким идентификатором исключения:</span><span class="sxs-lookup"><span data-stu-id="dfa1c-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="dfa1c-110">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="dfa1c-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dfa1c-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="dfa1c-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa1c-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfa1c-112">See also</span></span>

- [<span data-ttu-id="dfa1c-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="dfa1c-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="dfa1c-114">Правила именования</span><span class="sxs-lookup"><span data-stu-id="dfa1c-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
