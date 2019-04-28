---
title: <remove> Элемент для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: adf00394bc0bfe808836e74214003cd2078204e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673684"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="6fcd4-102">\<Удалить > элемент для \<прослушиватели > для \<трассировки ></span><span class="sxs-lookup"><span data-stu-id="6fcd4-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="6fcd4-103">Удаляет прослушиватель из **прослушиватели** коллекции.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="6fcd4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6fcd4-104">\<configuration></span></span>  
<span data-ttu-id="6fcd4-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="6fcd4-105">\<system.diagnostics></span></span>  
<span data-ttu-id="6fcd4-106">\<трассировки ></span><span class="sxs-lookup"><span data-stu-id="6fcd4-106">\<trace></span></span>  
<span data-ttu-id="6fcd4-107">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="6fcd4-107">\<listeners></span></span>  
<span data-ttu-id="6fcd4-108">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="6fcd4-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fcd4-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fcd4-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fcd4-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6fcd4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6fcd4-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fcd4-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6fcd4-112">Attributes</span></span>  
  
|<span data-ttu-id="6fcd4-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6fcd4-113">Attribute</span></span>|<span data-ttu-id="6fcd4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6fcd4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6fcd4-115">**name**</span><span class="sxs-lookup"><span data-stu-id="6fcd4-115">**name**</span></span>|<span data-ttu-id="6fcd4-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="6fcd4-117">Имя прослушивателя для удаления из **прослушиватели** коллекции.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6fcd4-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6fcd4-118">Child Elements</span></span>  
 <span data-ttu-id="6fcd4-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6fcd4-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6fcd4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6fcd4-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="6fcd4-121">Element</span></span>|<span data-ttu-id="6fcd4-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6fcd4-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6fcd4-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="6fcd4-124">Указывает прослушиватель, который собирает, хранилищ и направляет сообщения.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="6fcd4-125">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6fcd4-126">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="6fcd4-127">Настройка службы трассировки ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fcd4-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="6fcd4-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fcd4-129">Удаление <xref:System.Diagnostics.DefaultTraceListener> из `Listeners` коллекции изменяет поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="6fcd4-130">Вызов `Assert` или `Fail` метод, обычно в результате Отображение окна сообщения, но окно сообщения не отображается, если <xref:System.Diagnostics.DefaultTraceListener> не находится в `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fcd4-131">Пример</span><span class="sxs-lookup"><span data-stu-id="6fcd4-131">Example</span></span>  
 <span data-ttu-id="6fcd4-132">В следующем примере показано, как удалить прослушиватель трассировки по умолчанию из трассировки **прослушиватели** коллекции.</span><span class="sxs-lookup"><span data-stu-id="6fcd4-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6fcd4-133">См. также</span><span class="sxs-lookup"><span data-stu-id="6fcd4-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="6fcd4-134">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="6fcd4-134">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
