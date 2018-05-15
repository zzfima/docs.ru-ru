---
title: '&lt;Добавить&gt; элемент для &lt;прослушиватели&gt; для &lt;трассировки&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e27187c05b49b7f73ef19243a3286e8c1de71579
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="9fd95-102">&lt;Добавить&gt; элемент для &lt;прослушиватели&gt; для &lt;трассировки&gt;</span><span class="sxs-lookup"><span data-stu-id="9fd95-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="9fd95-103">Добавление прослушивателя к **прослушиватели** коллекции.</span><span class="sxs-lookup"><span data-stu-id="9fd95-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="9fd95-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9fd95-104">\<configuration></span></span>  
<span data-ttu-id="9fd95-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="9fd95-105">\<system.diagnostics></span></span>  
<span data-ttu-id="9fd95-106">\<трассировки ></span><span class="sxs-lookup"><span data-stu-id="9fd95-106">\<trace></span></span>  
<span data-ttu-id="9fd95-107">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="9fd95-107">\<listeners></span></span>  
<span data-ttu-id="9fd95-108">\<add></span><span class="sxs-lookup"><span data-stu-id="9fd95-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fd95-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fd95-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fd95-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9fd95-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9fd95-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9fd95-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fd95-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9fd95-112">Attributes</span></span>  
  
|<span data-ttu-id="9fd95-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9fd95-113">Attribute</span></span>|<span data-ttu-id="9fd95-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9fd95-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fd95-115">**type**</span><span class="sxs-lookup"><span data-stu-id="9fd95-115">**type**</span></span>|<span data-ttu-id="9fd95-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9fd95-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="9fd95-117">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="9fd95-117">Specifies the type of the listener.</span></span> <span data-ttu-id="9fd95-118">Необходимо использовать строку, отвечающую требованиям, указанным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="9fd95-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="9fd95-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="9fd95-119">**initializeData**</span></span>|<span data-ttu-id="9fd95-120">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9fd95-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9fd95-121">Строка, передаваемая в конструктор для заданного класса.</span><span class="sxs-lookup"><span data-stu-id="9fd95-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="9fd95-122">**name**</span><span class="sxs-lookup"><span data-stu-id="9fd95-122">**name**</span></span>|<span data-ttu-id="9fd95-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9fd95-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9fd95-124">Указывает имя прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="9fd95-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fd95-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9fd95-125">Child Elements</span></span>  
  
|<span data-ttu-id="9fd95-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="9fd95-126">Element</span></span>|<span data-ttu-id="9fd95-127">Описание</span><span class="sxs-lookup"><span data-stu-id="9fd95-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fd95-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="9fd95-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="9fd95-129">Добавляет фильтр в прослушиватель в `Listeners` сбор данных для трассировки.</span><span class="sxs-lookup"><span data-stu-id="9fd95-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9fd95-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9fd95-130">Parent Elements</span></span>  
  
|<span data-ttu-id="9fd95-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="9fd95-131">Element</span></span>|<span data-ttu-id="9fd95-132">Описание</span><span class="sxs-lookup"><span data-stu-id="9fd95-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9fd95-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9fd95-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="9fd95-134">Задает прослушиватель, собирающий, хранилища и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="9fd95-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="9fd95-135">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="9fd95-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9fd95-136">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9fd95-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="9fd95-137">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="9fd95-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fd95-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="9fd95-138">Remarks</span></span>  
 <span data-ttu-id="9fd95-139"><xref:System.Diagnostics.Debug> И <xref:System.Diagnostics.Trace> классы одного и того же **прослушиватели** коллекции.</span><span class="sxs-lookup"><span data-stu-id="9fd95-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="9fd95-140">Если добавить объект прослушивателя в коллекцию в один из этих классов, прослушивателю же используется в другом классе.</span><span class="sxs-lookup"><span data-stu-id="9fd95-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="9fd95-141">Прослушиватель классы являются производными от <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="9fd95-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="9fd95-142">Если вы не укажете `name` атрибут прослушивателя трассировки <xref:System.Diagnostics.TraceListener.Name%2A> прослушиватель трассировки по умолчанию пустая строка (»»).</span><span class="sxs-lookup"><span data-stu-id="9fd95-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="9fd95-143">Если приложение имеет только один прослушиватель, добавьте его без указания имени и удалить, указав для имени пустую строку.</span><span class="sxs-lookup"><span data-stu-id="9fd95-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="9fd95-144">Однако если приложение имеет более одного прослушивателя, следует указать уникальные имена для каждого прослушивателя трассировки, который позволяет идентифицировать и управлять отдельные прослушиватели трассировки в <xref:System.Diagnostics.Debug.Listeners%2A> и <xref:System.Diagnostics.Trace.Listeners%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="9fd95-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fd95-145">Добавлении более одного прослушивателя трассировки того же типа и с тем же именем приведет лишь один прослушиватель этого типа и имя, добавляемый `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="9fd95-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="9fd95-146">Однако можно программно добавить несколько идентичных прослушивателей для `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="9fd95-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="9fd95-147">Значение для **initializeData** атрибута зависит от типа создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="9fd95-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="9fd95-148">Не все прослушиватели трассировки требуют указывать **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="9fd95-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fd95-149">При использовании `initializeData` атрибут, можно получить компилятор предупреждение «атрибута «initializeData» не объявлен.»</span><span class="sxs-lookup"><span data-stu-id="9fd95-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="9fd95-150">Это предупреждение возникает, поскольку параметры конфигурации проверяются абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута.</span><span class="sxs-lookup"><span data-stu-id="9fd95-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="9fd95-151">Как правило можно игнорировать это предупреждение для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="9fd95-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="9fd95-152">В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описываются значения их **initializeData** атрибуты.</span><span class="sxs-lookup"><span data-stu-id="9fd95-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="9fd95-153">Класс прослушивателей трассировки</span><span class="sxs-lookup"><span data-stu-id="9fd95-153">Trace listener class</span></span>|<span data-ttu-id="9fd95-154">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="9fd95-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9fd95-155">`useErrorStream` Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="9fd95-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="9fd95-156">Задать `initializeData` для атрибута "`true`» для записи трассировки и отладки выходных данных <xref:System.Console.Error%2A?displayProperty=nameWithType>; «`false`» для записи <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fd95-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9fd95-157">Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="9fd95-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9fd95-158">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="9fd95-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9fd95-159">Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="9fd95-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9fd95-160">Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="9fd95-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9fd95-161">Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.</span><span class="sxs-lookup"><span data-stu-id="9fd95-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9fd95-162">Пример</span><span class="sxs-lookup"><span data-stu-id="9fd95-162">Example</span></span>  
 <span data-ttu-id="9fd95-163">В следующем примере показано, как использовать  **\<Добавить >** элементы для добавления прослушивателей `MyListener` и `MyEventListener` для **прослушиватели** коллекции.</span><span class="sxs-lookup"><span data-stu-id="9fd95-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="9fd95-164">`MyListener` Создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="9fd95-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="9fd95-165">`MyEventListener` создает запись в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="9fd95-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fd95-166">См. также</span><span class="sxs-lookup"><span data-stu-id="9fd95-166">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [<span data-ttu-id="9fd95-167">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="9fd95-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="9fd95-168">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="9fd95-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
