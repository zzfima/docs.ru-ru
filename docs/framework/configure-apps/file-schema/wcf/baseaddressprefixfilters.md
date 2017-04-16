---
title: "&lt;baseAddressPrefixFilters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;baseAddressPrefixFilters&gt;
Представляет коллекцию элементов конфигурации, которые задают фильтры, предоставляющие механизм выбора соответствующих привязок служб IIS при размещении [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] в службе IIS.  
  
> [!WARNING]
>  \<baseAddressPrefixFilters\> не распознает «localhost», используйте вместо этого полное имя компьютера.  
  
## Синтаксис  
  
```  
  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|Добавляет элемент конфигурации, который задает префиксный фильтр для базовых адресов, используемых узлом службы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceHostingEnvironment\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Определяет, какой тип среда размещения служб создает для конкретного транспорта.|  
  
## Заметки  
 Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой.  Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.  
  
 Веб\-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги.  Доступ к приложению на узле можно осуществлять через одну или несколько привязок службы IIS.  Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки.  Протокол привязки \(например, HTTP\) определяет схему, посредством которой осуществляется связь, а данные привязки \(например, IP\-адрес, порт, заголовок узла\) содержат сведения, используемые для доступа к узлу.  
  
 IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы.  Поскольку размещаемая на узле служба [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] разрешает привязку только к одному базовому адресу для каждой схемы, можно использовать функцию префиксного фильтра, чтобы выбирать необходимый базовый адрес размещенной службы.  Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.  
  
 Например, узел может содержать следующие базовые адреса.  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 Для задания префиксного фильтра на уровне домена приложений можно использовать следующий файл конфигурации.  
  
```  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix=”net.tcp://test1.fabrikam.com:8000”/>  
        <add prefix=”http://test2.fabrikam.com:9000”/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 В этом примере `net.tcp://test1.fabrikam.com:8000` и `http://test2.fabrikam.com:9000` являются единственными базовыми адресами для соответствующих схем, которые могут пропускаться.  
  
 Если префикс не задан, по умолчанию пропускаются все адреса.  При задании префикса разрешается прохождение данных только с соответствующего базового адреса для данной схемы.  
  
> [!NOTE]
>  Фильтр не поддерживает какие\-либо подстановочные знаки.  Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`.  Эти адреса не фильтруются.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>   
 <xref:System.ServiceModel.ServiceHostingEnvironment>   
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)