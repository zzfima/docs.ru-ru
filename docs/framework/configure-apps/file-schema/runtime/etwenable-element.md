---
title: Элемент <etwEnable>
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd6d6d9e192fdf43ba9436cda54920bdeba9ab64
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279179"
---
# <a name="etwenable-element"></a><span data-ttu-id="d3b28-102">\<etwEnable > элемент</span><span class="sxs-lookup"><span data-stu-id="d3b28-102">\<etwEnable> Element</span></span>
<span data-ttu-id="d3b28-103">Указывает, следует ли включить трассировку событий Windows для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d3b28-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="d3b28-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="d3b28-104">\<configuration> Element</span></span>  
<span data-ttu-id="d3b28-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="d3b28-105">\<runtime> Element</span></span>  
<span data-ttu-id="d3b28-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="d3b28-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b28-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3b28-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3b28-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d3b28-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d3b28-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d3b28-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3b28-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3b28-110">Attributes</span></span>  
  
|<span data-ttu-id="d3b28-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d3b28-111">Attribute</span></span>|<span data-ttu-id="d3b28-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d3b28-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3b28-113">enabled</span><span class="sxs-lookup"><span data-stu-id="d3b28-113">enabled</span></span>|<span data-ttu-id="d3b28-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d3b28-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="d3b28-115">Указывает, должна ли быть включена трассировка событий Windows.</span><span class="sxs-lookup"><span data-stu-id="d3b28-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d3b28-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="d3b28-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="d3b28-117">Значение</span><span class="sxs-lookup"><span data-stu-id="d3b28-117">Value</span></span>|<span data-ttu-id="d3b28-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d3b28-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d3b28-119">true</span><span class="sxs-lookup"><span data-stu-id="d3b28-119">true</span></span>|<span data-ttu-id="d3b28-120">Включение трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="d3b28-120">Enable ETW.</span></span> <span data-ttu-id="d3b28-121">Это значение по умолчанию для версий Windows, начиная с операционными системами Windows Vista и Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d3b28-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="d3b28-122">False</span><span class="sxs-lookup"><span data-stu-id="d3b28-122">false</span></span>|<span data-ttu-id="d3b28-123">Отключение трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="d3b28-123">Disable ETW.</span></span> <span data-ttu-id="d3b28-124">Это значение по умолчанию для более ранних версий Windows.</span><span class="sxs-lookup"><span data-stu-id="d3b28-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3b28-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d3b28-125">Child Elements</span></span>  
 <span data-ttu-id="d3b28-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d3b28-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3b28-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d3b28-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d3b28-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3b28-128">Element</span></span>|<span data-ttu-id="d3b28-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="d3b28-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d3b28-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3b28-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d3b28-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="d3b28-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3b28-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3b28-132">Remarks</span></span>  
 <span data-ttu-id="d3b28-133">Начиная с Windows Vista, ETW включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3b28-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="d3b28-134">Этот элемент используется для отключения трассировки событий Windows для приложения.</span><span class="sxs-lookup"><span data-stu-id="d3b28-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="d3b28-135">В более ранних версиях Windows этот элемент используется для включения трассировки событий Windows для приложения.</span><span class="sxs-lookup"><span data-stu-id="d3b28-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3b28-136">Трассировки событий Windows может быть включен или отключен глобально на сервере с помощью параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="d3b28-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="d3b28-137">См. в разделе [контроль ведения журнала .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="d3b28-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3b28-138">Пример</span><span class="sxs-lookup"><span data-stu-id="d3b28-138">Example</span></span>  
 <span data-ttu-id="d3b28-139">В следующем примере показано, как включить отслеживание ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="d3b28-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3b28-140">См. также</span><span class="sxs-lookup"><span data-stu-id="d3b28-140">See also</span></span>
- [<span data-ttu-id="d3b28-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d3b28-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d3b28-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d3b28-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d3b28-143">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d3b28-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
