---
title: Элемент <source>
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153299"
---
# <a name="source-element"></a><span data-ttu-id="4a98a-102">\<источник> Элемент</span><span class="sxs-lookup"><span data-stu-id="4a98a-102">\<source> Element</span></span>
<span data-ttu-id="4a98a-103">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="4a98a-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="4a98a-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a98a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4a98a-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a98a-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="4a98a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<источники>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a98a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="4a98a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<источник>**</span><span class="sxs-lookup"><span data-stu-id="4a98a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4a98a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a98a-108">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a98a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4a98a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4a98a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4a98a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a98a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4a98a-111">Attributes</span></span>  
  
|<span data-ttu-id="4a98a-112">attribute</span><span class="sxs-lookup"><span data-stu-id="4a98a-112">Attribute</span></span>|<span data-ttu-id="4a98a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4a98a-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="4a98a-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4a98a-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4a98a-115">Определяет сяочниз-имя источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="4a98a-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="4a98a-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4a98a-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4a98a-117">Установить имя экземпляра переключателя трассировки в приложении.</span><span class="sxs-lookup"><span data-stu-id="4a98a-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="4a98a-118">Если переключатель не идентифицирован `<switches>` в элементе, значение определяет уровень для коммутатора.</span><span class="sxs-lookup"><span data-stu-id="4a98a-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="4a98a-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4a98a-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4a98a-120">Определяет тип переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="4a98a-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="4a98a-121">При наличии этого типа он должен быть действительным именем класса и не может быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="4a98a-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="4a98a-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4a98a-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4a98a-123">Определяет значение для специфического атрибута источника трассировки, идентифицированного <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> методом для этого источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="4a98a-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a98a-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4a98a-124">Child Elements</span></span>  
  
|<span data-ttu-id="4a98a-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="4a98a-125">Element</span></span>|<span data-ttu-id="4a98a-126">Описание</span><span class="sxs-lookup"><span data-stu-id="4a98a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a98a-127">\<слушатели></span><span class="sxs-lookup"><span data-stu-id="4a98a-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="4a98a-128">Содержит слушателей, которые собирают, хранят и направляют сообщения.</span><span class="sxs-lookup"><span data-stu-id="4a98a-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a98a-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4a98a-129">Parent Elements</span></span>  
  
|<span data-ttu-id="4a98a-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="4a98a-130">Element</span></span>|<span data-ttu-id="4a98a-131">Описание</span><span class="sxs-lookup"><span data-stu-id="4a98a-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4a98a-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a98a-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4a98a-133">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="4a98a-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4a98a-134">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="4a98a-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a98a-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a98a-135">Remarks</span></span>  
 <span data-ttu-id="4a98a-136">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4a98a-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a98a-137">Пример</span><span class="sxs-lookup"><span data-stu-id="4a98a-137">Example</span></span>  
 <span data-ttu-id="4a98a-138">Ниже приводится следующий `<source>` пример, как использовать `mySource` элемент для добавления источника `sourceSwitch`трассировки и для установки уровня для названного источника коммутатора.</span><span class="sxs-lookup"><span data-stu-id="4a98a-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="4a98a-139">Добавлен слушатель трассировки консоли, который записывает информацию о следах на консоль.</span><span class="sxs-lookup"><span data-stu-id="4a98a-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>
  </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a98a-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a98a-140">See also</span></span>

- [<span data-ttu-id="4a98a-141">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="4a98a-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4a98a-142">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="4a98a-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
