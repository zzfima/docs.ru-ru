---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 378db238d647be2248c0303f45aece42f7ea5b31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227630"
---
# <a name="baseaddressprefixfilters"></a>\<baseAddressPrefixFilters>
Представляет коллекцию конфигурации, которые элементы, которые задают пройти фильтров, которые обеспечивают механизм для выбора необходимых привязок служб Internet Information Services (IIS), при размещении приложения Windows Communication Foundation (WCF) в службах IIS.  
  
> [!WARNING]
>  \<baseAddressPrefixFilters > не распознает «localhost», вместо этого используйте полное имя компьютера.  
  
 \<system.ServiceModel>  
\<ServiceHostingEnvironment>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|Добавляет элемент конфигурации, который задает префиксный фильтр для базовых адресов, используемых узлом службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Определяет, какой тип среда размещения служб создает для конкретного транспорта.|  
  
## <a name="remarks"></a>Примечания  
 Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой. Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.  
  
 Веб-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги. Доступ к приложению на узле можно осуществлять через одну или несколько привязок службы IIS. Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки. Протокол привязки (например, HTTP) определяет схему, посредством которой осуществляется связь, а данные привязки (например, IP-адрес, порт, заголовок узла) содержат сведения, используемые для доступа к узлу.  
  
 IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы. Так как служба WCF, размещаемая на узле разрешает привязку только к одному базовому адресу для каждой схемы, чтобы выбрать необходимый базовый адрес размещенной службы можно использовать возможность префиксного фильтра. Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.  
  
 Например, узел может содержать следующие базовые адреса.  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 Для задания префиксного фильтра на уровне домена приложений можно использовать следующий файл конфигурации.  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 В этом примере `net.tcp://test1.fabrikam.com:8000` и `http://test2.fabrikam.com:9000` являются единственными базовыми адресами для соответствующих схем, которые могут пропускаться.  
  
 Если префикс не задан, по умолчанию пропускаются все адреса. При задании префикса разрешается прохождение данных только с соответствующего базового адреса для данной схемы.  
  
> [!NOTE]
>  Фильтр не поддерживает какие-либо подстановочные знаки. Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`. Эти адреса не фильтруются.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)
