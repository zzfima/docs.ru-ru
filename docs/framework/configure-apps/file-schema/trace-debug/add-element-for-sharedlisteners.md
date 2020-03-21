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
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153611"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="35b0d-102">\<добавить элемент \<> для> общих слушателей</span><span class="sxs-lookup"><span data-stu-id="35b0d-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="35b0d-103">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="35b0d-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="35b0d-104">`sharedListeners`представляет собой набор слушателей, что любой [ \<источник>](source-element.md) или [ \<след>](trace-element.md) может ссылаться.</span><span class="sxs-lookup"><span data-stu-id="35b0d-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="35b0d-105">По умолчанию слушатели в `sharedListeners` коллекции `Listeners` не помещаются в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="35b0d-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="35b0d-106">Они должны быть добавлены по имени к [ \<источнику>](source-element.md) или [ \<>следа. ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="35b0d-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="35b0d-107">Невозможно получить слушателей в коллекции `sharedListeners` в коде во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="35b0d-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

<span data-ttu-id="35b0d-108">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="35b0d-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="35b0d-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="35b0d-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="35b0d-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<общиеслушатели>**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="35b0d-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="35b0d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="35b0d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="35b0d-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35b0d-112">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35b0d-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="35b0d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="35b0d-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="35b0d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35b0d-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="35b0d-115">Attributes</span></span>  
  
|<span data-ttu-id="35b0d-116">attribute</span><span class="sxs-lookup"><span data-stu-id="35b0d-116">Attribute</span></span>|<span data-ttu-id="35b0d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="35b0d-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="35b0d-118">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="35b0d-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="35b0d-119">Упоняет имя слушателя, который используется для добавления `Listeners` общего слушателя в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="35b0d-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="35b0d-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="35b0d-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="35b0d-121">Определяет тип слушателя.</span><span class="sxs-lookup"><span data-stu-id="35b0d-121">Specifies the type of the listener.</span></span> <span data-ttu-id="35b0d-122">Необходимо использовать строку, соответствующую требованиям, указанным в [определении полностью квалифицированных имен типов.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span><span class="sxs-lookup"><span data-stu-id="35b0d-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="35b0d-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="35b0d-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="35b0d-124">Строка перешла к конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="35b0d-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="35b0d-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="35b0d-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="35b0d-126">Представление строки одного <xref:System.Diagnostics.TraceOptions> или нескольких участников, отодевавав данные, которые должны быть записаны на вывод трассировки.</span><span class="sxs-lookup"><span data-stu-id="35b0d-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="35b0d-127">Несколько элементов разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="35b0d-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="35b0d-128">Значение по умолчанию — "Нет".</span><span class="sxs-lookup"><span data-stu-id="35b0d-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="35b0d-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="35b0d-129">Child Elements</span></span>  
  
|<span data-ttu-id="35b0d-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="35b0d-130">Element</span></span>|<span data-ttu-id="35b0d-131">Описание</span><span class="sxs-lookup"><span data-stu-id="35b0d-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35b0d-132">\<фильтр></span><span class="sxs-lookup"><span data-stu-id="35b0d-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="35b0d-133">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="35b0d-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35b0d-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="35b0d-134">Parent Elements</span></span>  
  
|<span data-ttu-id="35b0d-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="35b0d-135">Element</span></span>|<span data-ttu-id="35b0d-136">Описание</span><span class="sxs-lookup"><span data-stu-id="35b0d-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="35b0d-137">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35b0d-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="35b0d-138">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="35b0d-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="35b0d-139">Коллекция слушателей, на которую может ссылаться любой источник или элемент микро- информации.</span><span class="sxs-lookup"><span data-stu-id="35b0d-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35b0d-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="35b0d-140">Remarks</span></span>  
 <span data-ttu-id="35b0d-141">Классы слушателя, поставляемые с помощью <xref:System.Diagnostics.TraceListener> рамочной программы .NET, происходят из класса.</span><span class="sxs-lookup"><span data-stu-id="35b0d-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="35b0d-142">Значение для `name` атрибута используется для добавления `Listeners` общего слушателя в коллекцию для отслеживания или источника следов.</span><span class="sxs-lookup"><span data-stu-id="35b0d-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="35b0d-143">Значение атрибута `initializeData` зависит от типа создаваемого слушателя.</span><span class="sxs-lookup"><span data-stu-id="35b0d-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="35b0d-144">Не все слушатели трасстребуют `initializeData`указания.</span><span class="sxs-lookup"><span data-stu-id="35b0d-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35b0d-145">При использовании `initializeData` атрибута можно получить предупреждение компилятора "Атрибут "initializeData" не объявлен".</span><span class="sxs-lookup"><span data-stu-id="35b0d-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="35b0d-146">Это предупреждение возникает из-за того, что <xref:System.Diagnostics.TraceListener>настройки конфигурации `initializeData` проверяются на основе абстрактного базового класса, который не распознает атрибут.</span><span class="sxs-lookup"><span data-stu-id="35b0d-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="35b0d-147">Как правило, можно проигнорировать это предупреждение для реализации микрослушателя, у которых есть конструктор, который принимает параметр.</span><span class="sxs-lookup"><span data-stu-id="35b0d-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="35b0d-148">В следующей таблице показаны слушатели трасс, включенные в `initializeData` рамку .NET, и описывается значение их атрибутов.</span><span class="sxs-lookup"><span data-stu-id="35b0d-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="35b0d-149">Класс слушателя трассировки</span><span class="sxs-lookup"><span data-stu-id="35b0d-149">Trace listener class</span></span>|<span data-ttu-id="35b0d-150">инициализация значения атрибутаData</span><span class="sxs-lookup"><span data-stu-id="35b0d-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="35b0d-151">Значение `useErrorStream` для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.</span><span class="sxs-lookup"><span data-stu-id="35b0d-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="35b0d-152">Установите `initializeData` атрибут`true`на "для записи трассировки и отладки вывода в стандартный поток ошибок; установить его`false`на ", чтобы написать на стандартный поток вывода.</span><span class="sxs-lookup"><span data-stu-id="35b0d-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="35b0d-153">Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="35b0d-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="35b0d-154">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="35b0d-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="35b0d-155">Имя файла, который <xref:System.Diagnostics.EventSchemaTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="35b0d-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="35b0d-156">Имя файла, который <xref:System.Diagnostics.TextWriterTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="35b0d-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="35b0d-157">Имя файла, который <xref:System.Diagnostics.XmlWriterTraceListener> пишет.</span><span class="sxs-lookup"><span data-stu-id="35b0d-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="35b0d-158">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="35b0d-158">Configuration File</span></span>  
 <span data-ttu-id="35b0d-159">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="35b0d-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35b0d-160">Пример</span><span class="sxs-lookup"><span data-stu-id="35b0d-160">Example</span></span>  
 <span data-ttu-id="35b0d-161">В следующем примере `<add>` показано, как <xref:System.Diagnostics.TextWriterTraceListener> `textListener` использовать `sharedListeners` элементы для добавления в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="35b0d-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="35b0d-162">`textListener`добавляется по имени `Listeners` в коллекцию `TraceSourceApp`для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="35b0d-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="35b0d-163">Слушатель `textListener` записывает выход трассировки в файл myListener.log.</span><span class="sxs-lookup"><span data-stu-id="35b0d-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35b0d-164">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="35b0d-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="35b0d-165">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="35b0d-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="35b0d-166">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="35b0d-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
