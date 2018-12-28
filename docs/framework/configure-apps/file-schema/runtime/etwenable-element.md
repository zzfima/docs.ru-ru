---
title: '&lt;etwEnable&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6ea2f8a32a18dfce6be54ce52ce8fef4abf92ce
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610779"
---
# <a name="ltetwenablegt-element"></a><span data-ttu-id="0b154-102">&lt;etwEnable&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="0b154-102">&lt;etwEnable&gt; Element</span></span>
<span data-ttu-id="0b154-103">Указывает, следует ли включить трассировку событий Windows для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0b154-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="0b154-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="0b154-104">\<configuration> Element</span></span>  
<span data-ttu-id="0b154-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="0b154-105">\<runtime> Element</span></span>  
<span data-ttu-id="0b154-106">\<etwEnabled ></span><span class="sxs-lookup"><span data-stu-id="0b154-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b154-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b154-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b154-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b154-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0b154-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b154-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b154-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b154-110">Attributes</span></span>  
  
|<span data-ttu-id="0b154-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0b154-111">Attribute</span></span>|<span data-ttu-id="0b154-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0b154-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b154-113">enabled</span><span class="sxs-lookup"><span data-stu-id="0b154-113">enabled</span></span>|<span data-ttu-id="0b154-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0b154-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="0b154-115">Указывает, должна ли быть включена трассировка событий Windows.</span><span class="sxs-lookup"><span data-stu-id="0b154-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0b154-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="0b154-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="0b154-117">Значение</span><span class="sxs-lookup"><span data-stu-id="0b154-117">Value</span></span>|<span data-ttu-id="0b154-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b154-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b154-119">true</span><span class="sxs-lookup"><span data-stu-id="0b154-119">true</span></span>|<span data-ttu-id="0b154-120">Включение трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="0b154-120">Enable ETW.</span></span> <span data-ttu-id="0b154-121">Это значение по умолчанию для версий Windows, начиная с операционными системами Windows Vista и Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="0b154-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="0b154-122">False</span><span class="sxs-lookup"><span data-stu-id="0b154-122">false</span></span>|<span data-ttu-id="0b154-123">Отключение трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="0b154-123">Disable ETW.</span></span> <span data-ttu-id="0b154-124">Это значение по умолчанию для более ранних версий Windows.</span><span class="sxs-lookup"><span data-stu-id="0b154-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b154-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b154-125">Child Elements</span></span>  
 <span data-ttu-id="0b154-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0b154-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b154-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b154-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0b154-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b154-128">Element</span></span>|<span data-ttu-id="0b154-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b154-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0b154-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b154-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0b154-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="0b154-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b154-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b154-132">Remarks</span></span>  
 <span data-ttu-id="0b154-133">Начиная с Windows Vista, ETW включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b154-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="0b154-134">Этот элемент используется для отключения трассировки событий Windows для приложения.</span><span class="sxs-lookup"><span data-stu-id="0b154-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="0b154-135">В более ранних версиях Windows этот элемент используется для включения трассировки событий Windows для приложения.</span><span class="sxs-lookup"><span data-stu-id="0b154-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b154-136">Трассировки событий Windows может быть включен или отключен глобально на сервере с помощью параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="0b154-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="0b154-137">См. в разделе [контроль ведения журнала .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="0b154-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b154-138">Пример</span><span class="sxs-lookup"><span data-stu-id="0b154-138">Example</span></span>  
 <span data-ttu-id="0b154-139">В следующем примере показано, как включить отслеживание ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="0b154-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b154-140">См. также</span><span class="sxs-lookup"><span data-stu-id="0b154-140">See Also</span></span>  
- [<span data-ttu-id="0b154-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0b154-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="0b154-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="0b154-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="0b154-143">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0b154-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
