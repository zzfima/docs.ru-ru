---
title: Элемент <NetFx40_PInvokeStackResilience>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116162"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="f1f90-102">\<NetFx40_PInvokeStackResilience > элемент</span><span class="sxs-lookup"><span data-stu-id="f1f90-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="f1f90-103">Указывает, исправляет ли автоматически среда выполнения неправильные объявления вызова неуправляемого кода во время выполнения за счет скорости перехода между управляемыми и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="f1f90-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

<span data-ttu-id="f1f90-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f1f90-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f1f90-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="f1f90-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f1f90-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NetFx40_PInvokeStackResilience >**</span><span class="sxs-lookup"><span data-stu-id="f1f90-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f1f90-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1f90-107">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f1f90-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f1f90-108">Attributes and Elements</span></span>

<span data-ttu-id="f1f90-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f1f90-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f1f90-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f1f90-110">Attributes</span></span>

|<span data-ttu-id="f1f90-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f1f90-111">Attribute</span></span>|<span data-ttu-id="f1f90-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f1f90-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f1f90-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f1f90-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f1f90-114">Указывает, обнаруживает ли среда выполнения неверные объявления вызова неуправляемого кода и автоматически исправляет стек во время выполнения на 32-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="f1f90-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f1f90-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="f1f90-115">enabled Attribute</span></span>

|<span data-ttu-id="f1f90-116">значения</span><span class="sxs-lookup"><span data-stu-id="f1f90-116">Value</span></span>|<span data-ttu-id="f1f90-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f1f90-117">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="f1f90-118">Среда выполнения использует более быструю архитектуру маршалинга взаимодействия, представленную в .NET Framework 4, которая не обнаруживает и не устраняет неверные объявления вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f1f90-118">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="f1f90-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1f90-119">This is the default.</span></span>|
|`1`|<span data-ttu-id="f1f90-120">Среда выполнения использует медленные переходы, которые обнаруживают и исправляют неверные объявления вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f1f90-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f1f90-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f1f90-121">Child Elements</span></span>

<span data-ttu-id="f1f90-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f1f90-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f1f90-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f1f90-123">Parent Elements</span></span>

|<span data-ttu-id="f1f90-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="f1f90-124">Element</span></span>|<span data-ttu-id="f1f90-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f1f90-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f1f90-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f1f90-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f1f90-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f1f90-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f1f90-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="f1f90-128">Remarks</span></span>

<span data-ttu-id="f1f90-129">Этот элемент позволяет ускорить маршалинг взаимодействия для устойчивости во время выполнения по неправильным объявлениям вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f1f90-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="f1f90-130">Начиная с .NET Framework 4, оптимизированная архитектура маршалинга взаимодействия обеспечивает значительное повышение производительности при переходе от управляемого кода к неуправляемому.</span><span class="sxs-lookup"><span data-stu-id="f1f90-130">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="f1f90-131">В более ранних версиях .NET Framework слой упаковки обнаружил неверные объявления вызова неуправляемого кода на 32-разрядных платформах и автоматически устранил стек.</span><span class="sxs-lookup"><span data-stu-id="f1f90-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="f1f90-132">Новая архитектура маршалирования устраняет этот шаг.</span><span class="sxs-lookup"><span data-stu-id="f1f90-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="f1f90-133">В результате переходы выполняются очень быстро, но неправильное объявление вызова неуправляемого кода может привести к сбою программы.</span><span class="sxs-lookup"><span data-stu-id="f1f90-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="f1f90-134">Чтобы упростить обнаружение неверных объявлений во время разработки, улучшен процесс отладки в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f1f90-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="f1f90-135">Помощник по отладке управляемого кода [пинвокестаккимбаланце](../../../debug-trace-profile/pinvokestackimbalance-mda.md) (MDA) уведомляет вас о неправильном объявлении вызова платформы, когда приложение выполняется с присоединенным отладчиком.</span><span class="sxs-lookup"><span data-stu-id="f1f90-135">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="f1f90-136">Для решения сценариев, в которых приложение использует компоненты, которые нельзя перекомпилировать, с неправильными объявлениями вызова неуправляемого кода, можно использовать элемент `NetFx40_PInvokeStackResilience`.</span><span class="sxs-lookup"><span data-stu-id="f1f90-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="f1f90-137">Добавление этого элемента в файл конфигурации приложения с `enabled="1"` переводится в режим совместимости с поведением более ранних версий .NET Framework, за счет более медленных переходов.</span><span class="sxs-lookup"><span data-stu-id="f1f90-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="f1f90-138">Сборки, скомпилированные для более ранних версий .NET Framework, автоматически включаются в этот режим совместимости и не нуждаются в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="f1f90-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="f1f90-139">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1f90-139">Configuration File</span></span>

<span data-ttu-id="f1f90-140">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f1f90-140">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="f1f90-141">Пример</span><span class="sxs-lookup"><span data-stu-id="f1f90-141">Example</span></span>

<span data-ttu-id="f1f90-142">В следующем примере показано, как выбрать повышенную устойчивость к неправильным объявлениям вызова неуправляемого кода для приложения за счет более медленных переходов между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="f1f90-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f1f90-143">См. также</span><span class="sxs-lookup"><span data-stu-id="f1f90-143">See also</span></span>

- [<span data-ttu-id="f1f90-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f1f90-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f1f90-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1f90-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f1f90-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="f1f90-146">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
