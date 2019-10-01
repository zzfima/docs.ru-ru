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
ms.openlocfilehash: 0ca35d9be5e1eaf36a2c9cae99efc2736ef3403d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699209"
---
# <a name="sources-element"></a><span data-ttu-id="a165e-102">Элемент > @no__t 0sources</span><span class="sxs-lookup"><span data-stu-id="a165e-102">\<sources> Element</span></span>
<span data-ttu-id="a165e-103">Указывает источники трассировки, инициирующие сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="a165e-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
[<span data-ttu-id="a165e-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a165e-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a165e-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a165e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="a165e-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<sources >**</span><span class="sxs-lookup"><span data-stu-id="a165e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a165e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a165e-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a165e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a165e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a165e-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a165e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a165e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a165e-110">Attributes</span></span>  
 <span data-ttu-id="a165e-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="a165e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a165e-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a165e-112">Child Elements</span></span>  
  
|<span data-ttu-id="a165e-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="a165e-113">Element</span></span>|<span data-ttu-id="a165e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a165e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a165e-115">\<source></span><span class="sxs-lookup"><span data-stu-id="a165e-115">\<source></span></span>](source-element.md)|<span data-ttu-id="a165e-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a165e-116">Required element.</span></span><br /><br /> <span data-ttu-id="a165e-117">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="a165e-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a165e-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a165e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a165e-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="a165e-119">Element</span></span>|<span data-ttu-id="a165e-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a165e-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a165e-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a165e-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a165e-122">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="a165e-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a165e-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="a165e-123">Remarks</span></span>  
 <span data-ttu-id="a165e-124">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="a165e-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a165e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="a165e-125">Example</span></span>  
 <span data-ttu-id="a165e-126">В следующем примере показано, как использовать элемент `<sources>`, чтобы добавить источник трассировки `mySource` и задать уровень для коммутатора источника с именем `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="a165e-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="a165e-127">Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="a165e-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a165e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a165e-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="a165e-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="a165e-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a165e-130">\<source></span><span class="sxs-lookup"><span data-stu-id="a165e-130">\<source></span></span>](source-element.md)
