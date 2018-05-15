---
title: '&lt;Добавить&gt; элемент для &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 27d83ba706b4d93b4ac5426bf5bae59b4bfc0d9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a><span data-ttu-id="20ec1-102">&lt;Добавить&gt; элемент для &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="20ec1-102">&lt;add&gt; Element for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="20ec1-103">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="20ec1-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="20ec1-104">`sharedListeners` — Это коллекция прослушивателей, чтобы любое [ \<источника >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [ \<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) может ссылаться.</span><span class="sxs-lookup"><span data-stu-id="20ec1-104">`sharedListeners` is a collection of listeners that any [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) can reference.</span></span>  <span data-ttu-id="20ec1-105">По умолчанию в прослушиватели `sharedListeners` коллекции не помещаются в `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="20ec1-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="20ec1-106">Они должны быть добавлены по имени, чтобы [ \<источника >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [ \<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="20ec1-106">They must be added by name to the [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span></span> <span data-ttu-id="20ec1-107">Невозможно получить прослушиватели `sharedListeners` коллекции в коде во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="20ec1-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="20ec1-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="20ec1-108">\<configuration></span></span>  
<span data-ttu-id="20ec1-109">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="20ec1-109">\<system.diagnostics></span></span>  
<span data-ttu-id="20ec1-110">\<sharedListeners > элемент</span><span class="sxs-lookup"><span data-stu-id="20ec1-110">\<sharedListeners> Element</span></span>  
<span data-ttu-id="20ec1-111">\<add></span><span class="sxs-lookup"><span data-stu-id="20ec1-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ec1-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20ec1-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20ec1-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="20ec1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="20ec1-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="20ec1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20ec1-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="20ec1-115">Attributes</span></span>  
  
|<span data-ttu-id="20ec1-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="20ec1-116">Attribute</span></span>|<span data-ttu-id="20ec1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="20ec1-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="20ec1-118">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="20ec1-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="20ec1-119">Указывает имя прослушивателя, который используется для добавления общего прослушивателя для `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="20ec1-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="20ec1-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="20ec1-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="20ec1-121">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="20ec1-121">Specifies the type of the listener.</span></span> <span data-ttu-id="20ec1-122">Необходимо использовать строку, отвечающую требованиям, указанным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="20ec1-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="20ec1-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="20ec1-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="20ec1-124">Строка, передаваемая в конструктор для заданного класса.</span><span class="sxs-lookup"><span data-stu-id="20ec1-124">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20ec1-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="20ec1-125">Child Elements</span></span>  
  
|<span data-ttu-id="20ec1-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="20ec1-126">Element</span></span>|<span data-ttu-id="20ec1-127">Описание</span><span class="sxs-lookup"><span data-stu-id="20ec1-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20ec1-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="20ec1-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="20ec1-129">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="20ec1-129">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20ec1-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="20ec1-130">Parent Elements</span></span>  
  
|<span data-ttu-id="20ec1-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="20ec1-131">Element</span></span>|<span data-ttu-id="20ec1-132">Описание</span><span class="sxs-lookup"><span data-stu-id="20ec1-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="20ec1-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20ec1-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="20ec1-134">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="20ec1-134">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="20ec1-135">Коллекция прослушивателей, которые могут ссылаться на любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="20ec1-135">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20ec1-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="20ec1-136">Remarks</span></span>  
 <span data-ttu-id="20ec1-137">Классы слушателя поставляются с платформой .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="20ec1-137">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="20ec1-138">Значение для `name` атрибут используется для добавления общего прослушивателя для `Listeners` сбор данных для трассировки или источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="20ec1-138">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="20ec1-139">Значение для `initializeData` атрибута зависит от типа создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="20ec1-139">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="20ec1-140">Не все прослушиватели трассировки требуют указывать `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="20ec1-140">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20ec1-141">При использовании `initializeData` атрибут, можно получить компилятор предупреждение «атрибута «initializeData» не объявлен.»</span><span class="sxs-lookup"><span data-stu-id="20ec1-141">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="20ec1-142">Это предупреждение возникает, поскольку параметры конфигурации проверяются абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута.</span><span class="sxs-lookup"><span data-stu-id="20ec1-142">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="20ec1-143">Как правило можно игнорировать это предупреждение для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="20ec1-143">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="20ec1-144">В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описываются значения их `initializeData` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="20ec1-144">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="20ec1-145">Класс прослушивателей трассировки</span><span class="sxs-lookup"><span data-stu-id="20ec1-145">Trace listener class</span></span>|<span data-ttu-id="20ec1-146">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="20ec1-146">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="20ec1-147">`useErrorStream` Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="20ec1-147">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="20ec1-148">Задать `initializeData` для атрибута "`true`«для записи выходных данных трассировки и отладки в стандартный поток ошибок; присвоить»`false`» на запись в стандартный выходной поток.</span><span class="sxs-lookup"><span data-stu-id="20ec1-148">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="20ec1-149">Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="20ec1-149">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="20ec1-150">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="20ec1-150">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="20ec1-151">Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="20ec1-151">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="20ec1-152">Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="20ec1-152">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="20ec1-153">Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="20ec1-153">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="20ec1-154">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="20ec1-154">Configuration File</span></span>  
 <span data-ttu-id="20ec1-155">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="20ec1-155">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20ec1-156">Пример</span><span class="sxs-lookup"><span data-stu-id="20ec1-156">Example</span></span>  
 <span data-ttu-id="20ec1-157">В следующем примере показано, как использовать `<add>` элементы для добавления <xref:System.Diagnostics.TextWriterTraceListener> `textListener` для `sharedListeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="20ec1-157">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="20ec1-158">`textListener` добавляется по имени, чтобы `Listeners` коллекции для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="20ec1-158">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="20ec1-159">`textListener` Прослушиватель записывает выходные данные трассировки в файл myListener.log.</span><span class="sxs-lookup"><span data-stu-id="20ec1-159">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="20ec1-160">См. также</span><span class="sxs-lookup"><span data-stu-id="20ec1-160">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="20ec1-161">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="20ec1-161">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="20ec1-162">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="20ec1-162">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
