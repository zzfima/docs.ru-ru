---
title: Элемент <add> для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 0818d7ec248b210f215759069b9f69a3e29637f5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699405"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="f074e-102">Элемент \<add > для > \<listeners для \<source ></span><span class="sxs-lookup"><span data-stu-id="f074e-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="f074e-103">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="f074e-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="f074e-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f074e-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f074e-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="f074e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="f074e-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="f074e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="f074e-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="f074e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="f074e-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="f074e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="f074e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="f074e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f074e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f074e-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f074e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f074e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f074e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f074e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f074e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f074e-113">Attributes</span></span>  
  
|<span data-ttu-id="f074e-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f074e-114">Attribute</span></span>|<span data-ttu-id="f074e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f074e-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="f074e-116">Обязательный атрибут, если вы не ссылаетесь на прослушиватель в коллекции `sharedListeners`, в этом случае необходимо ссылаться на него по имени (см. [Пример](#example)).</span><span class="sxs-lookup"><span data-stu-id="f074e-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="f074e-117">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="f074e-117">Specifies the type of the listener.</span></span> <span data-ttu-id="f074e-118">Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="f074e-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="f074e-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f074e-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f074e-120">Строка, передаваемая конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="f074e-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="f074e-121">Если у класса нет конструктора, принимающего строку, возникает исключение <xref:System.Configuration.ConfigurationException>.</span><span class="sxs-lookup"><span data-stu-id="f074e-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="f074e-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f074e-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f074e-123">Указывает имя прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="f074e-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="f074e-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f074e-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f074e-125">Задает значение свойства <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> для прослушивателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="f074e-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="f074e-126">[настраиваемые атрибуты]</span><span class="sxs-lookup"><span data-stu-id="f074e-126">[custom attributes]</span></span>|<span data-ttu-id="f074e-127">Необязательные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="f074e-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="f074e-128">Задает значение для атрибутов прослушивателя, определенных методом <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> для этого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="f074e-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="f074e-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> является примером дополнительного атрибута, уникального для класса <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="f074e-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f074e-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f074e-130">Child Elements</span></span>  
  
|<span data-ttu-id="f074e-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="f074e-131">Element</span></span>|<span data-ttu-id="f074e-132">Описание</span><span class="sxs-lookup"><span data-stu-id="f074e-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f074e-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="f074e-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="f074e-134">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="f074e-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f074e-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f074e-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f074e-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="f074e-136">Element</span></span>|<span data-ttu-id="f074e-137">Описание</span><span class="sxs-lookup"><span data-stu-id="f074e-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f074e-138">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f074e-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f074e-139">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="f074e-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="f074e-140">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="f074e-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="f074e-141">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="f074e-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="f074e-142">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="f074e-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f074e-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="f074e-143">Remarks</span></span>  
 <span data-ttu-id="f074e-144">Классы прослушивателей, поставляемые с .NET Framework, являются производными от класса <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="f074e-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="f074e-145">Если не указать атрибут `name` прослушивателя трассировки, свойство <xref:System.Diagnostics.TraceListener.Name%2A> прослушивателя трассировки по умолчанию имеет пустую строку ("").</span><span class="sxs-lookup"><span data-stu-id="f074e-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="f074e-146">Если у приложения есть только один прослушиватель, его можно добавить без указания имени, и его можно удалить, указав в качестве имени пустую строку.</span><span class="sxs-lookup"><span data-stu-id="f074e-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="f074e-147">Однако если приложение имеет несколько прослушивателей, необходимо указать уникальное имя для каждого прослушивателя трассировки, что позволяет определять отдельные прослушиватели трассировки в коллекции <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="f074e-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f074e-148">Добавление нескольких прослушивателей трассировки одного и того же типа и с одним и тем же именем приводит к тому, что только один прослушиватель трассировки этого типа и имя добавляются в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="f074e-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="f074e-149">Однако можно программно добавить несколько идентичных прослушивателей в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="f074e-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="f074e-150">Значение для атрибута `initializeData` зависит от типа создаваемого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="f074e-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="f074e-151">Не все прослушиватели трассировки должны указывать `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="f074e-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f074e-152">При использовании атрибута `initializeData` может появиться предупреждение компилятора "атрибут initializeData не объявлен".</span><span class="sxs-lookup"><span data-stu-id="f074e-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="f074e-153">Это предупреждение возникает, если параметры конфигурации проверяются по абстрактному базовому классу <xref:System.Diagnostics.TraceListener>, который не распознает атрибут `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="f074e-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="f074e-154">Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="f074e-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="f074e-155">В следующей таблице показаны прослушиватели трассировки, которые включены в .NET Framework и описаны значения их атрибутов `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="f074e-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="f074e-156">Класс прослушивателя трассировки</span><span class="sxs-lookup"><span data-stu-id="f074e-156">Trace listener class</span></span>|<span data-ttu-id="f074e-157">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="f074e-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="f074e-158">Значение `useErrorStream` для конструктора <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="f074e-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="f074e-159">Задайте для атрибута `initializeData` значение "`true`", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок. Задайте для него значение "`false`", чтобы выполнить запись в стандартный выходной поток.</span><span class="sxs-lookup"><span data-stu-id="f074e-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="f074e-160">Имя файла, в который записывается <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="f074e-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="f074e-161">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="f074e-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="f074e-162">Имя файла, в который записывается <xref:System.Diagnostics.EventSchemaTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="f074e-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="f074e-163">Имя файла, в который записывается <xref:System.Diagnostics.TextWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="f074e-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="f074e-164">Имя файла, в который записывается <xref:System.Diagnostics.XmlWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="f074e-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="f074e-165">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="f074e-165">Configuration File</span></span>  
 <span data-ttu-id="f074e-166">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f074e-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f074e-167">Пример</span><span class="sxs-lookup"><span data-stu-id="f074e-167">Example</span></span>  
 <span data-ttu-id="f074e-168">В следующем примере показано, как использовать элементы `<add>` для добавления прослушивателей `console` и `textListener` в коллекцию `Listeners` для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="f074e-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="f074e-169">Прослушиватель `textListener` записывает выходные данные трассировки в файл myListener. log.</span><span class="sxs-lookup"><span data-stu-id="f074e-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f074e-170">См. также</span><span class="sxs-lookup"><span data-stu-id="f074e-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="f074e-171">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="f074e-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f074e-172">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="f074e-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
