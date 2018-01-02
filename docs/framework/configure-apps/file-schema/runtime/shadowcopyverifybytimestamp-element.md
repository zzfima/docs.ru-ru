---
title: "&lt;shadowCopyVerifyByTimestamp&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bae98c91c8a9b68ec7c21b142bc9f004c7bc1394
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a><span data-ttu-id="3befb-102">&lt;shadowCopyVerifyByTimestamp&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="3befb-102">&lt;shadowCopyVerifyByTimestamp&gt; Element</span></span>
<span data-ttu-id="3befb-103">Указывает, использует ли теневое копирование поведение при запуске по умолчанию, представленное в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], или возвращается к поведению при запуске, используемому в предыдущих версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3befb-103">Specifies whether shadow copying uses the default startup behavior introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="3befb-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="3befb-104">\<configuration> Element</span></span>  
<span data-ttu-id="3befb-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="3befb-105">\<runtime> Element</span></span>  
<span data-ttu-id="3befb-106">\<shadowCopyVerifyByTimestamp > элемент</span><span class="sxs-lookup"><span data-stu-id="3befb-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3befb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3befb-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3befb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3befb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3befb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3befb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3befb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3befb-110">Attributes</span></span>  
  
|<span data-ttu-id="3befb-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3befb-111">Attribute</span></span>|<span data-ttu-id="3befb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3befb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3befb-113">enabled</span><span class="sxs-lookup"><span data-stu-id="3befb-113">enabled</span></span>|<span data-ttu-id="3befb-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="3befb-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="3befb-115">Указывает ли домены приложений, использующих теневое копирование сравнивать отметки времени сборок при запуске, чтобы определить, обновляется ли сборки перед теневым копированием.</span><span class="sxs-lookup"><span data-stu-id="3befb-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3befb-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="3befb-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="3befb-117">Значение</span><span class="sxs-lookup"><span data-stu-id="3befb-117">Value</span></span>|<span data-ttu-id="3befb-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3befb-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3befb-119">true</span><span class="sxs-lookup"><span data-stu-id="3befb-119">true</span></span>|<span data-ttu-id="3befb-120">При запуске копируются только сборки, которые были обновлены с момента последнего копирования в каталог теневого копирования.</span><span class="sxs-lookup"><span data-stu-id="3befb-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="3befb-121">Это значение по умолчанию для [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3befb-121">This is the default for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>|  
|<span data-ttu-id="3befb-122">false</span><span class="sxs-lookup"><span data-stu-id="3befb-122">false</span></span>|<span data-ttu-id="3befb-123">Возвращается к поведению при запуске предыдущих версий платформы .NET Framework, который был для копирования всех файлов во время запуска.</span><span class="sxs-lookup"><span data-stu-id="3befb-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3befb-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3befb-124">Child Elements</span></span>  
 <span data-ttu-id="3befb-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3befb-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3befb-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3befb-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3befb-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="3befb-127">Element</span></span>|<span data-ttu-id="3befb-128">Описание</span><span class="sxs-lookup"><span data-stu-id="3befb-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3befb-129">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3befb-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3befb-130">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="3befb-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3befb-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="3befb-131">Remarks</span></span>  
 <span data-ttu-id="3befb-132">Начиная с [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], выполняется теневое копирование только в том случае, если их отметки времени показывают, что они были изменены с момента последнего копирования в каталог теневого копирования сборок.</span><span class="sxs-lookup"><span data-stu-id="3befb-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="3befb-133">Это сокращает время запуска для многих приложений, использующих теневое копирование, как описано в [теневое копирование сборок](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="3befb-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="3befb-134">Для приложений с большим процентом и высокой частотой обновления сборок это изменение в поведении может не быть выгодно.</span><span class="sxs-lookup"><span data-stu-id="3befb-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="3befb-135">В этом случае можно использовать этот элемент для восстановления поведения предыдущих версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3befb-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3befb-136">Пример</span><span class="sxs-lookup"><span data-stu-id="3befb-136">Example</span></span>  
 <span data-ttu-id="3befb-137">Приведенный ниже показано, как отключить поведение по умолчанию при запуске теневое копирование в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]и вернуться к поведению при запуске предыдущих версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3befb-137">The following example shows how to disable the default startup behavior of shadow copying in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3befb-138">См. также</span><span class="sxs-lookup"><span data-stu-id="3befb-138">See Also</span></span>  
 [<span data-ttu-id="3befb-139">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="3befb-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="3befb-140">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="3befb-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="3befb-141">Теневое копирование сборок</span><span class="sxs-lookup"><span data-stu-id="3befb-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
