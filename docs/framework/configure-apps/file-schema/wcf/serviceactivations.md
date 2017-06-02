---
title: "&lt;serviceActivations&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;serviceActivations&gt;
Элемент конфигурации, позволяющий добавлять настройки, которые определяют параметры активации виртуальной службы, сопоставляющиеся с типами служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  Это позволяет активировать службы, расположенные в WAS\/IIS, без SVC\-файла.  
  
## Синтаксис  
  
```  
  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|Добавляет элемент конфигурации, который задает активацию приложения службы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceHostingEnvironment\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Определяет, какой тип среда размещения служб создает для конкретного транспорта.|  
  
## Заметки  
 В следующем примере показано, как настроить параметры активации в файле web.config.  
  
```  
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
  
 Использование этой конфигурации позволяет активировать GreetingService без SVC\-файла.  
  
 Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.  Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.  Помимо этого, `serviceHostingEnvironment` является наследуемым разделом machinetoApplication.  Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.  
  
 Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.  В relatativeAddress требуется расширение  SVC, XOML или XAMLX.  Можно сопоставить пользовательские модули с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любой модуль.  При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC\-файле.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>   
 <xref:System.ServiceModel.ServiceHostingEnvironment>