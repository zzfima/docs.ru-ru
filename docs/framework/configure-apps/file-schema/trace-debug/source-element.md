---
title: Элемент <source>
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: b59144f4772c940f8c7e6ca19aa21666069b4b55
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088830"
---
# <a name="source-element"></a><span data-ttu-id="b1695-102">\<исходный > элемент</span><span class="sxs-lookup"><span data-stu-id="b1695-102">\<source> Element</span></span>
<span data-ttu-id="b1695-103">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="b1695-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="b1695-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b1695-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b1695-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b1695-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b1695-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="b1695-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="b1695-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**source >**</span><span class="sxs-lookup"><span data-stu-id="b1695-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b1695-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1695-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1695-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b1695-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b1695-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b1695-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1695-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b1695-111">Attributes</span></span>  
  
|<span data-ttu-id="b1695-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b1695-112">Attribute</span></span>|<span data-ttu-id="b1695-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b1695-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b1695-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b1695-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b1695-115">Задает имя источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="b1695-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="b1695-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b1695-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b1695-117">Задает имя экземпляра переключателя трассировки в приложении.</span><span class="sxs-lookup"><span data-stu-id="b1695-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="b1695-118">Если параметр не определен в элементе `<switches>`, значение указывает уровень для переключателя.</span><span class="sxs-lookup"><span data-stu-id="b1695-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="b1695-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b1695-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b1695-120">Указывает тип переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="b1695-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="b1695-121">При наличии тип должен быть допустимым именем класса и не может быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="b1695-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="b1695-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b1695-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b1695-123">Задает значение для атрибута, зависящего от источника трассировки, определяемого методом <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> для этого источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="b1695-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1695-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b1695-124">Child Elements</span></span>  
  
|<span data-ttu-id="b1695-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="b1695-125">Element</span></span>|<span data-ttu-id="b1695-126">Описание</span><span class="sxs-lookup"><span data-stu-id="b1695-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1695-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="b1695-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="b1695-128">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="b1695-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1695-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b1695-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b1695-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="b1695-130">Element</span></span>|<span data-ttu-id="b1695-131">Описание</span><span class="sxs-lookup"><span data-stu-id="b1695-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b1695-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b1695-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b1695-133">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="b1695-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b1695-134">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="b1695-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1695-135">Заметки</span><span class="sxs-lookup"><span data-stu-id="b1695-135">Remarks</span></span>  
 <span data-ttu-id="b1695-136">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b1695-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1695-137">Пример</span><span class="sxs-lookup"><span data-stu-id="b1695-137">Example</span></span>  
 <span data-ttu-id="b1695-138">В следующем примере показано, как использовать элемент `<source>`, чтобы добавить источник трассировки `mySource` и задать уровень для коммутатора источника с именем `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="b1695-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="b1695-139">Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="b1695-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b1695-140">См. также</span><span class="sxs-lookup"><span data-stu-id="b1695-140">See also</span></span>

- [<span data-ttu-id="b1695-141">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="b1695-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b1695-142">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="b1695-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
