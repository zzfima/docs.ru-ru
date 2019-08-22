---
title: Элемент <etwEnable>
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f24e9a06137744dbc97d5f34cda7ad6eab873700
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663736"
---
# <a name="etwenable-element"></a><span data-ttu-id="e2e38-102">\<Элемент > Етвенабле</span><span class="sxs-lookup"><span data-stu-id="e2e38-102">\<etwEnable> Element</span></span>
<span data-ttu-id="e2e38-103">Указывает, следует ли включить трассировку событий Windows для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e2e38-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="e2e38-104">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="e2e38-104">\<configuration> Element</span></span>  
<span data-ttu-id="e2e38-105">\<Элемент > среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e2e38-105">\<runtime> Element</span></span>  
<span data-ttu-id="e2e38-106">\<Етвенаблед ></span><span class="sxs-lookup"><span data-stu-id="e2e38-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e38-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2e38-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2e38-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e2e38-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e2e38-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e2e38-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2e38-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e2e38-110">Attributes</span></span>  
  
|<span data-ttu-id="e2e38-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e2e38-111">Attribute</span></span>|<span data-ttu-id="e2e38-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e2e38-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2e38-113">enabled</span><span class="sxs-lookup"><span data-stu-id="e2e38-113">enabled</span></span>|<span data-ttu-id="e2e38-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e2e38-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e2e38-115">Указывает, включена ли трассировка событий Windows.</span><span class="sxs-lookup"><span data-stu-id="e2e38-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e2e38-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="e2e38-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="e2e38-117">Значение</span><span class="sxs-lookup"><span data-stu-id="e2e38-117">Value</span></span>|<span data-ttu-id="e2e38-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e2e38-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e2e38-119">true</span><span class="sxs-lookup"><span data-stu-id="e2e38-119">true</span></span>|<span data-ttu-id="e2e38-120">Включите ETW.</span><span class="sxs-lookup"><span data-stu-id="e2e38-120">Enable ETW.</span></span> <span data-ttu-id="e2e38-121">Это значение по умолчанию для версий Windows, начинающихся с операционных систем Windows Vista и Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="e2e38-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="e2e38-122">false</span><span class="sxs-lookup"><span data-stu-id="e2e38-122">false</span></span>|<span data-ttu-id="e2e38-123">Отключите трассировку событий Windows.</span><span class="sxs-lookup"><span data-stu-id="e2e38-123">Disable ETW.</span></span> <span data-ttu-id="e2e38-124">Это значение по умолчанию для более ранних версий Windows.</span><span class="sxs-lookup"><span data-stu-id="e2e38-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2e38-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e2e38-125">Child Elements</span></span>  
 <span data-ttu-id="e2e38-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="e2e38-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2e38-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e2e38-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e2e38-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2e38-128">Element</span></span>|<span data-ttu-id="e2e38-129">Описание</span><span class="sxs-lookup"><span data-stu-id="e2e38-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e2e38-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e2e38-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e2e38-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e2e38-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2e38-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2e38-132">Remarks</span></span>  
 <span data-ttu-id="e2e38-133">Начиная с Windows Vista трассировка событий Windows включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e2e38-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="e2e38-134">Используйте этот элемент, чтобы отключить ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="e2e38-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="e2e38-135">В более ранних версиях Windows этот элемент используется для включения ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="e2e38-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2e38-136">Трассировку событий Windows можно включить или отключить глобально на сервере с помощью параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="e2e38-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="e2e38-137">См. раздел [Управление ведением журнала .NET Framework](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="e2e38-137">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2e38-138">Пример</span><span class="sxs-lookup"><span data-stu-id="e2e38-138">Example</span></span>  
 <span data-ttu-id="e2e38-139">В следующем примере показано, как включить трассировку ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="e2e38-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2e38-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e2e38-140">See also</span></span>

- [<span data-ttu-id="e2e38-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e2e38-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e2e38-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e2e38-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e2e38-143">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e2e38-143">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
