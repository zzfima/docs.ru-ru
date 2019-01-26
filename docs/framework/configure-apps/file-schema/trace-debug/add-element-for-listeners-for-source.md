---
title: '&lt;Добавить&gt; элемент для &lt;прослушиватели&gt; для &lt;источника&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 9e1bc2629b613b278ad38bbe9aab4cdfaa3f2a5e
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084033"
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="09104-102">&lt;Добавить&gt; элемент для &lt;прослушиватели&gt; для &lt;источника&gt;</span><span class="sxs-lookup"><span data-stu-id="09104-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="09104-103">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="09104-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="09104-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="09104-104">\<configuration></span></span>  
<span data-ttu-id="09104-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="09104-105">\<system.diagnostics></span></span>  
<span data-ttu-id="09104-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="09104-106">\<sources></span></span>  
<span data-ttu-id="09104-107">\<Источник ></span><span class="sxs-lookup"><span data-stu-id="09104-107">\<source></span></span>  
<span data-ttu-id="09104-108">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="09104-108">\<listeners></span></span>  
<span data-ttu-id="09104-109">\<add></span><span class="sxs-lookup"><span data-stu-id="09104-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09104-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09104-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09104-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09104-111">Attributes and Elements</span></span>  
 <span data-ttu-id="09104-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="09104-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09104-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09104-113">Attributes</span></span>  
  
|<span data-ttu-id="09104-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="09104-114">Attribute</span></span>|<span data-ttu-id="09104-115">Описание</span><span class="sxs-lookup"><span data-stu-id="09104-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="09104-116">Необходимый атрибут, в том случае, если не обращаются к прослушивателю в `sharedListeners` коллекции, в котором случае необходима только для ссылки на него по имени (см. в разделе [пример](#example)).</span><span class="sxs-lookup"><span data-stu-id="09104-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="09104-117">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="09104-117">Specifies the type of the listener.</span></span> <span data-ttu-id="09104-118">Необходимо использовать строку, которая соответствует требованиям, перечисленным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="09104-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="09104-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="09104-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="09104-120">Строка, передаваемая в конструктор для заданного класса.</span><span class="sxs-lookup"><span data-stu-id="09104-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="09104-121">Объект <xref:System.Configuration.ConfigurationException> создается, если класс имеет конструктор, принимающий строку.</span><span class="sxs-lookup"><span data-stu-id="09104-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="09104-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="09104-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="09104-123">Имя прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="09104-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="09104-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="09104-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="09104-125">Указывает <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> значение свойства для прослушивателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="09104-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="09104-126">[настраиваемые атрибуты]</span><span class="sxs-lookup"><span data-stu-id="09104-126">[custom attributes]</span></span>|<span data-ttu-id="09104-127">Необязательные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="09104-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="09104-128">Указывает значение для прослушивателя атрибутов, идентифицируемых <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> метод для этого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="09104-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="09104-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> является примером дополнительный атрибут, уникальные для <xref:System.Diagnostics.DelimitedListTraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="09104-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09104-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09104-130">Child Elements</span></span>  
  
|<span data-ttu-id="09104-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="09104-131">Element</span></span>|<span data-ttu-id="09104-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="09104-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09104-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="09104-133">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="09104-134">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="09104-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09104-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09104-135">Parent Elements</span></span>  
  
|<span data-ttu-id="09104-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="09104-136">Element</span></span>|<span data-ttu-id="09104-137">Описание:</span><span class="sxs-lookup"><span data-stu-id="09104-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="09104-138">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="09104-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="09104-139">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="09104-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="09104-140">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="09104-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="09104-141">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="09104-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="09104-142">Задает прослушиватели для сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="09104-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09104-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="09104-143">Remarks</span></span>  
 <span data-ttu-id="09104-144">Классы прослушивателя, поставлявшихся с .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="09104-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="09104-145">Если вы не укажете `name` атрибут прослушивателя трассировки, <xref:System.Diagnostics.TraceListener.Name%2A> свойства прослушивателя трассировки по умолчанию используется пустая строка (»»).</span><span class="sxs-lookup"><span data-stu-id="09104-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="09104-146">Если у приложения имеется только один прослушиватель, его можно добавить без указания имени и его можно удалить, указав пустую строку для имени.</span><span class="sxs-lookup"><span data-stu-id="09104-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="09104-147">Тем не менее, если приложение имеет несколько прослушивателей, следует указать уникальное имя для каждого прослушивателя трассировки, для идентификации и управления ими в прослушиватели трассировки в отдельных <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> коллекции.</span><span class="sxs-lookup"><span data-stu-id="09104-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09104-148">Добавление более одного прослушивателя трассировки, того же типа и с тем же присвойте приводит только одного прослушивателя этого типа имя, а, добавляемый `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="09104-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="09104-149">Тем не менее, можно программно добавить несколько идентичных прослушивателей для `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="09104-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="09104-150">Значение для `initializeData` атрибута зависит от типа создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="09104-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="09104-151">Не все прослушиватели трассировки необходимо указать `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="09104-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09104-152">При использовании `initializeData` атрибут, может появиться предупреждение «атрибут «initializeData» не объявлен.» компилятора</span><span class="sxs-lookup"><span data-stu-id="09104-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="09104-153">Это предупреждение возникает, так как параметры конфигурации проверяются на соответствие абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута.</span><span class="sxs-lookup"><span data-stu-id="09104-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="09104-154">Как правило можно игнорировать это предупреждение для реализации прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="09104-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="09104-155">В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описаны значения их `initializeData` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="09104-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="09104-156">Класс прослушивателя трассировки</span><span class="sxs-lookup"><span data-stu-id="09104-156">Trace listener class</span></span>|<span data-ttu-id="09104-157">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="09104-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="09104-158">`useErrorStream` Значение <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="09104-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="09104-159">Задайте `initializeData` для атрибута "`true`«для записи выходных данных трассировки и отладки в стандартный поток ошибок; ему присвоено»`false`" для записи в стандартный выходной поток.</span><span class="sxs-lookup"><span data-stu-id="09104-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="09104-160">Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="09104-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="09104-161">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="09104-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="09104-162">Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="09104-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="09104-163">Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="09104-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="09104-164">Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="09104-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="09104-165">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="09104-165">Configuration File</span></span>  
 <span data-ttu-id="09104-166">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="09104-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09104-167">Пример</span><span class="sxs-lookup"><span data-stu-id="09104-167">Example</span></span>  
 <span data-ttu-id="09104-168">В следующем примере показано, как использовать `<add>` элементы для добавления прослушивателей `console` и `textListener` для `Listeners` коллекции для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="09104-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="09104-169">`textListener` Прослушиватель записывает выходные данные трассировки в файл myListener.log.</span><span class="sxs-lookup"><span data-stu-id="09104-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="09104-170">См. также</span><span class="sxs-lookup"><span data-stu-id="09104-170">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="09104-171">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="09104-171">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="09104-172">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="09104-172">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
