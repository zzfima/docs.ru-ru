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
ms.openlocfilehash: b8de4fd8a130f93b2ed3e14701c442a65c9ffcd8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712474"
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a><span data-ttu-id="d24c9-102">&lt;Добавить&gt; элемент для &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="d24c9-102">&lt;add&gt; Element for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="d24c9-103">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="d24c9-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="d24c9-104">`sharedListeners` — Это коллекция прослушивателей, что все [ \<источника >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [ \<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) может ссылаться на.</span><span class="sxs-lookup"><span data-stu-id="d24c9-104">`sharedListeners` is a collection of listeners that any [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) can reference.</span></span>  <span data-ttu-id="d24c9-105">По умолчанию, в прослушиватели `sharedListeners` коллекции не помещаются в `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="d24c9-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="d24c9-106">Они должны быть добавлены по имени, чтобы [ \<источника >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [ \<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="d24c9-106">They must be added by name to the [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span></span> <span data-ttu-id="d24c9-107">Невозможно получить прослушиватели `sharedListeners` коллекции в коде во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d24c9-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="d24c9-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d24c9-108">\<configuration></span></span>  
<span data-ttu-id="d24c9-109">&nbsp;&nbsp;\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d24c9-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="d24c9-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners > элемент</span><span class="sxs-lookup"><span data-stu-id="d24c9-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="d24c9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<Добавить ></span><span class="sxs-lookup"><span data-stu-id="d24c9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d24c9-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d24c9-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d24c9-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d24c9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d24c9-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d24c9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d24c9-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d24c9-115">Attributes</span></span>  
  
|<span data-ttu-id="d24c9-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d24c9-116">Attribute</span></span>|<span data-ttu-id="d24c9-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d24c9-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d24c9-118">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d24c9-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="d24c9-119">Указывает имя прослушивателя, который используется для добавления общего прослушивателя для `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="d24c9-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="d24c9-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d24c9-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="d24c9-121">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="d24c9-121">Specifies the type of the listener.</span></span> <span data-ttu-id="d24c9-122">Необходимо использовать строку, которая соответствует требованиям, перечисленным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="d24c9-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="d24c9-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d24c9-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d24c9-124">Строка, передаваемая в конструктор для заданного класса.</span><span class="sxs-lookup"><span data-stu-id="d24c9-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="d24c9-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d24c9-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="d24c9-126">Строковое представление одного или нескольких <xref:System.Diagnostics.TraceOptions> членов перечисления, указывающих данные для записи выходных данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="d24c9-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="d24c9-127">Элементы разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="d24c9-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="d24c9-128">Значение по умолчанию — «None».</span><span class="sxs-lookup"><span data-stu-id="d24c9-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d24c9-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d24c9-129">Child Elements</span></span>  
  
|<span data-ttu-id="d24c9-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="d24c9-130">Element</span></span>|<span data-ttu-id="d24c9-131">Описание</span><span class="sxs-lookup"><span data-stu-id="d24c9-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d24c9-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="d24c9-132">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="d24c9-133">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="d24c9-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d24c9-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d24c9-134">Parent Elements</span></span>  
  
|<span data-ttu-id="d24c9-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="d24c9-135">Element</span></span>|<span data-ttu-id="d24c9-136">Описание:</span><span class="sxs-lookup"><span data-stu-id="d24c9-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d24c9-137">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d24c9-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d24c9-138">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="d24c9-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="d24c9-139">Коллекция прослушивателей, которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="d24c9-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d24c9-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="d24c9-140">Remarks</span></span>  
 <span data-ttu-id="d24c9-141">Классы прослушивателя, поставлявшихся с .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="d24c9-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="d24c9-142">Значение для `name` атрибут используется для добавления общего прослушивателя для `Listeners` сбор данных для источника трассировки или трассировки.</span><span class="sxs-lookup"><span data-stu-id="d24c9-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="d24c9-143">Значение для `initializeData` атрибута зависит от типа создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="d24c9-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="d24c9-144">Не все прослушиватели трассировки необходимо указать `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="d24c9-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d24c9-145">При использовании `initializeData` атрибут, может появиться предупреждение «атрибут «initializeData» не объявлен.» компилятора</span><span class="sxs-lookup"><span data-stu-id="d24c9-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="d24c9-146">Это предупреждение возникает, так как параметры конфигурации проверяются на соответствие абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута.</span><span class="sxs-lookup"><span data-stu-id="d24c9-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="d24c9-147">Как правило можно игнорировать это предупреждение для реализации прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="d24c9-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="d24c9-148">В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описаны значения их `initializeData` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="d24c9-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="d24c9-149">Класс прослушивателя трассировки</span><span class="sxs-lookup"><span data-stu-id="d24c9-149">Trace listener class</span></span>|<span data-ttu-id="d24c9-150">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="d24c9-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="d24c9-151">`useErrorStream` Значение <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="d24c9-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="d24c9-152">Задайте `initializeData` для атрибута "`true`«для записи выходных данных трассировки и отладки в стандартный поток ошибок; ему присвоено»`false`" для записи в стандартный выходной поток.</span><span class="sxs-lookup"><span data-stu-id="d24c9-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="d24c9-153">Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="d24c9-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d24c9-154">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="d24c9-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d24c9-155">Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="d24c9-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d24c9-156">Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="d24c9-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="d24c9-157">Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="d24c9-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="d24c9-158">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="d24c9-158">Configuration File</span></span>  
 <span data-ttu-id="d24c9-159">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d24c9-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d24c9-160">Пример</span><span class="sxs-lookup"><span data-stu-id="d24c9-160">Example</span></span>  
 <span data-ttu-id="d24c9-161">В следующем примере показано, как использовать `<add>` добавляемые элементы <xref:System.Diagnostics.TextWriterTraceListener> `textListener` для `sharedListeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="d24c9-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="d24c9-162">`textListener` добавляется по имени, чтобы `Listeners` коллекции для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="d24c9-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="d24c9-163">`textListener` Прослушиватель записывает выходные данные трассировки в файл myListener.log.</span><span class="sxs-lookup"><span data-stu-id="d24c9-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d24c9-164">См. также</span><span class="sxs-lookup"><span data-stu-id="d24c9-164">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="d24c9-165">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="d24c9-165">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="d24c9-166">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="d24c9-166">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
