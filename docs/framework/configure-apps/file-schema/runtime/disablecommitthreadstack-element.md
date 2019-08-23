---
title: Элемент <disableCommitThreadStack>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3071b25392048161ebb40c39842f5da0dce3475
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920833"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="252d3-102">\<Элемент > Дисаблекоммитсреадстакк</span><span class="sxs-lookup"><span data-stu-id="252d3-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="252d3-103">Указывает, фиксируется ли весь стек потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="252d3-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="252d3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="252d3-104">\<configuration></span></span>  
<span data-ttu-id="252d3-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="252d3-105">\<runtime></span></span>  
<span data-ttu-id="252d3-106">\<Дисаблекоммитсреадстакк ></span><span class="sxs-lookup"><span data-stu-id="252d3-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="252d3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="252d3-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="252d3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="252d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="252d3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="252d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="252d3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="252d3-110">Attributes</span></span>  
  
|<span data-ttu-id="252d3-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="252d3-111">Attribute</span></span>|<span data-ttu-id="252d3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="252d3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="252d3-113">enabled</span><span class="sxs-lookup"><span data-stu-id="252d3-113">enabled</span></span>|<span data-ttu-id="252d3-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="252d3-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="252d3-115">Указывает, отключена ли фиксация всего стека потоков при запуске потока (режим по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="252d3-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="252d3-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="252d3-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="252d3-117">Значение</span><span class="sxs-lookup"><span data-stu-id="252d3-117">Value</span></span>|<span data-ttu-id="252d3-118">Описание</span><span class="sxs-lookup"><span data-stu-id="252d3-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="252d3-119">0</span><span class="sxs-lookup"><span data-stu-id="252d3-119">0</span></span>|<span data-ttu-id="252d3-120">Не отключать для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="252d3-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="252d3-121">1</span><span class="sxs-lookup"><span data-stu-id="252d3-121">1</span></span>|<span data-ttu-id="252d3-122">Отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="252d3-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="252d3-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="252d3-123">Child Elements</span></span>  
 <span data-ttu-id="252d3-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="252d3-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="252d3-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="252d3-125">Parent Elements</span></span>  
  
|<span data-ttu-id="252d3-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="252d3-126">Element</span></span>|<span data-ttu-id="252d3-127">Описание</span><span class="sxs-lookup"><span data-stu-id="252d3-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="252d3-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="252d3-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="252d3-129">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="252d3-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="252d3-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="252d3-130">Remarks</span></span>  
 <span data-ttu-id="252d3-131">Режим по умолчанию для среды CLR заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="252d3-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="252d3-132">Если на сервере с ограниченным объемом памяти необходимо создать большое число потоков и большинство из этих потоков будут использовать очень небольшое пространство стека, сервер может работать лучше, если среда не фиксирует весь стек потоков сразу после запуска потока.</span><span class="sxs-lookup"><span data-stu-id="252d3-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="252d3-133">Неуправляемые узлы могут использовать флаг запуска `STARTUP_DISABLE_COMMITTHREADSTACK` в перечислении [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) для достижения такого же результата.</span><span class="sxs-lookup"><span data-stu-id="252d3-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="252d3-134">Пример</span><span class="sxs-lookup"><span data-stu-id="252d3-134">Example</span></span>  
 <span data-ttu-id="252d3-135">В следующем примере показано, как отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="252d3-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="252d3-136">См. также</span><span class="sxs-lookup"><span data-stu-id="252d3-136">See also</span></span>

- [<span data-ttu-id="252d3-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="252d3-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="252d3-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="252d3-138">Configuration File Schema</span></span>](../index.md)
