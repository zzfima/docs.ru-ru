---
title: '&lt;UseSmallInternalThreadStacks&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed128cc2ddec3c599932cd5a82364d1cf6642cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505241"
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a><span data-ttu-id="e8136-102">&lt;UseSmallInternalThreadStacks&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="e8136-102">&lt;UseSmallInternalThreadStacks&gt; Element</span></span>
<span data-ttu-id="e8136-103">Запросы, что сокращает общеязыковой среды выполнения (CLR) используют путем указания явных размеров стека при создании определенных потоков, используемых для внутренних целей, вместо размер стека по умолчанию для этих потоков.</span><span class="sxs-lookup"><span data-stu-id="e8136-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="e8136-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="e8136-104">\<configuration> Element</span></span>  
<span data-ttu-id="e8136-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="e8136-105">\<runtime> Element</span></span>  
<span data-ttu-id="e8136-106">\<UseSmallInternalThreadStacks > элемент</span><span class="sxs-lookup"><span data-stu-id="e8136-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8136-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8136-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8136-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e8136-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e8136-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e8136-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8136-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e8136-110">Attributes</span></span>  
  
|<span data-ttu-id="e8136-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e8136-111">Attribute</span></span>|<span data-ttu-id="e8136-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e8136-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8136-113">enabled</span><span class="sxs-lookup"><span data-stu-id="e8136-113">enabled</span></span>|<span data-ttu-id="e8136-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e8136-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e8136-115">Признак запроса, CLR использования явных размеров стека вместо размер стека по умолчанию при создании определенных потоков, используемых для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="e8136-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="e8136-116">Явных размеров стека имеют меньший размер, чем размер стека по умолчанию 1 МБ.</span><span class="sxs-lookup"><span data-stu-id="e8136-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e8136-117">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="e8136-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="e8136-118">Значение</span><span class="sxs-lookup"><span data-stu-id="e8136-118">Value</span></span>|<span data-ttu-id="e8136-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="e8136-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e8136-120">true</span><span class="sxs-lookup"><span data-stu-id="e8136-120">true</span></span>|<span data-ttu-id="e8136-121">Запросите явных размеров стека.</span><span class="sxs-lookup"><span data-stu-id="e8136-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="e8136-122">False</span><span class="sxs-lookup"><span data-stu-id="e8136-122">false</span></span>|<span data-ttu-id="e8136-123">Используйте размер стека по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8136-123">Use the default stack size.</span></span> <span data-ttu-id="e8136-124">Это значение по умолчанию для [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8136-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8136-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e8136-125">Child Elements</span></span>  
 <span data-ttu-id="e8136-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e8136-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8136-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e8136-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e8136-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="e8136-128">Element</span></span>|<span data-ttu-id="e8136-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="e8136-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e8136-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8136-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e8136-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e8136-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8136-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8136-132">Remarks</span></span>  
 <span data-ttu-id="e8136-133">Этот элемент конфигурации используется для запроса Использование ограниченной виртуальной памяти в процессе, поскольку явные размеры потоков, которые среда CLR использует для своих внутренних потоков, если запрос выполняется, меньше, чем размер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8136-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8136-134">Этот элемент конфигурации — это запрос на CLR, а не является обязательным требованием.</span><span class="sxs-lookup"><span data-stu-id="e8136-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="e8136-135">В [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], запрос выполняется только для x86 архитектуры.</span><span class="sxs-lookup"><span data-stu-id="e8136-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="e8136-136">Этот элемент может полностью обрабатывается в будущих версиях среды CLR или заменены явных размеров стека, которые всегда используются для выбранного внутренних потоков.</span><span class="sxs-lookup"><span data-stu-id="e8136-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="e8136-137">Указание данного элемента конфигурации меняет надежность для меньшего использования виртуальной памяти, если среда CLR учитывает запрос, так как меньшие размеры стека могут сделать стек переполнения более вероятно.</span><span class="sxs-lookup"><span data-stu-id="e8136-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8136-138">Пример</span><span class="sxs-lookup"><span data-stu-id="e8136-138">Example</span></span>  
 <span data-ttu-id="e8136-139">Приведенный ниже показано, как для запроса, что CLR использования явных размеров стека для определенных потоков, используемых для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="e8136-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8136-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e8136-140">See also</span></span>
- [<span data-ttu-id="e8136-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e8136-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="e8136-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e8136-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
