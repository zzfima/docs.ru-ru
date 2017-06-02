---
title: "&lt;add&gt; для &lt;serviceActivations&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;add&gt; для &lt;serviceActivations&gt;
Элемент конфигурации, позволяющий настраивать параметры определения активации виртуальной службы, которые сопоставляются с типами служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  Это позволяет активировать службы, расположенные в WAS\/IIS, без SVC\-файла.  
  
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
  
|Атрибут|Описание|  
|-------------|--------------|  
|factory|Строка, задающая имя типа CLR фабрики, которая формирует элемент активации службы.|  
|service|ServiceType, реализующий службу \(либо полное, либо короткое имя типа\) \(когда оно размещено в папке App\_Code\).|  
|relativeAddress|Относительный адрес в текущем приложении IIS \(например, «Service.svc»\).  В WCF 4.0 этот относительный адрес должен содержать одно из известных расширений файлов \(SVC, XAMLX и т. д.\).  Ни один физический файл не должен существовать по адресу relativeUrl|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceHostingEnvironment\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Раздел конфигурации, в котором описываются параметры активации.|  
  
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
  
 Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.  В relatativeAddress требуется расширение, т. е.  SVC, XOML или XAMLX.  Можно сопоставить пользовательские модули с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любой модуль.  При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC\-файле.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServiceActivationElement>   
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>   
 <xref:System.ServiceModel.ServiceHostingEnvironment>