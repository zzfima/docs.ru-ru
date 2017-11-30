---
title: "&lt;Добавить&gt; элемент для &lt;sharedListeners&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fd8e7d18ca72cbeb558876eefcde17ebdc6c095f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a><span data-ttu-id="970b0-102">&lt;Добавить&gt; элемент для &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="970b0-102">&lt;add&gt; Element for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="970b0-103">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="970b0-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="970b0-104">`sharedListeners`— Это коллекция прослушивателей, чтобы любое [ \<источника >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [ \<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) может ссылаться.</span><span class="sxs-lookup"><span data-stu-id="970b0-104">`sharedListeners` is a collection of listeners that any [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) can reference.</span></span>  <span data-ttu-id="970b0-105">По умолчанию в прослушиватели `sharedListeners` коллекции не помещаются в `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="970b0-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="970b0-106">Они должны быть добавлены по имени, чтобы [ \<источника >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [ \<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="970b0-106">They must be added by name to the [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span></span> <span data-ttu-id="970b0-107">Невозможно получить прослушиватели `sharedListeners` коллекции в коде во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="970b0-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="970b0-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="970b0-108">\<configuration></span></span>  
<span data-ttu-id="970b0-109">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="970b0-109">\<system.diagnostics></span></span>  
<span data-ttu-id="970b0-110">\<sharedListeners > элемент</span><span class="sxs-lookup"><span data-stu-id="970b0-110">\<sharedListeners> Element</span></span>  
<span data-ttu-id="970b0-111">\<add></span><span class="sxs-lookup"><span data-stu-id="970b0-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970b0-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="970b0-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="970b0-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="970b0-113">Attributes and Elements</span></span>  
 <span data-ttu-id="970b0-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="970b0-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="970b0-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="970b0-115">Attributes</span></span>  
  
|<span data-ttu-id="970b0-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="970b0-116">Attribute</span></span>|<span data-ttu-id="970b0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="970b0-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="970b0-118">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="970b0-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="970b0-119">Указывает имя прослушивателя, который используется для добавления общего прослушивателя для `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="970b0-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="970b0-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="970b0-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="970b0-121">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="970b0-121">Specifies the type of the listener.</span></span> <span data-ttu-id="970b0-122">Необходимо использовать строку, отвечающую требованиям, указанным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="970b0-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="970b0-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="970b0-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="970b0-124">Строка, передаваемая в конструктор для заданного класса.</span><span class="sxs-lookup"><span data-stu-id="970b0-124">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="970b0-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="970b0-125">Child Elements</span></span>  
  
|<span data-ttu-id="970b0-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="970b0-126">Element</span></span>|<span data-ttu-id="970b0-127">Описание</span><span class="sxs-lookup"><span data-stu-id="970b0-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="970b0-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="970b0-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="970b0-129">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="970b0-129">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="970b0-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="970b0-130">Parent Elements</span></span>  
  
|<span data-ttu-id="970b0-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="970b0-131">Element</span></span>|<span data-ttu-id="970b0-132">Описание</span><span class="sxs-lookup"><span data-stu-id="970b0-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="970b0-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="970b0-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="970b0-134">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="970b0-134">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="970b0-135">Коллекция прослушивателей, которые могут ссылаться на любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="970b0-135">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="970b0-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="970b0-136">Remarks</span></span>  
 <span data-ttu-id="970b0-137">Классы слушателя поставляются с платформой .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="970b0-137">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="970b0-138">Значение для `name` атрибут используется для добавления общего прослушивателя для `Listeners` сбор данных для трассировки или источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="970b0-138">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="970b0-139">Значение для `initializeData` атрибута зависит от типа создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="970b0-139">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="970b0-140">Не все прослушиватели трассировки требуют указывать `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="970b0-140">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="970b0-141">При использовании `initializeData` атрибут, можно получить компилятор предупреждение «атрибута «initializeData» не объявлен.»</span><span class="sxs-lookup"><span data-stu-id="970b0-141">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="970b0-142">Это предупреждение возникает, поскольку параметры конфигурации проверяются абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута.</span><span class="sxs-lookup"><span data-stu-id="970b0-142">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="970b0-143">Как правило можно игнорировать это предупреждение для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="970b0-143">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="970b0-144">В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описываются значения их `initializeData` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="970b0-144">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="970b0-145">Класс прослушивателей трассировки</span><span class="sxs-lookup"><span data-stu-id="970b0-145">Trace listener class</span></span>|<span data-ttu-id="970b0-146">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="970b0-146">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="970b0-147">`useErrorStream` Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="970b0-147">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="970b0-148">Задать `initializeData` для атрибута "`true`«для записи выходных данных трассировки и отладки в стандартный поток ошибок; присвоить»`false`» на запись в стандартный выходной поток.</span><span class="sxs-lookup"><span data-stu-id="970b0-148">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="970b0-149">Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="970b0-149">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="970b0-150">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="970b0-150">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="970b0-151">Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="970b0-151">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="970b0-152">Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="970b0-152">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="970b0-153">Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="970b0-153">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="970b0-154">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="970b0-154">Configuration File</span></span>  
 <span data-ttu-id="970b0-155">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="970b0-155">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="970b0-156">Пример</span><span class="sxs-lookup"><span data-stu-id="970b0-156">Example</span></span>  
 <span data-ttu-id="970b0-157">В следующем примере показано, как использовать `<add>` элементы для добавления <xref:System.Diagnostics.TextWriterTraceListener> `textListener` для `sharedListeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="970b0-157">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="970b0-158">`textListener`добавляется по имени, чтобы `Listeners` коллекции для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="970b0-158">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="970b0-159">`textListener` Прослушиватель записывает выходные данные трассировки в файл myListener.log.</span><span class="sxs-lookup"><span data-stu-id="970b0-159">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="970b0-160">См. также</span><span class="sxs-lookup"><span data-stu-id="970b0-160">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="970b0-161">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="970b0-161">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="970b0-162">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="970b0-162">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
