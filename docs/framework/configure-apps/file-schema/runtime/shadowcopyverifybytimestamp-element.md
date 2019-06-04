---
title: Элемент <shadowCopyVerifyByTimestamp>
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4187d266d82783ebb72073c1da92faff95352884
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489376"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="de1fd-102">Элемент \<shadowCopyVerifyByTimeStamp></span><span class="sxs-lookup"><span data-stu-id="de1fd-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="de1fd-103">Указывает, использует ли теневое копирование поведение при запуске по умолчанию, представленные в .NET Framework 4, или возвращается к поведению более ранних версий платформы .NET Framework при запуске.</span><span class="sxs-lookup"><span data-stu-id="de1fd-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="de1fd-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="de1fd-104">\<configuration> Element</span></span>  
<span data-ttu-id="de1fd-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="de1fd-105">\<runtime> Element</span></span>  
<span data-ttu-id="de1fd-106">Элемент \<shadowCopyVerifyByTimeStamp></span><span class="sxs-lookup"><span data-stu-id="de1fd-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de1fd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de1fd-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de1fd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="de1fd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="de1fd-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="de1fd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de1fd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="de1fd-110">Attributes</span></span>  
  
|<span data-ttu-id="de1fd-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="de1fd-111">Attribute</span></span>|<span data-ttu-id="de1fd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="de1fd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de1fd-113">enabled</span><span class="sxs-lookup"><span data-stu-id="de1fd-113">enabled</span></span>|<span data-ttu-id="de1fd-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="de1fd-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="de1fd-115">Указывает, следует ли домены приложений, использующих теневое копирование сравнение отметки времени сборок при запуске, чтобы определить, обновлена ли сборки перед теневым копированием.</span><span class="sxs-lookup"><span data-stu-id="de1fd-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="de1fd-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="de1fd-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="de1fd-117">Значение</span><span class="sxs-lookup"><span data-stu-id="de1fd-117">Value</span></span>|<span data-ttu-id="de1fd-118">Описание</span><span class="sxs-lookup"><span data-stu-id="de1fd-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de1fd-119">true</span><span class="sxs-lookup"><span data-stu-id="de1fd-119">true</span></span>|<span data-ttu-id="de1fd-120">При запуске копируются только те сборки, которые были обновлены с момента последнего копирования в каталог теневого копирования.</span><span class="sxs-lookup"><span data-stu-id="de1fd-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="de1fd-121">Это значение по умолчанию для .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="de1fd-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="de1fd-122">False</span><span class="sxs-lookup"><span data-stu-id="de1fd-122">false</span></span>|<span data-ttu-id="de1fd-123">Возвращается поведение при запуске предыдущих версий платформы .NET Framework, в которых должен был быть скопируйте все файлы во время запуска.</span><span class="sxs-lookup"><span data-stu-id="de1fd-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de1fd-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="de1fd-124">Child Elements</span></span>  
 <span data-ttu-id="de1fd-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="de1fd-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de1fd-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="de1fd-126">Parent Elements</span></span>  
  
|<span data-ttu-id="de1fd-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="de1fd-127">Element</span></span>|<span data-ttu-id="de1fd-128">Описание</span><span class="sxs-lookup"><span data-stu-id="de1fd-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="de1fd-129">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de1fd-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="de1fd-130">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="de1fd-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de1fd-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="de1fd-131">Remarks</span></span>  
 <span data-ttu-id="de1fd-132">Начиная с .NET Framework 4, копируются сборки только в том случае, если их отметки времени показывают, что они были изменены с момента последнего копирования в каталог теневого копирования.</span><span class="sxs-lookup"><span data-stu-id="de1fd-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="de1fd-133">Это сокращает время запуска для многих приложений, использующих теневое копирование, как описано в разделе [теневое копирование сборок](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="de1fd-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="de1fd-134">Для приложений с большим процентом и высокой частотой обновления сборок это изменение в поведении может не быть выгодно.</span><span class="sxs-lookup"><span data-stu-id="de1fd-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="de1fd-135">В этом случае можно использовать этот элемент для восстановления поведения предыдущих версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de1fd-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de1fd-136">Пример</span><span class="sxs-lookup"><span data-stu-id="de1fd-136">Example</span></span>  
 <span data-ttu-id="de1fd-137">Приведенный ниже показано, как отключить режим запуска по умолчанию теневое копирование в .NET Framework 4, и вернуться к поведению при запуске предыдущих версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de1fd-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de1fd-138">См. также</span><span class="sxs-lookup"><span data-stu-id="de1fd-138">See also</span></span>

- [<span data-ttu-id="de1fd-139">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="de1fd-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="de1fd-140">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="de1fd-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="de1fd-141">Теневое копирование сборок</span><span class="sxs-lookup"><span data-stu-id="de1fd-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
