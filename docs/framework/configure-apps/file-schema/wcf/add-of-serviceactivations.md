---
title: "&lt;add&gt; для &lt;serviceActivations&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 956134f0db25055fb9a2f9317a770989cfdab67f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a>&lt;add&gt; для &lt;serviceActivations&gt;
Элемент конфигурации, позволяющий настраивать параметры определения активации виртуальной службы, которые сопоставляются с типами служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]. Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.  
  
 \<система. ServiceModel >  
\<ServiceHostingEnvironment >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|factory|Строка, задающая имя типа CLR фабрики, которая формирует элемент активации службы.|  
|service|ServiceType, реализующий службу (либо полное, либо короткое имя типа) (когда оно размещено в папке App_Code).|  
|relativeAddress|Относительный адрес в текущем приложении IIS (например, «Service.svc»). В WCF 4.0 этот относительный адрес должен содержать одно из известных расширений файлов (SVC, XAMLX и т. д.). Ни один физический файл не должен существовать по адресу relativeUrl|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Раздел конфигурации, в котором описываются параметры активации.|  
  
## <a name="remarks"></a>Примечания  
 В следующем примере показано, как настроить параметры активации в файле web.config.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.  
  
 Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения. Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения. Помимо этого, `serviceHostingEnvironment` является наследуемым разделом machinetoApplication. Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.  
  
 Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP. Требует расширений в relatativeAddress, т.е. SVC, XOML или XAMLX. Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение. При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceActivationElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
