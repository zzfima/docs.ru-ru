---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: cdf3264d1631db8e61bbcc4f6febd7008099251b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968717"
---
# <a name="baseaddressprefixfilters"></a>\<baseAddressPrefixFilters >
Представляет коллекцию элементов конфигурации, задающих сквозные фильтры, которые предоставляют механизм для выбора соответствующих привязок службы IIS (IIS) при размещении приложения Windows Communication Foundation (WCF) в службах IIS.  
  
> [!WARNING]
> \<baseAddressPrefixFilters > не распознает "localhost"; Вместо этого используйте полное имя компьютера.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<baseAddressPrefixFilters >**  
  
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
|[\<add>](add-of-baseaddressprefixfilter.md)|Добавляет элемент конфигурации, который задает префиксный фильтр для базовых адресов, используемых узлом службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment >](servicehostingenvironment.md)|Определяет, какой тип среда размещения служб создает для конкретного транспорта.|  
  
## <a name="remarks"></a>Заметки  
 Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой. Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.  
  
 Веб-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги. Доступ к приложению на узле можно осуществлять через одну или несколько привязок службы IIS. Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки. Протокол привязки (например, HTTP) определяет схему, посредством которой осуществляется связь, а данные привязки (например, IP-адрес, порт, заголовок узла) содержат сведения, используемые для доступа к узлу.  
  
 IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы. Так как служба WCF, размещенная на сайте, допускает привязку только к одному базовому адресу для каждой схемы, можно использовать функцию фильтрации префиксов, чтобы выбрать необходимый базовый адрес размещенной службы. Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.  
  
 Например, сайт может содержать следующие базовые адреса:
  
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
> Фильтр не поддерживает какие-либо подстановочные знаки. Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`. Эти адреса не фильтруются.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [Размещение](../../../wcf/feature-details/hosting.md)
