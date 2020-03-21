---
title: <add>Элемент <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153676"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="152aa-102">\<добавить элемент \<> \<для слушателей> для> трассировки</span><span class="sxs-lookup"><span data-stu-id="152aa-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="152aa-103">Добавляет слушателя в коллекцию **Слушателей.**</span><span class="sxs-lookup"><span data-stu-id="152aa-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="152aa-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="152aa-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="152aa-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="152aa-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="152aa-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<след>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="152aa-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="152aa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="152aa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="152aa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="152aa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="152aa-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="152aa-109">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="152aa-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="152aa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="152aa-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="152aa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="152aa-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="152aa-112">Attributes</span></span>  
  
|<span data-ttu-id="152aa-113">attribute</span><span class="sxs-lookup"><span data-stu-id="152aa-113">Attribute</span></span>|<span data-ttu-id="152aa-114">Описание</span><span class="sxs-lookup"><span data-stu-id="152aa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="152aa-115">**тип**</span><span class="sxs-lookup"><span data-stu-id="152aa-115">**type**</span></span>|<span data-ttu-id="152aa-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="152aa-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="152aa-117">Определяет тип слушателя.</span><span class="sxs-lookup"><span data-stu-id="152aa-117">Specifies the type of the listener.</span></span> <span data-ttu-id="152aa-118">Необходимо использовать строку, соответствующую требованиям, указанным в [определении полностью квалифицированных имен типов.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span><span class="sxs-lookup"><span data-stu-id="152aa-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="152aa-119">**инициализацияДанны**</span><span class="sxs-lookup"><span data-stu-id="152aa-119">**initializeData**</span></span>|<span data-ttu-id="152aa-120">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="152aa-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="152aa-121">Строка перешла к конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="152aa-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="152aa-122">**name**</span><span class="sxs-lookup"><span data-stu-id="152aa-122">**name**</span></span>|<span data-ttu-id="152aa-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="152aa-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="152aa-124">Определяет имя слушателя.</span><span class="sxs-lookup"><span data-stu-id="152aa-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="152aa-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="152aa-125">Child Elements</span></span>  
  
|<span data-ttu-id="152aa-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="152aa-126">Element</span></span>|<span data-ttu-id="152aa-127">Описание</span><span class="sxs-lookup"><span data-stu-id="152aa-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="152aa-128">\<фильтр></span><span class="sxs-lookup"><span data-stu-id="152aa-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="152aa-129">Добавляет фильтр слушателю в `Listeners` коллекцию для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="152aa-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="152aa-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="152aa-130">Parent Elements</span></span>  
  
