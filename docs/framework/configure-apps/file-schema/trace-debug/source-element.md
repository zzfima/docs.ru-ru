---
title: Элемент <source>
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 8860f5d3ed7ee0c04d1e8afd7614f3f73b470808
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673710"
---
# <a name="source-element"></a><span data-ttu-id="2da09-102">\<Источник > элемент</span><span class="sxs-lookup"><span data-stu-id="2da09-102">\<source> Element</span></span>
<span data-ttu-id="2da09-103">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="2da09-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="2da09-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2da09-104">\<configuration></span></span>  
<span data-ttu-id="2da09-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="2da09-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2da09-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="2da09-106">\<sources></span></span>  
<span data-ttu-id="2da09-107">\<Источник ></span><span class="sxs-lookup"><span data-stu-id="2da09-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da09-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2da09-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2da09-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2da09-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2da09-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2da09-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2da09-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2da09-111">Attributes</span></span>  
  
|<span data-ttu-id="2da09-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2da09-112">Attribute</span></span>|<span data-ttu-id="2da09-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2da09-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="2da09-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2da09-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2da09-115">Задает имя источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="2da09-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="2da09-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2da09-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2da09-117">Задает имя экземпляра коммутатора трассировки в приложении.</span><span class="sxs-lookup"><span data-stu-id="2da09-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="2da09-118">Если параметр не указан в `<switches>` элемент, значение задает уровень для переключателя.</span><span class="sxs-lookup"><span data-stu-id="2da09-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="2da09-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2da09-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2da09-120">Указывает тип переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="2da09-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="2da09-121">Если он имеется, тип должен быть допустимым именем класса и не может быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="2da09-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="2da09-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2da09-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2da09-123">Указывает значение атрибута зависящие от источника трассировки, идентифицируемый <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> метод для этого источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="2da09-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2da09-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2da09-124">Child Elements</span></span>  
  
|<span data-ttu-id="2da09-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="2da09-125">Element</span></span>|<span data-ttu-id="2da09-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2da09-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2da09-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="2da09-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="2da09-128">Содержит прослушиватели, сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="2da09-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2da09-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2da09-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2da09-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="2da09-130">Element</span></span>|<span data-ttu-id="2da09-131">Описание</span><span class="sxs-lookup"><span data-stu-id="2da09-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2da09-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2da09-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2da09-133">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="2da09-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="2da09-134">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="2da09-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2da09-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="2da09-135">Remarks</span></span>  
 <span data-ttu-id="2da09-136">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="2da09-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2da09-137">Пример</span><span class="sxs-lookup"><span data-stu-id="2da09-137">Example</span></span>  
 <span data-ttu-id="2da09-138">В следующем примере показано, как использовать `<source>` элемент для добавления источника трассировки `mySource` и задать уровень для переключателя источника с именем `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="2da09-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="2da09-139">Добавляется прослушиватель трассировки консоли, записывает сведения трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="2da09-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2da09-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2da09-140">See also</span></span>

- [<span data-ttu-id="2da09-141">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="2da09-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="2da09-142">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="2da09-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
