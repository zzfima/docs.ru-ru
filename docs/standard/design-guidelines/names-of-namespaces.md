---
title: "Имена пространств имен."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4fc0cb9183fde33887a3e84bb30cc3f79892586e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-namespaces"></a><span data-ttu-id="f6f06-102">Имена пространств имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-102">Names of Namespaces</span></span>
<span data-ttu-id="f6f06-103">Как с другими соглашениями об именовании, цель при именовании пространств имен является создание ясности достаточно для программистов, используя платформу немедленно знать, что содержимое пространства имен, скорее всего, будут.</span><span class="sxs-lookup"><span data-stu-id="f6f06-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="f6f06-104">Следующий шаблон определяет правило именования пространства имен:</span><span class="sxs-lookup"><span data-stu-id="f6f06-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="f6f06-105">Ниже приведены примеры.</span><span class="sxs-lookup"><span data-stu-id="f6f06-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="f6f06-106">**✓ СДЕЛАТЬ** префикса пространства имен названия название компании, чтобы предотвратить пространства имен из разных компаний с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="f6f06-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="f6f06-107">**✓ СДЕЛАТЬ** название стабильной, независимые от версии продукта, используемое на втором уровне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="f6f06-108">**X не** использовать организационные иерархии как основу для имен в иерархии пространств имен, так как имена групп в организации, как правило краткосрочны.</span><span class="sxs-lookup"><span data-stu-id="f6f06-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="f6f06-109">Организация иерархии пространств имен вокруг группы связанных технологий.</span><span class="sxs-lookup"><span data-stu-id="f6f06-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="f6f06-110">**СДЕЛАТЬ ✓** использовать PascalCasing и компонентов в отдельном пространстве имен с точками (например, `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="f6f06-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="f6f06-111">Если марки используется нетрадиционных регистр, необходимо следовать торговой марки, даже если она отличается от обычных имен регистр.</span><span class="sxs-lookup"><span data-stu-id="f6f06-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="f6f06-112">**✓ Попробуйте** с помощью имена во множественном числе пространств имен, где это применимо.</span><span class="sxs-lookup"><span data-stu-id="f6f06-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="f6f06-113">Например, использовать `System.Collections` вместо `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="f6f06-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="f6f06-114">Марки и акронимы, однако исключения из этого правила.</span><span class="sxs-lookup"><span data-stu-id="f6f06-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="f6f06-115">Например, использовать `System.IO` вместо `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="f6f06-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="f6f06-116">**X не** использовать то же имя для пространства имен и типа в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="f6f06-117">Например, не используйте `Debug` как пространство имен имя, а также предоставляют класс с именем `Debug` в том же пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="f6f06-118">Некоторые компиляторы требуют таких типов быть полным.</span><span class="sxs-lookup"><span data-stu-id="f6f06-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="f6f06-119">Пространства имен и конфликтов имен типов</span><span class="sxs-lookup"><span data-stu-id="f6f06-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="f6f06-120">**X не** ввести имена универсальных типов, таких как `Element`, `Node`, `Log`, и `Message`.</span><span class="sxs-lookup"><span data-stu-id="f6f06-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="f6f06-121">Имеется очень велика вероятность того, что это приведет к введите имя конфликтует общих сценариев.</span><span class="sxs-lookup"><span data-stu-id="f6f06-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="f6f06-122">Следует определить имена универсальных типов (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="f6f06-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="f6f06-123">Существуют конкретные рекомендации, чтобы избежать конфликтов имен типов для различных категорий пространств имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="f6f06-124">**Пространства имен модели приложения**</span><span class="sxs-lookup"><span data-stu-id="f6f06-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="f6f06-125">Пространства имен, принадлежащие одной модели приложения очень часто используются совместно, но почти никогда не используются с пространствами имен других моделей для приложения.</span><span class="sxs-lookup"><span data-stu-id="f6f06-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="f6f06-126">Например <xref:System.Windows.Forms?displayProperty=nameWithType> пространства имен очень редко используется совместно с <xref:System.Web.UI?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="f6f06-127">Ниже приведен список известных приложений модели пространства имен групп:</span><span class="sxs-lookup"><span data-stu-id="f6f06-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="f6f06-128">**X не** дать одинаковые имена, чтобы типы в пространствах имен в пределах одной модели приложения.</span><span class="sxs-lookup"><span data-stu-id="f6f06-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="f6f06-129">Например, не добавляйте тип с именем `Page` для <xref:System.Web.UI.Adapters?displayProperty=nameWithType> пространства имен, так как <xref:System.Web.UI?displayProperty=nameWithType> пространство имен уже содержит тип с именем `Page`.</span><span class="sxs-lookup"><span data-stu-id="f6f06-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="f6f06-130">**Пространства имен инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="f6f06-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="f6f06-131">Эта группа содержит пространства имен, которые редко импортируются во время разработки из распространенных приложений.</span><span class="sxs-lookup"><span data-stu-id="f6f06-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="f6f06-132">Например `.Design` при разработке программирования средств в основном используются пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="f6f06-133">Предотвращение конфликтов с типами в этих пространствах имен не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="f6f06-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="f6f06-134">**Основные пространства имен**</span><span class="sxs-lookup"><span data-stu-id="f6f06-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="f6f06-135">Основные пространства имен включают все `System` пространства имен, за исключением пространств имен модели приложений и инфраструктуры пространств имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="f6f06-136">Содержит основные пространства имен, в частности, `System`, `System.IO`, `System.Xml`, и `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="f6f06-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="f6f06-137">**X не** предоставляют типы имен, которые могли бы конфликтовать с любым типом из основных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="f6f06-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="f6f06-138">Например, никогда не использовать `Stream` как имя типа.</span><span class="sxs-lookup"><span data-stu-id="f6f06-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="f6f06-139">Оно будет конфликтовать со <xref:System.IO.Stream?displayProperty=nameWithType>, очень часто используемых типов.</span><span class="sxs-lookup"><span data-stu-id="f6f06-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="f6f06-140">**Группы пространств имен технологий**</span><span class="sxs-lookup"><span data-stu-id="f6f06-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="f6f06-141">В эту категорию входят все пространства имен с те же узлы первые два пространства имен `(<Company>.<Technology>*`), такие как `Microsoft.Build.Utilities` и `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="f6f06-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="f6f06-142">Очень важно, что типы, принадлежащие одной технологии не конфликтуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="f6f06-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="f6f06-143">**X не** назначить имена типов, которые могли бы конфликтовать с другими типами внутри одной технологии.</span><span class="sxs-lookup"><span data-stu-id="f6f06-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="f6f06-144">**X не** вводит конфликтов имен типов между типами из пространств имен технологии и пространстве имен модели приложения (если компонент не предназначен для использования с моделью приложения).</span><span class="sxs-lookup"><span data-stu-id="f6f06-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="f6f06-145">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="f6f06-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f6f06-146">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f6f06-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f06-147">См. также</span><span class="sxs-lookup"><span data-stu-id="f6f06-147">See Also</span></span>  
 [<span data-ttu-id="f6f06-148">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="f6f06-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="f6f06-149">Правила именования</span><span class="sxs-lookup"><span data-stu-id="f6f06-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
