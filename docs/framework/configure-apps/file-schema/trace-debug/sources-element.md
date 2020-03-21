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
ms.openlocfilehash: 2a76816ee73f516b3c7544877a77531acaa8e09c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153273"
---
# <a name="sources-element"></a><span data-ttu-id="5f6e6-102">\<источники> Элемент</span><span class="sxs-lookup"><span data-stu-id="5f6e6-102">\<sources> Element</span></span>
<span data-ttu-id="5f6e6-103">Определяет источники трассировки, которые инициируют отслеживание сообщений.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-103">Specifies trace sources that initiate tracing messages.</span></span>  

<span data-ttu-id="5f6e6-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5f6e6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5f6e6-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="5f6e6-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="5f6e6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<источники>**</span><span class="sxs-lookup"><span data-stu-id="5f6e6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5f6e6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f6e6-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f6e6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5f6e6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5f6e6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f6e6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5f6e6-110">Attributes</span></span>  
 <span data-ttu-id="5f6e6-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5f6e6-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5f6e6-112">Child Elements</span></span>  
  
|<span data-ttu-id="5f6e6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5f6e6-113">Element</span></span>|<span data-ttu-id="5f6e6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5f6e6-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f6e6-115">\<источник></span><span class="sxs-lookup"><span data-stu-id="5f6e6-115">\<source></span></span>](source-element.md)|<span data-ttu-id="5f6e6-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-116">Required element.</span></span><br /><br /> <span data-ttu-id="5f6e6-117">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f6e6-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5f6e6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5f6e6-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="5f6e6-119">Element</span></span>|<span data-ttu-id="5f6e6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5f6e6-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5f6e6-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5f6e6-122">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f6e6-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="5f6e6-123">Remarks</span></span>  
 <span data-ttu-id="5f6e6-124">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f6e6-125">Пример</span><span class="sxs-lookup"><span data-stu-id="5f6e6-125">Example</span></span>  
 <span data-ttu-id="5f6e6-126">Ниже приводится следующий `<sources>` пример, как использовать `mySource` элемент для добавления источника `sourceSwitch`трассировки и для установки уровня для названного источника коммутатора.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="5f6e6-127">Добавлен слушатель трассировки консоли, который записывает информацию о следах на консоль.</span><span class="sxs-lookup"><span data-stu-id="5f6e6-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5f6e6-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5f6e6-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="5f6e6-129">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="5f6e6-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5f6e6-130">\<источник></span><span class="sxs-lookup"><span data-stu-id="5f6e6-130">\<source></span></span>](source-element.md)
