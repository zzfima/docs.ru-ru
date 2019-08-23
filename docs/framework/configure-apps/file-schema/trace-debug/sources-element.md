---
title: Элемент <sources>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 73d4eb2741bdbe5a07704ca0f3b2f779706e66dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926959"
---
# <a name="sources-element"></a><span data-ttu-id="33826-102">\<sources >, элемент</span><span class="sxs-lookup"><span data-stu-id="33826-102">\<sources> Element</span></span>
<span data-ttu-id="33826-103">Указывает источники трассировки, инициирующие сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="33826-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="33826-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="33826-104">\<configuration></span></span>  
<span data-ttu-id="33826-105">\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="33826-105">\<system.diagnostics></span></span>  
<span data-ttu-id="33826-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="33826-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33826-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33826-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33826-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33826-108">Attributes and Elements</span></span>  
 <span data-ttu-id="33826-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="33826-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33826-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33826-110">Attributes</span></span>  
 <span data-ttu-id="33826-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="33826-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33826-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33826-112">Child Elements</span></span>  
  
|<span data-ttu-id="33826-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="33826-113">Element</span></span>|<span data-ttu-id="33826-114">Описание</span><span class="sxs-lookup"><span data-stu-id="33826-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33826-115">\<source></span><span class="sxs-lookup"><span data-stu-id="33826-115">\<source></span></span>](source-element.md)|<span data-ttu-id="33826-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="33826-116">Required element.</span></span><br /><br /> <span data-ttu-id="33826-117">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="33826-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33826-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33826-118">Parent Elements</span></span>  
  
|<span data-ttu-id="33826-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="33826-119">Element</span></span>|<span data-ttu-id="33826-120">Описание</span><span class="sxs-lookup"><span data-stu-id="33826-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="33826-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="33826-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="33826-122">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="33826-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33826-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="33826-123">Remarks</span></span>  
 <span data-ttu-id="33826-124">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="33826-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33826-125">Пример</span><span class="sxs-lookup"><span data-stu-id="33826-125">Example</span></span>  
 <span data-ttu-id="33826-126">В следующем примере показано, как с помощью `<sources>` элемента добавить источник `mySource` трассировки и задать уровень для коммутатора источника с именем `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="33826-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="33826-127">Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="33826-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="33826-128">См. также</span><span class="sxs-lookup"><span data-stu-id="33826-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="33826-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="33826-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="33826-130">\<source></span><span class="sxs-lookup"><span data-stu-id="33826-130">\<source></span></span>](source-element.md)
