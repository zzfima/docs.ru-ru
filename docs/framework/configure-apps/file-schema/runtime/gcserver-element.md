---
title: '&lt;gcServer&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bfe0db3d6fcbdbbcfb90ff488ab19cdbfaab75e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216149"
---
# <a name="ltgcservergt-element"></a><span data-ttu-id="70752-102">&lt;gcServer&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="70752-102">&lt;gcServer&gt; Element</span></span>
<span data-ttu-id="70752-103">Указывает, выполняет ли среда CLR сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="70752-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
 <span data-ttu-id="70752-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="70752-104">\<configuration></span></span>  
<span data-ttu-id="70752-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="70752-105">\<runtime></span></span>  
<span data-ttu-id="70752-106">\<gcServer ></span><span class="sxs-lookup"><span data-stu-id="70752-106">\<gcServer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70752-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70752-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70752-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="70752-108">Attributes and Elements</span></span>  
 <span data-ttu-id="70752-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="70752-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70752-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70752-110">Attributes</span></span>  
  
|<span data-ttu-id="70752-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="70752-111">Attribute</span></span>|<span data-ttu-id="70752-112">Описание</span><span class="sxs-lookup"><span data-stu-id="70752-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="70752-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="70752-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="70752-114">Указывает, выполняет ли среда выполнения сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="70752-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="70752-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="70752-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="70752-116">Значение</span><span class="sxs-lookup"><span data-stu-id="70752-116">Value</span></span>|<span data-ttu-id="70752-117">Описание</span><span class="sxs-lookup"><span data-stu-id="70752-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="70752-118">Не выполняет сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="70752-118">Does not run server garbage collection.</span></span> <span data-ttu-id="70752-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70752-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="70752-120">Выполняет сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="70752-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70752-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70752-121">Child Elements</span></span>  
 <span data-ttu-id="70752-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="70752-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70752-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70752-123">Parent Elements</span></span>  
  
|<span data-ttu-id="70752-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="70752-124">Element</span></span>|<span data-ttu-id="70752-125">Описание</span><span class="sxs-lookup"><span data-stu-id="70752-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="70752-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70752-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="70752-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="70752-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70752-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="70752-128">Remarks</span></span>  
 <span data-ttu-id="70752-129">Среда CLR поддерживает два типа сборки мусора: сборку мусора рабочей станции, которая доступна во всех системах, и сборку мусора сервера, которая доступна в многопроцессорных системах.</span><span class="sxs-lookup"><span data-stu-id="70752-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="70752-130">Для управления типом сборки мусора среды CLR можно использовать элемент `<gcServer>`.</span><span class="sxs-lookup"><span data-stu-id="70752-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="70752-131">Используйте свойство <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>, чтобы определить, включена ли сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="70752-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="70752-132">Для однопроцессорных компьютеров сборка мусора рабочей станции по умолчанию должна быть самым быстрым вариантом.</span><span class="sxs-lookup"><span data-stu-id="70752-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="70752-133">Для двухпроцессорных компьютеров можно использовать сборку мусора как рабочей станции, так и сервера.</span><span class="sxs-lookup"><span data-stu-id="70752-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="70752-134">Сборка мусора сервера должно быть самым быстрым вариантом при наличии более двух процессоров.</span><span class="sxs-lookup"><span data-stu-id="70752-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="70752-135">Этот элемент может использоваться только в файле конфигурации приложения; в файле конфигурации компьютера он игнорируется.</span><span class="sxs-lookup"><span data-stu-id="70752-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70752-136">В платформе .NET Framework версии 4 и более ранних версиях параллельная сборка мусора недоступна, если включена серверная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="70752-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="70752-137">Начиная с версии [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] сборка мусора сервера является параллельной.</span><span class="sxs-lookup"><span data-stu-id="70752-137">Starting with the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], server garbage collection is concurrent.</span></span> <span data-ttu-id="70752-138">Чтобы использовать непараллельной серверной сборки мусора, задайте `<gcServer>` элемент `true` и [ \<gcConcurrent > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) для `false`.</span><span class="sxs-lookup"><span data-stu-id="70752-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70752-139">Пример</span><span class="sxs-lookup"><span data-stu-id="70752-139">Example</span></span>  
 <span data-ttu-id="70752-140">В следующем примере включается параллельная сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="70752-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70752-141">См. также</span><span class="sxs-lookup"><span data-stu-id="70752-141">See Also</span></span>  
 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="70752-142">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="70752-142">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="70752-143">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="70752-143">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="70752-144">Практическое: отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="70752-144">How to: Disable Concurrent Garbage Collection</span></span>](https://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)
