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
ms.openlocfilehash: 8aefb8a20d6a95c5b8062d0c03dcb28a3557ca3d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117476"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="b81cb-102">\<Дисаблекоммитсреадстакк > элемент</span><span class="sxs-lookup"><span data-stu-id="b81cb-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="b81cb-103">Указывает, фиксируется ли весь стек потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="b81cb-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
<span data-ttu-id="b81cb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b81cb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b81cb-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="b81cb-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b81cb-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<дисаблекоммитсреадстакк >**</span><span class="sxs-lookup"><span data-stu-id="b81cb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b81cb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b81cb-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b81cb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b81cb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b81cb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b81cb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b81cb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b81cb-110">Attributes</span></span>  
  
|<span data-ttu-id="b81cb-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b81cb-111">Attribute</span></span>|<span data-ttu-id="b81cb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b81cb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b81cb-113">enabled</span><span class="sxs-lookup"><span data-stu-id="b81cb-113">enabled</span></span>|<span data-ttu-id="b81cb-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b81cb-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="b81cb-115">Указывает, отключена ли фиксация всего стека потоков при запуске потока (режим по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b81cb-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b81cb-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="b81cb-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="b81cb-117">значения</span><span class="sxs-lookup"><span data-stu-id="b81cb-117">Value</span></span>|<span data-ttu-id="b81cb-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b81cb-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b81cb-119">0</span><span class="sxs-lookup"><span data-stu-id="b81cb-119">0</span></span>|<span data-ttu-id="b81cb-120">Не отключать для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="b81cb-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="b81cb-121">1</span><span class="sxs-lookup"><span data-stu-id="b81cb-121">1</span></span>|<span data-ttu-id="b81cb-122">Отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="b81cb-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b81cb-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b81cb-123">Child Elements</span></span>  
 <span data-ttu-id="b81cb-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b81cb-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b81cb-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b81cb-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b81cb-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="b81cb-126">Element</span></span>|<span data-ttu-id="b81cb-127">Описание</span><span class="sxs-lookup"><span data-stu-id="b81cb-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b81cb-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b81cb-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b81cb-129">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="b81cb-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b81cb-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="b81cb-130">Remarks</span></span>  
 <span data-ttu-id="b81cb-131">Режим по умолчанию для среды CLR заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="b81cb-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="b81cb-132">Если на сервере с ограниченным объемом памяти необходимо создать большое число потоков и большинство из этих потоков будут использовать очень небольшое пространство стека, сервер может работать лучше, если среда не фиксирует весь стек потоков сразу после запуска потока.</span><span class="sxs-lookup"><span data-stu-id="b81cb-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b81cb-133">Неуправляемые узлы могут использовать флаг запуска `STARTUP_DISABLE_COMMITTHREADSTACK` в перечислении [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) для достижения такого же результата.</span><span class="sxs-lookup"><span data-stu-id="b81cb-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b81cb-134">Пример</span><span class="sxs-lookup"><span data-stu-id="b81cb-134">Example</span></span>  
 <span data-ttu-id="b81cb-135">В следующем примере показано, как отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="b81cb-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b81cb-136">См. также</span><span class="sxs-lookup"><span data-stu-id="b81cb-136">See also</span></span>

- [<span data-ttu-id="b81cb-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="b81cb-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b81cb-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b81cb-138">Configuration File Schema</span></span>](../index.md)
