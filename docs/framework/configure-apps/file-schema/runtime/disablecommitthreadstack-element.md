---
title: "&lt;disableCommitThreadStack&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a7961c62d46a10767b119c4c55a4b620e1ad782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdisablecommitthreadstackgt-element"></a><span data-ttu-id="bb2d0-102">&lt;disableCommitThreadStack&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="bb2d0-102">&lt;disableCommitThreadStack&gt; Element</span></span>
<span data-ttu-id="bb2d0-103">Указывает, фиксируется ли весь стек потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="bb2d0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb2d0-104">\<configuration></span></span>  
<span data-ttu-id="bb2d0-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="bb2d0-105">\<runtime></span></span>  
<span data-ttu-id="bb2d0-106">\<disableCommitThreadStack ></span><span class="sxs-lookup"><span data-stu-id="bb2d0-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb2d0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb2d0-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb2d0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb2d0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bb2d0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb2d0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb2d0-110">Attributes</span></span>  
  
|<span data-ttu-id="bb2d0-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bb2d0-111">Attribute</span></span>|<span data-ttu-id="bb2d0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bb2d0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb2d0-113">enabled</span><span class="sxs-lookup"><span data-stu-id="bb2d0-113">enabled</span></span>|<span data-ttu-id="bb2d0-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb2d0-115">Указывает, отключена ли фиксация всего стека потоков при запуске потока (режим по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bb2d0-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bb2d0-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="bb2d0-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="bb2d0-117">Значение</span><span class="sxs-lookup"><span data-stu-id="bb2d0-117">Value</span></span>|<span data-ttu-id="bb2d0-118">Описание</span><span class="sxs-lookup"><span data-stu-id="bb2d0-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb2d0-119">0</span><span class="sxs-lookup"><span data-stu-id="bb2d0-119">0</span></span>|<span data-ttu-id="bb2d0-120">Не отключать для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="bb2d0-121">1</span><span class="sxs-lookup"><span data-stu-id="bb2d0-121">1</span></span>|<span data-ttu-id="bb2d0-122">Отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb2d0-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb2d0-123">Child Elements</span></span>  
 <span data-ttu-id="bb2d0-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb2d0-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb2d0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bb2d0-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb2d0-126">Element</span></span>|<span data-ttu-id="bb2d0-127">Описание</span><span class="sxs-lookup"><span data-stu-id="bb2d0-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb2d0-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb2d0-128">The root element in every configuration file used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
|`runtime`|<span data-ttu-id="bb2d0-129">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb2d0-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb2d0-130">Remarks</span></span>  
 <span data-ttu-id="bb2d0-131">Режим по умолчанию для среды CLR заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="bb2d0-132">Если на сервере с ограниченным объемом памяти необходимо создать большое число потоков и большинство из этих потоков будут использовать очень небольшое пространство стека, сервер может работать лучше, если среда не фиксирует весь стек потоков сразу после запуска потока.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb2d0-133">Неуправляемые узлы могут использовать флаг запуска `STARTUP_DISABLE_COMMITTHREADSTACK` в перечислении [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) для достижения такого же результата.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb2d0-134">Пример</span><span class="sxs-lookup"><span data-stu-id="bb2d0-134">Example</span></span>  
 <span data-ttu-id="bb2d0-135">В следующем примере показано, как отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="bb2d0-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb2d0-136">См. также</span><span class="sxs-lookup"><span data-stu-id="bb2d0-136">See Also</span></span>  
 [<span data-ttu-id="bb2d0-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="bb2d0-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="bb2d0-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="bb2d0-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
