---
title: '&lt;NET.TCP&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 9e44ddcc3a3e983abe6e36d4b6095c5c4a67529f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349887"
---
# <a name="ltnettcpgt"></a><span data-ttu-id="c651d-102">&lt;NET.TCP&gt;</span><span class="sxs-lookup"><span data-stu-id="c651d-102">&lt;net.tcp&gt;</span></span>
<span data-ttu-id="c651d-103">Задает параметры конфигурации для службы общего доступа к портам Net.Tcp, которая позволяет нескольким процессам совместно использовать один и тот же порт протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="c651d-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="c651d-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="c651d-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="c651d-105">\<NET.TCP ></span><span class="sxs-lookup"><span data-stu-id="c651d-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c651d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c651d-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="c651d-107">Тип</span><span class="sxs-lookup"><span data-stu-id="c651d-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c651d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c651d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c651d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c651d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c651d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c651d-110">Attributes</span></span>  
  
|<span data-ttu-id="c651d-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c651d-111">Attribute</span></span>|<span data-ttu-id="c651d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c651d-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="c651d-113">Целое число, указывающее максимальное количество необработанных соединений, принятых от общего соединения, но еще не переданных службам Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c651d-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="c651d-114">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="c651d-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="c651d-115">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="c651d-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="c651d-116">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="c651d-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="c651d-117">Максимальное число подключений, принятия которых приложением может ожидать прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="c651d-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="c651d-118">После превышения значения этой квоты новые входящие подключения сбрасываются, а не ожидают принятия.</span><span class="sxs-lookup"><span data-stu-id="c651d-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="c651d-119">Функции подключения (такие как безопасность сообщения) могут вынудить клиента открыть несколько подключений.</span><span class="sxs-lookup"><span data-stu-id="c651d-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="c651d-120">При установке значения квоты администраторы службы должны учитывать возможность установления дополнительных подключений.</span><span class="sxs-lookup"><span data-stu-id="c651d-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="c651d-121">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="c651d-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="c651d-122">Значение `TimeSpan`, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="c651d-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="c651d-123">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="c651d-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="c651d-124">Логическое значение, указывающее, использует ли служба совместного использования портов службу Microsoft Teredo для прослушивания TCP портов от имени служб WCF.</span><span class="sxs-lookup"><span data-stu-id="c651d-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="c651d-125">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="c651d-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c651d-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c651d-126">Child Elements</span></span>  
  
|<span data-ttu-id="c651d-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="c651d-127">Element</span></span>|<span data-ttu-id="c651d-128">Описание</span><span class="sxs-lookup"><span data-stu-id="c651d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c651d-129">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="c651d-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="c651d-130">Коллекция элементов конфигурации, которые содержат `securityIdentifier` атрибут, чтобы задать учетные записи пользователей для процессов служб WCF, которые имеют доступ к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="c651d-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c651d-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c651d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c651d-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="c651d-132">Element</span></span>|<span data-ttu-id="c651d-133">Описание</span><span class="sxs-lookup"><span data-stu-id="c651d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c651d-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="c651d-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="c651d-135">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="c651d-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c651d-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="c651d-136">Remarks</span></span>  
 <span data-ttu-id="c651d-137">Дополнительные сведения на совместное использование порта см. в разделе [общего доступа к портам Net.TCP](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded).</span><span class="sxs-lookup"><span data-stu-id="c651d-137">For more information on port sharing, see [Net.TCP Port Sharing](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded).</span></span> <span data-ttu-id="c651d-138">Настройка службы совместного использования портов см [Настройка доступа к портам NET.TCP](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span><span class="sxs-lookup"><span data-stu-id="c651d-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c651d-139">См. также</span><span class="sxs-lookup"><span data-stu-id="c651d-139">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [<span data-ttu-id="c651d-140">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="c651d-140">Net.TCP Port Sharing</span></span>](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [<span data-ttu-id="c651d-141">Настройка службы совместного использования портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="c651d-141">Configuring the Net.TCP Port Sharing Service</span></span>](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
