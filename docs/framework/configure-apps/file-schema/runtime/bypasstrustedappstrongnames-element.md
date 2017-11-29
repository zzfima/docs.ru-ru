---
title: "&lt;bypassTrustedAppStrongNames&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b3e1cb839e9e7fd81a5452c0e034c3552b230cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a><span data-ttu-id="dc699-102">&lt;bypassTrustedAppStrongNames&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="dc699-102">&lt;bypassTrustedAppStrongNames&gt; Element</span></span>
<span data-ttu-id="dc699-103">Указывает, следует ли пропустить проверку строгих имен для сборок с полным доверием, которые загружаются с полным доверием <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="dc699-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="dc699-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dc699-104">\<configuration></span></span>  
<span data-ttu-id="dc699-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="dc699-105">\<runtime></span></span>  
<span data-ttu-id="dc699-106">\<bypassTrustedAppStrongNames ></span><span class="sxs-lookup"><span data-stu-id="dc699-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc699-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc699-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc699-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc699-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dc699-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc699-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc699-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc699-110">Attributes</span></span>  
  
|<span data-ttu-id="dc699-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dc699-111">Attribute</span></span>|<span data-ttu-id="dc699-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dc699-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="dc699-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="dc699-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="dc699-114">Указывает, включена ли функция пропуска, позволяющая избежать проверки строгих имен для сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="dc699-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="dc699-115">Если эта функция включена, строгие имена не проверяются на правильность после загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="dc699-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="dc699-116">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="dc699-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="dc699-117">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="dc699-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="dc699-118">Значение</span><span class="sxs-lookup"><span data-stu-id="dc699-118">Value</span></span>|<span data-ttu-id="dc699-119">Описание</span><span class="sxs-lookup"><span data-stu-id="dc699-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="dc699-120">Подписей строгих имен для сборок с полным доверием не проверяются при загрузке в полностью доверенных сборок <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="dc699-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="dc699-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc699-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="dc699-122">Подписей строгих имен для сборок с полным доверием проверяются при загрузке в полностью доверенных сборок <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="dc699-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="dc699-123">Подпись со строгим именем проверяется только правильность подписи; не сравнивается с другим строгим именем для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="dc699-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc699-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc699-124">Child Elements</span></span>  
 <span data-ttu-id="dc699-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dc699-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc699-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc699-126">Parent Elements</span></span>  
  
|<span data-ttu-id="dc699-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc699-127">Element</span></span>|<span data-ttu-id="dc699-128">Описание</span><span class="sxs-lookup"><span data-stu-id="dc699-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dc699-129">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dc699-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dc699-130">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="dc699-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc699-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc699-131">Remarks</span></span>  
 <span data-ttu-id="dc699-132">Функция обхода строгих имен позволяет избежать затрат ресурсов для проверки подписей строгих имен сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="dc699-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="dc699-133">Функция обхода применима к любой сборке, подписанной со строгим именем и имеющей следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="dc699-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="dc699-134">Полное доверие без <xref:System.Security.Policy.StrongName> свидетельства (например, имеет `MyComputer` доказательства зоны).</span><span class="sxs-lookup"><span data-stu-id="dc699-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="dc699-135">Загрузка в домен <xref:System.AppDomain> с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="dc699-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="dc699-136">Загрузка из расположения со свойством <xref:System.AppDomainSetup.ApplicationBase%2A> домена <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="dc699-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="dc699-137">Подпись осуществлена без задержки.</span><span class="sxs-lookup"><span data-stu-id="dc699-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc699-138">Если функция пропуска отключена для всех приложений на компьютере с помощью раздела реестра, этот параметр не делает ничего.</span><span class="sxs-lookup"><span data-stu-id="dc699-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="dc699-139">Дополнительные сведения см. в разделе [как: отключение функции пропуска строгих имен](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="dc699-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc699-140">Пример</span><span class="sxs-lookup"><span data-stu-id="dc699-140">Example</span></span>  
 <span data-ttu-id="dc699-141">Приведенный ниже показано, как указать поведение, которое проверяет подпись строгого имени для сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="dc699-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc699-142">См. также</span><span class="sxs-lookup"><span data-stu-id="dc699-142">See Also</span></span>  
 [<span data-ttu-id="dc699-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="dc699-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="dc699-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="dc699-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="dc699-145">Практическое руководство. Отключение возможности обхода строгих имен</span><span class="sxs-lookup"><span data-stu-id="dc699-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