|<span data-ttu-id="152aa-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="152aa-131">Element</span></span>|<span data-ttu-id="152aa-132">Описание</span><span class="sxs-lookup"><span data-stu-id="152aa-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="152aa-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="152aa-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="152aa-134">Определяет слушателя, который собирает, хранит и направляет сообщения.</span><span class="sxs-lookup"><span data-stu-id="152aa-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="152aa-135">Слушатели направляют результаты отслеживания на соответствующую цель.</span><span class="sxs-lookup"><span data-stu-id="152aa-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="152aa-136">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="152aa-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="152aa-137">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="152aa-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="152aa-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="152aa-138">Remarks</span></span>  
 <span data-ttu-id="152aa-139"><xref:System.Diagnostics.Debug> Классы <xref:System.Diagnostics.Trace> и классы имеют одну и ту же коллекцию **Слушателей.**</span><span class="sxs-lookup"><span data-stu-id="152aa-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="152aa-140">Если вы добавляете объект слушателя в коллекцию в одном из этих классов, другой класс использует тот же самый слушатель.</span><span class="sxs-lookup"><span data-stu-id="152aa-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="152aa-141">Классы слушателя вытекают из <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="152aa-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="152aa-142">Если вы не `name` указываете атрибут слушателя <xref:System.Diagnostics.TraceListener.Name%2A> трассировки, то слушатель трассировки по умолчанию по умолчанию к пустой строке (").</span><span class="sxs-lookup"><span data-stu-id="152aa-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="152aa-143">Если в приложении есть только один слушатель, вы можете добавить его, не указывая имя, и удалить его, указав пустую строку для имени.</span><span class="sxs-lookup"><span data-stu-id="152aa-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="152aa-144">Однако, если в вашем приложении более одного слушателя, следует указать уникальные имена для каждого <xref:System.Diagnostics.Debug.Listeners%2A> слушателя трассы, что позволяет идентифицировать и управлять отдельными слушателями трассировки в коллекциях и <xref:System.Diagnostics.Trace.Listeners%2A> коллекциях.</span><span class="sxs-lookup"><span data-stu-id="152aa-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="152aa-145">Добавление более одного слушателя трассы одного и того же типа и с тем же именем `Listeners` приводит к добавлению в коллекцию только одного слушателя этого типа и имени.</span><span class="sxs-lookup"><span data-stu-id="152aa-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="152aa-146">Тем не менее, вы можете программно `Listeners` добавить несколько идентичных слушателей в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="152aa-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="152aa-147">Значение атрибута **инициализироватьData** зависит от типа создаваемого слушателя.</span><span class="sxs-lookup"><span data-stu-id="152aa-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="152aa-148">Не все слушатели трасс требуют, чтобы вы **указали инициализироватьData.**</span><span class="sxs-lookup"><span data-stu-id="152aa-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="152aa-149">При использовании `initializeData` атрибута можно получить предупреждение компилятора "Атрибут "initializeData" не объявлен".</span><span class="sxs-lookup"><span data-stu-id="152aa-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="152aa-150">Это предупреждение возникает из-за того, что <xref:System.Diagnostics.TraceListener>настройки конфигурации `initializeData` проверяются на основе абстрактного базового класса, который не распознает атрибут.</span><span class="sxs-lookup"><span data-stu-id="152aa-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="152aa-151">Как правило, можно проигнорировать это предупреждение для реализации микрослушателя, у которых есть конструктор, который принимает параметр.</span><span class="sxs-lookup"><span data-stu-id="152aa-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="152aa-152">В следующей таблице показаны слушатели трасс, включенные в рамку .NET, и описывается значение их **инициализировать** атрибуты Data.</span><span class="sxs-lookup"><span data-stu-id="152aa-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="152aa-153">Класс слушателя трассировки</span><span class="sxs-lookup"><span data-stu-id="152aa-153">Trace listener class</span></span>|<span data-ttu-id="152aa-154">инициализация значения атрибутаData</span><span class="sxs-lookup"><span data-stu-id="152aa-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="152aa-155">Значение `useErrorStream` для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.</span><span class="sxs-lookup"><span data-stu-id="152aa-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="152aa-156">Установите `initializeData` атрибут`true`на " для записи <xref:System.Console.Error%2A?displayProperty=nameWithType>трассировки и отладки вывода; ",`false`чтобы <xref:System.Console.Out%2A?displayProperty=nameWithType>написать .</span><span class="sxs-lookup"><span data-stu-id="152aa-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="152aa-157">Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="152aa-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="152aa-158">Имя имени существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="152aa-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="152aa-159">Имя файла, который <xref:System.Diagnostics.EventSchemaTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="152aa-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="152aa-160">Имя файла, который <xref:System.Diagnostics.TextWriterTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="152aa-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="152aa-161">Имя файла, который <xref:System.Diagnostics.XmlWriterTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="152aa-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="152aa-162">Пример</span><span class="sxs-lookup"><span data-stu-id="152aa-162">Example</span></span>  
 <span data-ttu-id="152aa-163">Ниже приводится пример, \*\* \<\*\* как использовать>`MyListener` элементы для добавления слушателей и `MyEventListener` коллекции **Слушателей.**</span><span class="sxs-lookup"><span data-stu-id="152aa-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="152aa-164">`MyListener`создает вызванный `MyListener.log` файл и записывает вывод в файл.</span><span class="sxs-lookup"><span data-stu-id="152aa-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="152aa-165">`MyEventListener`создает запись в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="152aa-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="152aa-166">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="152aa-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="152aa-167">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="152aa-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="152aa-168">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="152aa-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
