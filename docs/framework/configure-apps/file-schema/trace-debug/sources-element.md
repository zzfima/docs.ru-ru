---
title: "&lt;источники&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7abe1f4a536d9f321e0a8b300f9542255433c030
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="7dbcc-102">&lt;источники&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="7dbcc-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="7dbcc-103">Задает источники трассировки, инициирующие сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="7dbcc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7dbcc-104">\<configuration></span></span>  
<span data-ttu-id="7dbcc-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="7dbcc-105">\<system.diagnostics></span></span>  
<span data-ttu-id="7dbcc-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="7dbcc-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dbcc-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dbcc-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dbcc-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7dbcc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7dbcc-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dbcc-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7dbcc-110">Attributes</span></span>  
 <span data-ttu-id="7dbcc-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7dbcc-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7dbcc-112">Child Elements</span></span>  
  
|<span data-ttu-id="7dbcc-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="7dbcc-113">Element</span></span>|<span data-ttu-id="7dbcc-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="7dbcc-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dbcc-115">\<source></span><span class="sxs-lookup"><span data-stu-id="7dbcc-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="7dbcc-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-116">Required element.</span></span><br /><br /> <span data-ttu-id="7dbcc-117">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7dbcc-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7dbcc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7dbcc-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="7dbcc-119">Element</span></span>|<span data-ttu-id="7dbcc-120">Описание</span><span class="sxs-lookup"><span data-stu-id="7dbcc-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7dbcc-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7dbcc-122">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dbcc-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="7dbcc-123">Remarks</span></span>  
 <span data-ttu-id="7dbcc-124">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dbcc-125">Пример</span><span class="sxs-lookup"><span data-stu-id="7dbcc-125">Example</span></span>  
 <span data-ttu-id="7dbcc-126">В следующем примере показано, как использовать `<sources>` элемента для добавления источника трассировки `mySource` и задать уровень для переключателя источника с именем `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="7dbcc-127">Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="7dbcc-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7dbcc-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7dbcc-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="7dbcc-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="7dbcc-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="7dbcc-130">\<source></span><span class="sxs-lookup"><span data-stu-id="7dbcc-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
