---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 43461f23476d1c387cec06f9aee893defa634201
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceactivationsgt"></a>&lt;serviceActivations&gt;
Элемент конфигурации, позволяющий добавлять настройки, которые определяют параметры активации виртуальной службы, сопоставляющиеся с типами служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]. Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.  
  
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
