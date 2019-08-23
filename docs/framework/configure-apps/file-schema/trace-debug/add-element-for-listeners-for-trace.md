---
title: <add>Элемент для <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: d4ff919991ab1505b2845a225706d32cc1e57d0a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920573"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="49e24-102">\<Добавление элемента > для \<прослушивателей, \<> для трассировки ></span><span class="sxs-lookup"><span data-stu-id="49e24-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="49e24-103">Добавляет прослушиватель в коллекцию **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="49e24-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="49e24-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="49e24-104">\<configuration></span></span>  
<span data-ttu-id="49e24-105">\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="49e24-105">\<system.diagnostics></span></span>  
<span data-ttu-id="49e24-106">\<> трассировки</span><span class="sxs-lookup"><span data-stu-id="49e24-106">\<trace></span></span>  
<span data-ttu-id="49e24-107">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="49e24-107">\<listeners></span></span>  
<span data-ttu-id="49e24-108">\<add></span><span class="sxs-lookup"><span data-stu-id="49e24-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e24-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49e24-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49e24-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="49e24-110">Attributes and Elements</span></span>  
 <span data-ttu-id="49e24-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="49e24-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49e24-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="49e24-112">Attributes</span></span>  
  
|<span data-ttu-id="49e24-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="49e24-113">Attribute</span></span>|<span data-ttu-id="49e24-114">Описание</span><span class="sxs-lookup"><span data-stu-id="49e24-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49e24-115">**type**</span><span class="sxs-lookup"><span data-stu-id="49e24-115">**type**</span></span>|<span data-ttu-id="49e24-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="49e24-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="49e24-117">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="49e24-117">Specifies the type of the listener.</span></span> <span data-ttu-id="49e24-118">Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="49e24-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="49e24-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="49e24-119">**initializeData**</span></span>|<span data-ttu-id="49e24-120">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="49e24-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="49e24-121">Строка, передаваемая конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="49e24-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="49e24-122">**name**</span><span class="sxs-lookup"><span data-stu-id="49e24-122">**name**</span></span>|<span data-ttu-id="49e24-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="49e24-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="49e24-124">Указывает имя прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="49e24-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49e24-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="49e24-125">Child Elements</span></span>  
  
|<span data-ttu-id="49e24-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="49e24-126">Element</span></span>|<span data-ttu-id="49e24-127">Описание</span><span class="sxs-lookup"><span data-stu-id="49e24-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49e24-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="49e24-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="49e24-129">Добавляет фильтр в прослушиватель в `Listeners` коллекции для трассировки.</span><span class="sxs-lookup"><span data-stu-id="49e24-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49e24-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="49e24-130">Parent Elements</span></span>  
  
|<span data-ttu-id="49e24-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="49e24-131">Element</span></span>|<span data-ttu-id="49e24-132">Описание</span><span class="sxs-lookup"><span data-stu-id="49e24-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="49e24-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49e24-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="49e24-134">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="49e24-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="49e24-135">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="49e24-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="49e24-136">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="49e24-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="49e24-137">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="49e24-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49e24-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="49e24-138">Remarks</span></span>  
 <span data-ttu-id="49e24-139">Классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> совместно используют одну и ту же коллекцию Listeners.</span><span class="sxs-lookup"><span data-stu-id="49e24-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="49e24-140">При добавлении объекта прослушивателя в коллекцию в одном из этих классов другой класс использует тот же прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="49e24-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="49e24-141">Классы прослушивателей являются производными от <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="49e24-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="49e24-142">Если `name` атрибут прослушивателя трассировки не указан, то <xref:System.Diagnostics.TraceListener.Name%2A> для прослушивателя трассировки по умолчанию используется пустая строка ("").</span><span class="sxs-lookup"><span data-stu-id="49e24-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="49e24-143">Если у приложения есть только один прослушиватель, можно добавить его без указания имени и удалить его, указав в качестве имени пустую строку.</span><span class="sxs-lookup"><span data-stu-id="49e24-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="49e24-144">Однако если приложение имеет более одного прослушивателя, необходимо указать уникальные имена для каждого прослушивателя трассировки, что позволяет определять отдельные прослушиватели трассировки в <xref:System.Diagnostics.Debug.Listeners%2A> коллекциях и <xref:System.Diagnostics.Trace.Listeners%2A> управлять ими.</span><span class="sxs-lookup"><span data-stu-id="49e24-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49e24-145">Добавление нескольких прослушивателей трассировки одного и того же типа и с одним и тем же именем приводит к тому, что только один прослушиватель трассировки этого типа и `Listeners` имя добавляются в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="49e24-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="49e24-146">Тем не менее можно программно добавить несколько идентичных прослушивателей в `Listeners` коллекцию.</span><span class="sxs-lookup"><span data-stu-id="49e24-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="49e24-147">Значение атрибута **initializeData** зависит от типа создаваемого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="49e24-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="49e24-148">Не все прослушиватели трассировки нуждаются в указании **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="49e24-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49e24-149">При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен".</span><span class="sxs-lookup"><span data-stu-id="49e24-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="49e24-150">Это предупреждение возникает из-за того, что параметры конфигурации проверяются <xref:System.Diagnostics.TraceListener>по абстрактному базовому классу, который не `initializeData` распознает атрибут.</span><span class="sxs-lookup"><span data-stu-id="49e24-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="49e24-151">Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="49e24-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="49e24-152">В следующей таблице показаны прослушиватели трассировки, которые включены в .NET Framework и описаны значения их атрибутов **initializeData** .</span><span class="sxs-lookup"><span data-stu-id="49e24-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="49e24-153">Класс прослушивателя трассировки</span><span class="sxs-lookup"><span data-stu-id="49e24-153">Trace listener class</span></span>|<span data-ttu-id="49e24-154">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="49e24-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e24-155">`useErrorStream` Значение<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> для конструктора.</span><span class="sxs-lookup"><span data-stu-id="49e24-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="49e24-156">Задайте для`true`атрибута значение "", чтобы записывать выходные данные трассировки и <xref:System.Console.Error%2A?displayProperty=nameWithType>отладки в; `initializeData` "`false`" для <xref:System.Console.Out%2A?displayProperty=nameWithType>записи.</span><span class="sxs-lookup"><span data-stu-id="49e24-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e24-157">Имя файла, <xref:System.Diagnostics.DelimitedListTraceListener> в который производится запись.</span><span class="sxs-lookup"><span data-stu-id="49e24-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e24-158">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="49e24-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e24-159">Имя файла, в который <xref:System.Diagnostics.EventSchemaTraceListener> производится запись.</span><span class="sxs-lookup"><span data-stu-id="49e24-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e24-160">Имя файла, в который <xref:System.Diagnostics.TextWriterTraceListener> производится запись.</span><span class="sxs-lookup"><span data-stu-id="49e24-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e24-161">Имя файла, в который <xref:System.Diagnostics.XmlWriterTraceListener> производится запись.</span><span class="sxs-lookup"><span data-stu-id="49e24-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="49e24-162">Пример</span><span class="sxs-lookup"><span data-stu-id="49e24-162">Example</span></span>  
 <span data-ttu-id="49e24-163">В следующем примере показано, как использовать  **\<Add >** Elements для добавления прослушивателей `MyEventListener` `MyListener` и в коллекцию **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="49e24-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="49e24-164">`MyListener`создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="49e24-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="49e24-165">`MyEventListener`создает запись в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="49e24-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="49e24-166">См. также</span><span class="sxs-lookup"><span data-stu-id="49e24-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="49e24-167">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="49e24-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="49e24-168">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="49e24-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
