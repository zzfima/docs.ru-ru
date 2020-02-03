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
ms.openlocfilehash: 95aff35569e58eacfd064609140a29b53e0036da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743812"
---
# <a name="naming-resources"></a><span data-ttu-id="4453a-102">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="4453a-102">Naming Resources</span></span>
<span data-ttu-id="4453a-103">Так как на локализуемые ресурсы можно ссылаться через определенные объекты, как если бы они были свойствами, рекомендации по именованию ресурсов похожи на правила свойств.</span><span class="sxs-lookup"><span data-stu-id="4453a-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="4453a-104">✔️ использовать Паскалкасинг в ключах ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4453a-104">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="4453a-105">✔️ предоставлять описательные, а не короткие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="4453a-105">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="4453a-106">❌ не использовать ключевые слова языка для основных языков CLR.</span><span class="sxs-lookup"><span data-stu-id="4453a-106">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="4453a-107">✔️ использовать в качестве имен ресурсов только буквы, цифры и символы подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="4453a-107">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="4453a-108">✔️ использовать следующее соглашение об именовании для ресурсов сообщений об исключениях.</span><span class="sxs-lookup"><span data-stu-id="4453a-108">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="4453a-109">Идентификатор ресурса должен быть именем типа исключения и коротким идентификатором исключения:</span><span class="sxs-lookup"><span data-stu-id="4453a-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="4453a-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="4453a-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="4453a-111">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="4453a-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4453a-112">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4453a-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4453a-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4453a-113">See also</span></span>

- [<span data-ttu-id="4453a-114">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="4453a-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="4453a-115">Правила именования</span><span class="sxs-lookup"><span data-stu-id="4453a-115">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
