---
title: '&lt;источники&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a9c5c5529e349eca2ba089ed6fb71da4bd48430a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084453"
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="16f06-102">&lt;источники&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="16f06-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="16f06-103">Задает источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="16f06-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="16f06-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="16f06-104">\<configuration></span></span>  
<span data-ttu-id="16f06-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="16f06-105">\<system.diagnostics></span></span>  
<span data-ttu-id="16f06-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="16f06-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f06-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16f06-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16f06-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="16f06-108">Attributes and Elements</span></span>  
 <span data-ttu-id="16f06-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="16f06-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16f06-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="16f06-110">Attributes</span></span>  
 <span data-ttu-id="16f06-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="16f06-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="16f06-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="16f06-112">Child Elements</span></span>  
  
|<span data-ttu-id="16f06-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="16f06-113">Element</span></span>|<span data-ttu-id="16f06-114">Описание</span><span class="sxs-lookup"><span data-stu-id="16f06-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16f06-115">\<source></span><span class="sxs-lookup"><span data-stu-id="16f06-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="16f06-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="16f06-116">Required element.</span></span><br /><br /> <span data-ttu-id="16f06-117">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="16f06-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16f06-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="16f06-118">Parent Elements</span></span>  
  
|<span data-ttu-id="16f06-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="16f06-119">Element</span></span>|<span data-ttu-id="16f06-120">Описание</span><span class="sxs-lookup"><span data-stu-id="16f06-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="16f06-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16f06-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="16f06-122">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="16f06-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16f06-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="16f06-123">Remarks</span></span>  
 <span data-ttu-id="16f06-124">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="16f06-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16f06-125">Пример</span><span class="sxs-lookup"><span data-stu-id="16f06-125">Example</span></span>  
 <span data-ttu-id="16f06-126">В следующем примере показано, как использовать `<sources>` элемент для добавления источника трассировки `mySource` и задать уровень для переключателя источника с именем `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="16f06-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="16f06-127">Добавляется прослушиватель трассировки консоли, записывает сведения трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="16f06-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"   
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"   
                     initializeData="Error" />  
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
  
## <a name="see-also"></a><span data-ttu-id="16f06-128">См. также</span><span class="sxs-lookup"><span data-stu-id="16f06-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="16f06-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="16f06-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="16f06-130">\<source></span><span class="sxs-lookup"><span data-stu-id="16f06-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
