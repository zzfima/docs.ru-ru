---
title: Имена пространств имен.
ms.date: 03/30/2017
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d68966f60c5039fd67195a03facc1586b9ed154
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44097013"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="8c1e3-102">Имена пространств имен.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-102">Names of Namespaces</span></span>
<span data-ttu-id="8c1e3-103">Как с помощью других рекомендациях по именованию, целью при именовании пространств имен является создание достаточно ясности для программиста, с помощью платформы для сразу знать содержимое пространства имен, вероятно, будет.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="8c1e3-104">Следующий шаблон определяет правило именования пространства имен:</span><span class="sxs-lookup"><span data-stu-id="8c1e3-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="8c1e3-105">Ниже приведены примеры:</span><span class="sxs-lookup"><span data-stu-id="8c1e3-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="8c1e3-106">**✓ DO** префикса пространства имен названия название компании, чтобы предотвратить пространства имен из разных компаний с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="8c1e3-107">**✓ DO** название стабильной, независимые от версии продукта, используемое на втором уровне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="8c1e3-108">**X DO NOT** использовать организационные иерархии как основу для имен в иерархии пространств имен, так как имена групп в организации, как правило краткосрочны.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="8c1e3-109">Организуйте иерархию пространств имен вокруг группы связанных технологий.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="8c1e3-110">**✓ DO** использовать PascalCasing и компонентов в отдельном пространстве имен с точками (например, `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="8c1e3-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="8c1e3-111">Если марки используется нетрадиционных регистр, соблюдайте торговой марки, даже если оно отклоняется от обычных имен регистр.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="8c1e3-112">**✓ CONSIDER** с помощью имена во множественном числе пространств имен, где это применимо.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="8c1e3-113">Например, использовать `System.Collections` вместо `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="8c1e3-114">Марки и акронимы, тем не менее исключения из этого правила.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="8c1e3-115">Например, использовать `System.IO` вместо `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="8c1e3-116">**X DO NOT** использовать то же имя для пространства имен и типа в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="8c1e3-117">Например, не используйте `Debug` как пространство имен имя и нужно будет указать класс с именем `Debug` в одном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="8c1e3-118">Некоторые компиляторы требуют таких типов должен быть полностью специфицированным.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="8c1e3-119">Пространства имен и конфликтов имен типов</span><span class="sxs-lookup"><span data-stu-id="8c1e3-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="8c1e3-120">**X DO NOT** ввести имена универсальных типов, таких как `Element`, `Node`, `Log`, и `Message`.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="8c1e3-121">Есть очень велика вероятность того, что это приведет к введите имя конфликтует в распространенных сценариях.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="8c1e3-122">Вы должны квалифицироваться имена универсальных типов (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="8c1e3-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="8c1e3-123">Существуют определенные правила для предотвращения конфликтов имен типов для различных категорий пространств имен.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="8c1e3-124">**Пространства имен модели приложения**</span><span class="sxs-lookup"><span data-stu-id="8c1e3-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="8c1e3-125">Пространства имен, принадлежащих одной модели приложения очень часто используются совместно, но они почти никогда не используются с пространствами имен других моделей приложений.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="8c1e3-126">Например <xref:System.Windows.Forms?displayProperty=nameWithType> вместе с очень редко используется пространство имен <xref:System.Web.UI?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="8c1e3-127">Ниже приведен список известных приложений модели пространство имен групп:</span><span class="sxs-lookup"><span data-stu-id="8c1e3-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="8c1e3-128">**X DO NOT** дать одинаковые имена, чтобы типы в пространствах имен в пределах одной модели приложения.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="8c1e3-129">Например, не добавляйте тип с именем `Page` для <xref:System.Web.UI.Adapters?displayProperty=nameWithType> пространства имен, так как <xref:System.Web.UI?displayProperty=nameWithType> пространство имен уже содержит тип с именем `Page`.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="8c1e3-130">**Пространства имен инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="8c1e3-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="8c1e3-131">Эта группа содержит пространства имен, которые редко импортируются во время разработки распространенных приложений.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="8c1e3-132">Например `.Design` пространства имен используются главным образом, при разработке программирования средств.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="8c1e3-133">Предотвращение конфликтов с типами из этих пространств имен не является критически важным.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="8c1e3-134">**Основные пространства имен**</span><span class="sxs-lookup"><span data-stu-id="8c1e3-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="8c1e3-135">Основные пространства имен включают все `System` пространства имен, за исключением пространства имен модели приложений и инфраструктуры пространств имен.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="8c1e3-136">Основные пространства имен включают, помимо прочего, `System`, `System.IO`, `System.Xml`, и `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="8c1e3-137">**X DO NOT** предоставляют типы имен, которые могли бы конфликтовать с любым типом из основных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="8c1e3-138">Например, никогда не используйте `Stream` как имя типа.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="8c1e3-139">Это вызовет конфликт с <xref:System.IO.Stream?displayProperty=nameWithType>, очень часто используемый тип.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="8c1e3-140">**Группы пространств имен технологий**</span><span class="sxs-lookup"><span data-stu-id="8c1e3-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="8c1e3-141">В эту категорию входят все пространства имен с тем же два первых узла пространства имен `(<Company>.<Technology>*`), такие как `Microsoft.Build.Utilities` и `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="8c1e3-142">Очень важно, что типы, принадлежащие к одной технологии не конфликтуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="8c1e3-143">**X DO NOT** назначить имена типов, которые могли бы конфликтовать с другими типами внутри одной технологии.</span><span class="sxs-lookup"><span data-stu-id="8c1e3-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="8c1e3-144">**X DO NOT** вводит конфликтов имен типов между типами из пространств имен технологии и пространстве имен модели приложения (если компонент не предназначен для использования с моделью приложения).</span><span class="sxs-lookup"><span data-stu-id="8c1e3-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="8c1e3-145">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="8c1e3-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8c1e3-146">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="8c1e3-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c1e3-147">См. также</span><span class="sxs-lookup"><span data-stu-id="8c1e3-147">See also</span></span>

- [<span data-ttu-id="8c1e3-148">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="8c1e3-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="8c1e3-149">Правила именования</span><span class="sxs-lookup"><span data-stu-id="8c1e3-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
