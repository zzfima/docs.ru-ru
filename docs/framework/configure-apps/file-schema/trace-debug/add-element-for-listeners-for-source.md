---
title: <add>Элемент <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153689"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="68583-102">\<добавить элемент \<> \<для слушателей> для исходных></span><span class="sxs-lookup"><span data-stu-id="68583-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="68583-103">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="68583-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="68583-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="68583-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="68583-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="68583-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="68583-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<источники>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="68583-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="68583-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<источник>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="68583-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="68583-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="68583-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="68583-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="68583-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="68583-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68583-110">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68583-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="68583-111">Attributes and Elements</span></span>  
 <span data-ttu-id="68583-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="68583-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68583-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="68583-113">Attributes</span></span>  
  
|<span data-ttu-id="68583-114">attribute</span><span class="sxs-lookup"><span data-stu-id="68583-114">Attribute</span></span>|<span data-ttu-id="68583-115">Описание</span><span class="sxs-lookup"><span data-stu-id="68583-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="68583-116">Требуемый атрибут, если вы не ссылаетесь `sharedListeners` на слушателя в коллекции, и в этом случае вам нужно только сослаться на него по имени (см. [пример).](#example)</span><span class="sxs-lookup"><span data-stu-id="68583-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="68583-117">Определяет тип слушателя.</span><span class="sxs-lookup"><span data-stu-id="68583-117">Specifies the type of the listener.</span></span> <span data-ttu-id="68583-118">Необходимо использовать строку, соответствующую требованиям, указанным в [определении полностью квалифицированных имен типов.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span><span class="sxs-lookup"><span data-stu-id="68583-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="68583-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="68583-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="68583-120">Строка перешла к конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="68583-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="68583-121">A <xref:System.Configuration.ConfigurationException> брошен, если класс не имеет конструктора, который занимает строку.</span><span class="sxs-lookup"><span data-stu-id="68583-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="68583-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="68583-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="68583-123">Определяет имя слушателя.</span><span class="sxs-lookup"><span data-stu-id="68583-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="68583-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="68583-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="68583-125">Определяет значение <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> свойства для слушателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="68583-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="68583-126">(таможенные атрибуты)</span><span class="sxs-lookup"><span data-stu-id="68583-126">[custom attributes]</span></span>|<span data-ttu-id="68583-127">Дополнительные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="68583-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="68583-128">Определяет значение для специфических атрибутов, определенных <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> методом для этого слушателя.</span><span class="sxs-lookup"><span data-stu-id="68583-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="68583-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>является примером дополнительного атрибута, уникального <xref:System.Diagnostics.DelimitedListTraceListener> для класса.</span><span class="sxs-lookup"><span data-stu-id="68583-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68583-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="68583-130">Child Elements</span></span>  
  
|<span data-ttu-id="68583-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="68583-131">Element</span></span>|<span data-ttu-id="68583-132">Описание</span><span class="sxs-lookup"><span data-stu-id="68583-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68583-133">\<фильтр></span><span class="sxs-lookup"><span data-stu-id="68583-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="68583-134">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="68583-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68583-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="68583-135">Parent Elements</span></span>  
  
|<span data-ttu-id="68583-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="68583-136">Element</span></span>|<span data-ttu-id="68583-137">Описание</span><span class="sxs-lookup"><span data-stu-id="68583-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="68583-138">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68583-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="68583-139">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="68583-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="68583-140">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="68583-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="68583-141">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="68583-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="68583-142">Определяет слушателей, которые собирают, хранят и направляют сообщения.</span><span class="sxs-lookup"><span data-stu-id="68583-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68583-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="68583-143">Remarks</span></span>  
 <span data-ttu-id="68583-144">Классы слушателя, поставляемые с помощью <xref:System.Diagnostics.TraceListener> рамочной программы .NET, происходят из класса.</span><span class="sxs-lookup"><span data-stu-id="68583-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="68583-145">Если вы не `name` указываете атрибут слушателя <xref:System.Diagnostics.TraceListener.Name%2A> трассировки, свойство слушателя трассировки по умолчанию по умолчанию к пустой строке ("").</span><span class="sxs-lookup"><span data-stu-id="68583-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="68583-146">Если в приложении есть только один слушатель, вы можете добавить его, не указывая имя, и вы можете удалить его, указав пустую строку для имени.</span><span class="sxs-lookup"><span data-stu-id="68583-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="68583-147">Однако, если в вашем приложении более одного слушателя, следует указать уникальное имя для каждого слушателя трассы, что позволяет идентифицировать и управлять отдельными слушателями трассировки в коллекции. <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68583-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68583-148">Добавление более одного слушателя трассы одного и того же типа и с тем же именем `Listeners` приводит к добавлению в коллекцию только одного слушателя этого типа и имени.</span><span class="sxs-lookup"><span data-stu-id="68583-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="68583-149">Тем не менее, вы можете программно `Listeners` добавить несколько идентичных слушателей в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="68583-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="68583-150">Значение атрибута `initializeData` зависит от типа создаваемого слушателя.</span><span class="sxs-lookup"><span data-stu-id="68583-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="68583-151">Не все слушатели трасстребуют `initializeData`указания.</span><span class="sxs-lookup"><span data-stu-id="68583-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68583-152">При использовании `initializeData` атрибута можно получить предупреждение компилятора "Атрибут "initializeData" не объявлен".</span><span class="sxs-lookup"><span data-stu-id="68583-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="68583-153">Это предупреждение возникает из-за того, что <xref:System.Diagnostics.TraceListener>настройки конфигурации `initializeData` проверяются на основе абстрактного базового класса, который не распознает атрибут.</span><span class="sxs-lookup"><span data-stu-id="68583-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="68583-154">Как правило, можно проигнорировать это предупреждение для реализации микрослушателя, у которых есть конструктор, который принимает параметр.</span><span class="sxs-lookup"><span data-stu-id="68583-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="68583-155">В следующей таблице показаны слушатели трасс, включенные в `initializeData` рамку .NET, и описывается значение их атрибутов.</span><span class="sxs-lookup"><span data-stu-id="68583-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="68583-156">Класс слушателя трассировки</span><span class="sxs-lookup"><span data-stu-id="68583-156">Trace listener class</span></span>|<span data-ttu-id="68583-157">инициализация значения атрибутаData</span><span class="sxs-lookup"><span data-stu-id="68583-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="68583-158">Значение `useErrorStream` для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.</span><span class="sxs-lookup"><span data-stu-id="68583-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="68583-159">Установите `initializeData` атрибут`true`на "для записи трассировки и отладки вывода в стандартный поток ошибок; установить его`false`на ", чтобы написать на стандартный поток вывода.</span><span class="sxs-lookup"><span data-stu-id="68583-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="68583-160">Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="68583-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="68583-161">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="68583-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="68583-162">Имя файла, который <xref:System.Diagnostics.EventSchemaTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="68583-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="68583-163">Имя файла, который <xref:System.Diagnostics.TextWriterTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="68583-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="68583-164">Имя файла, который <xref:System.Diagnostics.XmlWriterTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="68583-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="68583-165">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="68583-165">Configuration File</span></span>  
 <span data-ttu-id="68583-166">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="68583-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68583-167">Пример</span><span class="sxs-lookup"><span data-stu-id="68583-167">Example</span></span>  
 <span data-ttu-id="68583-168">Ниже приводится следующий `<add>` пример, как `console` `textListener` использовать `Listeners` элементы для `TraceSourceApp`добавления слушателей и в коллекцию для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="68583-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="68583-169">Слушатель `textListener` записывает выход трассировки в файл myListener.log.</span><span class="sxs-lookup"><span data-stu-id="68583-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="68583-170">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="68583-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="68583-171">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="68583-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="68583-172">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="68583-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
