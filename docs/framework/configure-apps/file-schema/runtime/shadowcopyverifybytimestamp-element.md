---
title: Элемент <shadowCopyVerifyByTimestamp>
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f3ea57364832553d16c7e34fc887b1c9f821602
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663452"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="cb767-102">Элемент \<shadowCopyVerifyByTimeStamp></span><span class="sxs-lookup"><span data-stu-id="cb767-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="cb767-103">Указывает, использует ли теневое копирование поведение при запуске по умолчанию, представленное в .NET Framework 4, или возвращается к поведению при запуске более ранних версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb767-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="cb767-104">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="cb767-104">\<configuration> Element</span></span>  
<span data-ttu-id="cb767-105">\<Элемент > среды выполнения</span><span class="sxs-lookup"><span data-stu-id="cb767-105">\<runtime> Element</span></span>  
<span data-ttu-id="cb767-106">Элемент \<shadowCopyVerifyByTimeStamp></span><span class="sxs-lookup"><span data-stu-id="cb767-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb767-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb767-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb767-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb767-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cb767-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb767-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb767-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb767-110">Attributes</span></span>  
  
|<span data-ttu-id="cb767-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cb767-111">Attribute</span></span>|<span data-ttu-id="cb767-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cb767-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb767-113">enabled</span><span class="sxs-lookup"><span data-stu-id="cb767-113">enabled</span></span>|<span data-ttu-id="cb767-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="cb767-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cb767-115">Указывает, были ли домены приложений, использующие теневое копирование, сравниваются метки времени сборки при запуске, чтобы определить, обновлена ли сборка перед теневым копированием сборки.</span><span class="sxs-lookup"><span data-stu-id="cb767-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cb767-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="cb767-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="cb767-117">Значение</span><span class="sxs-lookup"><span data-stu-id="cb767-117">Value</span></span>|<span data-ttu-id="cb767-118">Описание</span><span class="sxs-lookup"><span data-stu-id="cb767-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb767-119">true</span><span class="sxs-lookup"><span data-stu-id="cb767-119">true</span></span>|<span data-ttu-id="cb767-120">При запуске копирует только сборки, которые были обновлены с момента последнего копирования в каталог теневых копий.</span><span class="sxs-lookup"><span data-stu-id="cb767-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="cb767-121">Это значение по умолчанию для .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cb767-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="cb767-122">false</span><span class="sxs-lookup"><span data-stu-id="cb767-122">false</span></span>|<span data-ttu-id="cb767-123">Восстанавливает поведение при запуске предыдущих версий .NET Framework, при запуске которого были скопированы все файлы.</span><span class="sxs-lookup"><span data-stu-id="cb767-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb767-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb767-124">Child Elements</span></span>  
 <span data-ttu-id="cb767-125">Нет.</span><span class="sxs-lookup"><span data-stu-id="cb767-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb767-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb767-126">Parent Elements</span></span>  
  
|<span data-ttu-id="cb767-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb767-127">Element</span></span>|<span data-ttu-id="cb767-128">Описание</span><span class="sxs-lookup"><span data-stu-id="cb767-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cb767-129">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb767-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cb767-130">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="cb767-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb767-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb767-131">Remarks</span></span>  
 <span data-ttu-id="cb767-132">Начиная с .NET Framework 4 сборки копируются только в том случае, если их метки времени указывают, что они изменились с момента последнего копирования в каталог теневых копий.</span><span class="sxs-lookup"><span data-stu-id="cb767-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="cb767-133">Это улучшает время запуска для многих приложений, использующих теневое копирование, как описано в разделе [теневое копирование сборок](../../../app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="cb767-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="cb767-134">Для приложений с большим процентом и высокой частотой обновления сборок это изменение в поведении может не быть выгодно.</span><span class="sxs-lookup"><span data-stu-id="cb767-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="cb767-135">В этом случае можно использовать этот элемент для восстановления поведения предыдущих версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb767-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb767-136">Пример</span><span class="sxs-lookup"><span data-stu-id="cb767-136">Example</span></span>  
 <span data-ttu-id="cb767-137">В следующем примере показано, как отключить поведение при запуске теневого копирования по умолчанию в .NET Framework 4 и вернуться к режиму запуска предыдущих версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb767-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb767-138">См. также</span><span class="sxs-lookup"><span data-stu-id="cb767-138">See also</span></span>

- [<span data-ttu-id="cb767-139">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="cb767-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cb767-140">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="cb767-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cb767-141">Теневое копирование сборок</span><span class="sxs-lookup"><span data-stu-id="cb767-141">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
