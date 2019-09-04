---
title: Элемент <UseSmallInternalThreadStacks>
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515ea076c5eaead50b41e45e415725d0439914bc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252211"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="44e55-102">\<Элемент > Усесмаллинтерналсреадстаккс</span><span class="sxs-lookup"><span data-stu-id="44e55-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="44e55-103">Запрашивает уменьшение использования памяти средой CLR, указывая явные размеры стека при создании определенных потоков, используемых внутренним образом, вместо использования размера стека по умолчанию для этих потоков.</span><span class="sxs-lookup"><span data-stu-id="44e55-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
<span data-ttu-id="44e55-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44e55-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44e55-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="44e55-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="44e55-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseSmallInternalThreadStacks>**</span><span class="sxs-lookup"><span data-stu-id="44e55-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e55-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44e55-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44e55-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="44e55-108">Attributes and Elements</span></span>  
 <span data-ttu-id="44e55-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="44e55-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44e55-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="44e55-110">Attributes</span></span>  
  
|<span data-ttu-id="44e55-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="44e55-111">Attribute</span></span>|<span data-ttu-id="44e55-112">Описание</span><span class="sxs-lookup"><span data-stu-id="44e55-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44e55-113">enabled</span><span class="sxs-lookup"><span data-stu-id="44e55-113">enabled</span></span>|<span data-ttu-id="44e55-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="44e55-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="44e55-115">Указывает, следует ли запрашивать, что среда CLR использует явные размеры стека вместо размера стека по умолчанию при создании определенных потоков, используемых внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="44e55-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="44e55-116">Явные размеры стека меньше, чем размер стека по умолчанию (1 МБ).</span><span class="sxs-lookup"><span data-stu-id="44e55-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="44e55-117">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="44e55-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="44e55-118">Значение</span><span class="sxs-lookup"><span data-stu-id="44e55-118">Value</span></span>|<span data-ttu-id="44e55-119">Описание</span><span class="sxs-lookup"><span data-stu-id="44e55-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44e55-120">true</span><span class="sxs-lookup"><span data-stu-id="44e55-120">true</span></span>|<span data-ttu-id="44e55-121">Запрос явных размеров стека.</span><span class="sxs-lookup"><span data-stu-id="44e55-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="44e55-122">false</span><span class="sxs-lookup"><span data-stu-id="44e55-122">false</span></span>|<span data-ttu-id="44e55-123">Используйте размер стека по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44e55-123">Use the default stack size.</span></span> <span data-ttu-id="44e55-124">Это значение по умолчанию для .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="44e55-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44e55-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="44e55-125">Child Elements</span></span>  
 <span data-ttu-id="44e55-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="44e55-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44e55-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="44e55-127">Parent Elements</span></span>  
  
|<span data-ttu-id="44e55-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="44e55-128">Element</span></span>|<span data-ttu-id="44e55-129">Описание</span><span class="sxs-lookup"><span data-stu-id="44e55-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44e55-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44e55-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="44e55-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="44e55-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44e55-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="44e55-132">Remarks</span></span>  
 <span data-ttu-id="44e55-133">Этот элемент конфигурации используется для запроса уменьшенного использования виртуальной памяти в процессе, поскольку явные размеры потоков, используемые средой CLR для внутренних потоков, если запрос обрабатывается, меньше размера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44e55-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="44e55-134">Этот элемент конфигурации является запросом к CLR, а не абсолютному требованию.</span><span class="sxs-lookup"><span data-stu-id="44e55-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="44e55-135">В .NET Framework 4 запрос учитывается только для архитектуры x86.</span><span class="sxs-lookup"><span data-stu-id="44e55-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="44e55-136">Этот элемент может игнорироваться полностью в будущих версиях среды CLR или заменен на явные размеры стека, которые всегда используются для выбранных внутренних потоков.</span><span class="sxs-lookup"><span data-stu-id="44e55-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="44e55-137">Указание этого элемента конфигурации меняет надежность для использования меньшего объема виртуальной памяти, если среда CLR учитывает запрос, так как меньшие размеры стека потенциально могут привести к большей вероятности переполняет стек.</span><span class="sxs-lookup"><span data-stu-id="44e55-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44e55-138">Пример</span><span class="sxs-lookup"><span data-stu-id="44e55-138">Example</span></span>  
 <span data-ttu-id="44e55-139">В следующем примере показано, как запросить, чтобы среда CLR использовала явные размеры стека для определенных потоков, которые он использует для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="44e55-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44e55-140">См. также</span><span class="sxs-lookup"><span data-stu-id="44e55-140">See also</span></span>

- [<span data-ttu-id="44e55-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="44e55-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="44e55-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="44e55-142">Configuration File Schema</span></span>](../index.md)
