---
title: '&lt;NetFx40_PInvokeStackResilience&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cfd8c971edd4537de6e073c49f128f86eb8a042
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a><span data-ttu-id="836d1-102">&lt;NetFx40_PInvokeStackResilience&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="836d1-102">&lt;NetFx40_PInvokeStackResilience&gt; Element</span></span>
<span data-ttu-id="836d1-103">Указывает, исправляет ли автоматически среда выполнения неправильные объявления вызова неуправляемого кода во время выполнения за счет скорости перехода между управляемыми и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="836d1-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="836d1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="836d1-104">\<configuration></span></span>  
<span data-ttu-id="836d1-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="836d1-105">\<runtime></span></span>  
<span data-ttu-id="836d1-106"><NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="836d1-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="836d1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="836d1-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="836d1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="836d1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="836d1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="836d1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="836d1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="836d1-110">Attributes</span></span>  
  
|<span data-ttu-id="836d1-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="836d1-111">Attribute</span></span>|<span data-ttu-id="836d1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="836d1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="836d1-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="836d1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="836d1-114">Указывает, будет ли среда выполнения определять неверные объявления вызова неуправляемого кода и автоматически исправлять стек во время выполнения на 32-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="836d1-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="836d1-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="836d1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="836d1-116">Значение</span><span class="sxs-lookup"><span data-stu-id="836d1-116">Value</span></span>|<span data-ttu-id="836d1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="836d1-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="836d1-118">Среда выполнения использует быстрее архитектуру, представленные в маршалинга взаимодействия [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], которого не удается обнаружить и исправить неверные неуправляемого объявления.</span><span class="sxs-lookup"><span data-stu-id="836d1-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="836d1-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="836d1-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="836d1-120">Среда выполнения использует медленнее переходы, которые обнаруживают и исправляют неверные объявления вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="836d1-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="836d1-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="836d1-121">Child Elements</span></span>  
 <span data-ttu-id="836d1-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="836d1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="836d1-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="836d1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="836d1-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="836d1-124">Element</span></span>|<span data-ttu-id="836d1-125">Описание</span><span class="sxs-lookup"><span data-stu-id="836d1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="836d1-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="836d1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="836d1-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="836d1-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="836d1-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="836d1-128">Remarks</span></span>  
 <span data-ttu-id="836d1-129">Этот элемент позволяет быстрее реализовывать маршалинг взаимодействия для вызова неуправляемого кода во время выполнения устойчивость к неверным.</span><span class="sxs-lookup"><span data-stu-id="836d1-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="836d1-130">Начиная с [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], упрощенную архитектуру маршалинга взаимодействия обеспечивает значительное улучшение производительности для переходов из управляемого кода в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="836d1-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="836d1-131">В более ранних версиях платформы .NET Framework маршалинга обнаруживал неверные платформы неуправляемого кода на 32-разрядных платформах и автоматически исправлял стек.</span><span class="sxs-lookup"><span data-stu-id="836d1-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="836d1-132">Новая архитектура маршалинга устраняет этот шаг.</span><span class="sxs-lookup"><span data-stu-id="836d1-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="836d1-133">В результате переходы являются очень быстрыми, но неверные неуправляемого объявления могут привести к сбою программы.</span><span class="sxs-lookup"><span data-stu-id="836d1-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="836d1-134">Чтобы облегчить обнаружить неправильные объявления во время разработки были улучшены функции отладки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="836d1-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="836d1-135">[PInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) помощник по отладке управляемого (кода MDA) уведомляет о неправильном объявления вызова неуправляемого кода при запуске приложения с подключенным отладчиком.</span><span class="sxs-lookup"><span data-stu-id="836d1-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="836d1-136">Чтобы разрешить ситуации, где приложение использует компоненты, что невозможно перекомпилировать и, имеют неверные объявления вызова платформы, можно использовать `NetFx40_PInvokeStackResilience` элемент.</span><span class="sxs-lookup"><span data-stu-id="836d1-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="836d1-137">Добавление этого элемента в файле конфигурации приложения с `enabled="1"` переводит в режим совместимости с поведением более ранних версий платформы .NET Framework, за счет замедления переходов.</span><span class="sxs-lookup"><span data-stu-id="836d1-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="836d1-138">Сборки, которые были скомпилированы для более ранних версий платформы .NET Framework, автоматически переводятся в этот режим совместимости и не нуждаются в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="836d1-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="836d1-139">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="836d1-139">Configuration File</span></span>  
 <span data-ttu-id="836d1-140">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="836d1-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="836d1-141">Пример</span><span class="sxs-lookup"><span data-stu-id="836d1-141">Example</span></span>  
 <span data-ttu-id="836d1-142">В следующем примере показан способ, чтобы обеспечить дополнительную устойчивость к неправильным объявления платформенного вызова для приложения, за счет скорости переходы между управляемого и неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="836d1-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="836d1-143">См. также</span><span class="sxs-lookup"><span data-stu-id="836d1-143">See Also</span></span>  
 [<span data-ttu-id="836d1-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="836d1-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="836d1-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="836d1-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="836d1-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="836d1-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
