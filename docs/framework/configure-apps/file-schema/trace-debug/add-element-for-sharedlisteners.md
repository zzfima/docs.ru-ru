---
title: Элемент <add> для <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: c4b83834fb7aaf64a696b85bd2c8da47cfba2397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927211"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="bc96c-102">\<Добавление элемента > для \<шаредлистенерс ></span><span class="sxs-lookup"><span data-stu-id="bc96c-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="bc96c-103">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="bc96c-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="bc96c-104">`sharedListeners`— Это коллекция прослушивателей, на которые могут ссылаться любые [ \<исходные >](source-element.md) или [ \<> трассировки](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="bc96c-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="bc96c-105">По умолчанию прослушиватели в `sharedListeners` коллекции не помещаются `Listeners` в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="bc96c-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="bc96c-106">Они должны быть добавлены по имени в [ \<исходный >](source-element.md) или [ \<> трассировки](trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="bc96c-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="bc96c-107">Невозможно получить прослушиватели в `sharedListeners` коллекции в коде во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc96c-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="bc96c-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bc96c-108">\<configuration></span></span>  
<span data-ttu-id="bc96c-109">&nbsp;&nbsp;\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="bc96c-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="bc96c-110">&nbsp;&nbsp;&nbsp;&nbsp;\<Элемент > Шаредлистенерс</span><span class="sxs-lookup"><span data-stu-id="bc96c-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="bc96c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<Добавить ></span><span class="sxs-lookup"><span data-stu-id="bc96c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc96c-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc96c-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc96c-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bc96c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bc96c-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bc96c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc96c-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc96c-115">Attributes</span></span>  
  
|<span data-ttu-id="bc96c-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bc96c-116">Attribute</span></span>|<span data-ttu-id="bc96c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="bc96c-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bc96c-118">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bc96c-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc96c-119">Указывает имя прослушивателя, который используется для добавления общего прослушивателя в `Listeners` коллекцию.</span><span class="sxs-lookup"><span data-stu-id="bc96c-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="bc96c-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bc96c-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc96c-121">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="bc96c-121">Specifies the type of the listener.</span></span> <span data-ttu-id="bc96c-122">Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="bc96c-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="bc96c-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bc96c-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bc96c-124">Строка, передаваемая конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="bc96c-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="bc96c-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bc96c-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="bc96c-126">Строковое представление одного или нескольких <xref:System.Diagnostics.TraceOptions> элементов перечисления, которое указывает данные, записываемые в выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="bc96c-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="bc96c-127">Несколько элементов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="bc96c-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="bc96c-128">Значение по умолчанию — None.</span><span class="sxs-lookup"><span data-stu-id="bc96c-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="bc96c-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bc96c-129">Child Elements</span></span>  
  
|<span data-ttu-id="bc96c-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc96c-130">Element</span></span>|<span data-ttu-id="bc96c-131">Описание</span><span class="sxs-lookup"><span data-stu-id="bc96c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc96c-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="bc96c-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="bc96c-133">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="bc96c-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc96c-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bc96c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="bc96c-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc96c-135">Element</span></span>|<span data-ttu-id="bc96c-136">Описание</span><span class="sxs-lookup"><span data-stu-id="bc96c-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bc96c-137">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc96c-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bc96c-138">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="bc96c-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="bc96c-139">Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="bc96c-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc96c-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc96c-140">Remarks</span></span>  
 <span data-ttu-id="bc96c-141">Классы прослушивателей, поставляемые с .NET Framework, являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="bc96c-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="bc96c-142">Значение `name` атрибута используется для добавления общего прослушивателя `Listeners` в коллекцию либо для трассировки, либо для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="bc96c-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="bc96c-143">Значение `initializeData` атрибута зависит от типа создаваемого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="bc96c-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="bc96c-144">Не все прослушиватели трассировки нуждаются в указании `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="bc96c-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc96c-145">При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен".</span><span class="sxs-lookup"><span data-stu-id="bc96c-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="bc96c-146">Это предупреждение возникает из-за того, что параметры конфигурации проверяются <xref:System.Diagnostics.TraceListener>по абстрактному базовому классу, который не `initializeData` распознает атрибут.</span><span class="sxs-lookup"><span data-stu-id="bc96c-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="bc96c-147">Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="bc96c-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="bc96c-148">В следующей таблице показаны прослушиватели трассировки, которые включены в состав .NET Framework и описываются значения их `initializeData` атрибутов.</span><span class="sxs-lookup"><span data-stu-id="bc96c-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="bc96c-149">Класс прослушивателя трассировки</span><span class="sxs-lookup"><span data-stu-id="bc96c-149">Trace listener class</span></span>|<span data-ttu-id="bc96c-150">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="bc96c-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="bc96c-151">`useErrorStream` Значение<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> для конструктора.</span><span class="sxs-lookup"><span data-stu-id="bc96c-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="bc96c-152">Задайте для`true``false`атрибута значение "", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок; задайте для него значение "", чтобы выполнить запись в стандартный выходной поток. `initializeData`</span><span class="sxs-lookup"><span data-stu-id="bc96c-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="bc96c-153">Имя файла, <xref:System.Diagnostics.DelimitedListTraceListener> в который производится запись.</span><span class="sxs-lookup"><span data-stu-id="bc96c-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="bc96c-154">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="bc96c-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="bc96c-155">Имя файла, в который <xref:System.Diagnostics.EventSchemaTraceListener> производится запись.</span><span class="sxs-lookup"><span data-stu-id="bc96c-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="bc96c-156">Имя файла, в который <xref:System.Diagnostics.TextWriterTraceListener> производится запись.</span><span class="sxs-lookup"><span data-stu-id="bc96c-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="bc96c-157">Имя файла, в который <xref:System.Diagnostics.XmlWriterTraceListener> производится запись.</span><span class="sxs-lookup"><span data-stu-id="bc96c-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="bc96c-158">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="bc96c-158">Configuration File</span></span>  
 <span data-ttu-id="bc96c-159">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="bc96c-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc96c-160">Пример</span><span class="sxs-lookup"><span data-stu-id="bc96c-160">Example</span></span>  
 <span data-ttu-id="bc96c-161">В следующем примере показано, как использовать `<add>` элементы для <xref:System.Diagnostics.TextWriterTraceListener> `textListener` добавления `sharedListeners` в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="bc96c-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="bc96c-162">`textListener`добавляется по имени в `Listeners` коллекцию для источника `TraceSourceApp`трассировки.</span><span class="sxs-lookup"><span data-stu-id="bc96c-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="bc96c-163">`textListener` Прослушиватель записывает выходные данные трассировки в файл myListener. log.</span><span class="sxs-lookup"><span data-stu-id="bc96c-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc96c-164">См. также</span><span class="sxs-lookup"><span data-stu-id="bc96c-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="bc96c-165">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="bc96c-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bc96c-166">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="bc96c-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
