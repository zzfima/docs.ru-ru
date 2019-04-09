---
title: <bypassTrustedAppStrongNames> Элемент
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c39d9a1e3da9cccb2f027e9597a6f2272d187ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179144"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="e3b35-102">\<bypassTrustedAppStrongNames > элемент</span><span class="sxs-lookup"><span data-stu-id="e3b35-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="e3b35-103">Указывает, следует ли пропустить проверку строгих имен для сборок с полным доверием, которые загружаются с полным доверием <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="e3b35-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="e3b35-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e3b35-104">\<configuration></span></span>  
<span data-ttu-id="e3b35-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="e3b35-105">\<runtime></span></span>  
<span data-ttu-id="e3b35-106">\<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="e3b35-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b35-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3b35-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3b35-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3b35-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e3b35-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3b35-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3b35-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3b35-110">Attributes</span></span>  
  
|<span data-ttu-id="e3b35-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e3b35-111">Attribute</span></span>|<span data-ttu-id="e3b35-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e3b35-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e3b35-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e3b35-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e3b35-114">Указывает, включена ли функция пропуска, позволяющая избежать проверки строгих имен для сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="e3b35-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="e3b35-115">Если эта функция включена, строгие имена не проверяются на правильность при загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="e3b35-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="e3b35-116">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="e3b35-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e3b35-117">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="e3b35-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="e3b35-118">Значение</span><span class="sxs-lookup"><span data-stu-id="e3b35-118">Value</span></span>|<span data-ttu-id="e3b35-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e3b35-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="e3b35-120">Подписи строгих имен сборок с полным доверием не проверяются, когда сборки загружаются в с полным доверием <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="e3b35-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="e3b35-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3b35-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="e3b35-122">Подписи строгого имени для сборок с полным доверием проверяются при сборки загружаются в с полным доверием <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="e3b35-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="e3b35-123">Подпись строгого имени проверяется только правильность подписи; они не сравниваются с другой строгого имени для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="e3b35-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3b35-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3b35-124">Child Elements</span></span>  
 <span data-ttu-id="e3b35-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e3b35-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3b35-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3b35-126">Parent Elements</span></span>  
  
|<span data-ttu-id="e3b35-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3b35-127">Element</span></span>|<span data-ttu-id="e3b35-128">Описание</span><span class="sxs-lookup"><span data-stu-id="e3b35-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e3b35-129">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3b35-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e3b35-130">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e3b35-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3b35-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3b35-131">Remarks</span></span>  
 <span data-ttu-id="e3b35-132">Функция пропуска строгих имен избежать дополнительной нагрузки, проверка подписи строгого имени сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="e3b35-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="e3b35-133">Функция обхода применима к любой сборке, подписанной со строгим именем и имеющей следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="e3b35-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="e3b35-134">Полное доверие без <xref:System.Security.Policy.StrongName> свидетельства (например, имеет `MyComputer` свидетельство зоны).</span><span class="sxs-lookup"><span data-stu-id="e3b35-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="e3b35-135">Загрузка в домен <xref:System.AppDomain> с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="e3b35-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="e3b35-136">Загрузка из расположения со свойством <xref:System.AppDomainSetup.ApplicationBase%2A> домена <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="e3b35-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="e3b35-137">Подпись осуществлена без задержки.</span><span class="sxs-lookup"><span data-stu-id="e3b35-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3b35-138">Если функция пропуска отключена для всех приложений на компьютере с помощью раздела реестра, этот параметр не влияет.</span><span class="sxs-lookup"><span data-stu-id="e3b35-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="e3b35-139">Дополнительные сведения см. в разделе [Как Отключение возможности обхода строгих имен](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="e3b35-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3b35-140">Пример</span><span class="sxs-lookup"><span data-stu-id="e3b35-140">Example</span></span>  
 <span data-ttu-id="e3b35-141">Приведенный ниже показано, как указать поведение, которое проверяет подпись строгого имени сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="e3b35-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3b35-142">См. также</span><span class="sxs-lookup"><span data-stu-id="e3b35-142">See also</span></span>

- [<span data-ttu-id="e3b35-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e3b35-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="e3b35-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3b35-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e3b35-145">Практическое руководство. Отключение функции пропуска строгих имен</span><span class="sxs-lookup"><span data-stu-id="e3b35-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
