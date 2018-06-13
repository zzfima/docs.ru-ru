---
title: '&lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: c62f2bd1a34aca31ea9f9d5de17840f2967b269c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748533"
---
# <a name="ltserviceactivationsgt"></a>&lt;serviceActivations&gt;
Элемент конфигурации, позволяющий добавлять параметры, определяющие параметры активации виртуальной службы, которые сопоставляются с типами службы Windows Communication Foundation (WCF). Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.  
  
 \<система. ServiceModel >  
\<serviceHostingEnvironment >  
\<serviceActivations >  
  
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
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|Добавляет элемент конфигурации, который задает активацию приложения службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Определяет, какой тип среда размещения служб создает для конкретного транспорта.|  
  
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
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
