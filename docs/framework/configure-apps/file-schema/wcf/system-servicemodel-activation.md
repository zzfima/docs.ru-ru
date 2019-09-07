---
title: <system.serviceModel.activation>
ms.date: 03/30/2017
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
ms.openlocfilehash: e00bbad452398e7f8f4f50208da572986391fc9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399474"
---
# <a name="systemservicemodelactivation"></a><span data-ttu-id="88640-102">\<> System. serviceModel. Activation</span><span class="sxs-lookup"><span data-stu-id="88640-102">\<system.serviceModel.activation></span></span>
<span data-ttu-id="88640-103">В данном разделе конфигурации представлены параметры конфигурации для средства SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="88640-103">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="88640-104">Элементы конфигурации можно задать в файле SMSvcHost.exe.config.</span><span class="sxs-lookup"><span data-stu-id="88640-104">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="88640-105">В частности в нем содержатся все параметры компьютера, которые необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="88640-105">Specifically, it includes all machine-wide settings that must be configured.</span></span>  

<span data-ttu-id="88640-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="88640-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="88640-107">&nbsp;&nbsp; **\<> System. serviceModel. Activation**</span><span class="sxs-lookup"><span data-stu-id="88640-107">&nbsp;&nbsp;**\<system.serviceModel.activation>**</span></span>  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="88640-108">Образец файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="88640-108">Sample Configuration File</span></span>  
 <span data-ttu-id="88640-109">Далее приведен образец файла конфигурации (SMSvcHost.exe.config), используемый процессом прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="88640-109">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>
  <runtime>
    <gcConcurrent enabled="false" />
  </runtime>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="10"
             maxPendingAccepts="2"
             maxPendingConnections="100"
             receiveTimeout="00:00:10"
             teredoEnabled="false">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
    <net.pipe maxConnectionsPendingDispatch="100"
              maxPendingAccepts="2"
              receiveTimeout="00:00:10">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
    <diagnostics performanceCountersEnabled="true" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="88640-110">См. также</span><span class="sxs-lookup"><span data-stu-id="88640-110">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration>
