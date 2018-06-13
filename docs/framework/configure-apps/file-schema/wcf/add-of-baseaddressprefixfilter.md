---
title: '&lt;add&gt; для &lt;baseAddressPrefixFilter&gt;'
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: e4408488036be210e3a8b9cf8b8f8f8c2e669a1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365193"
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a>&lt;add&gt; для &lt;baseAddressPrefixFilter&gt;
Представляет элемент конфигурации, который задает проходной фильтр, предоставляющий механизм выбора соответствующих привязок служб Internet Information Services (IIS), при размещении приложения Windows Communication Foundation (WCF) в службах IIS.  
  
 \<система. ServiceModel >  
\<ServiceHostingEnvironment >  
\<baseAddressPrefixFilters >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|prefix|Универсальный код ресурса (URI), совпадающий с частью базового адреса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|Коллекция элементов конфигурации, которые задают проходные фильтры, предоставляющие механизм выбора необходимых привязок служб IIS при размещении приложения Windows Communication Foundation (WCF) в службах IIS.|  
  
## <a name="remarks"></a>Примечания  
 Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой. Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.  
  
 Веб-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги. Доступ к приложению на узле можно осуществлять через одну или несколько привязок IIS. Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки. Протокол привязки (например, HTTP) определяет схему, посредством которой осуществляется связь, а данные привязки (например, IP-адрес, порт, заголовок узла) содержат сведения, используемые для доступа к узлу.  
  
 IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы. Поскольку размещаемая на узле службы WCF допускает привязку только к одному базовому адресу для каждой схемы, можно использовать функцию префиксного фильтра, чтобы выбирать необходимые базовые адреса размещенной службы. Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.  
  
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
        <add prefix="net.tcp://test1.fabrikam.com:8000"/>  
        <add prefix="http://test2.fabrikam.com:9000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 В этом примере `net.tcp://test1.fabrikam.com:8000` и `http://test2.fabrikam.com:9000` являются единственными базовыми адресами соответствующих схем, для которых разрешено прохождение данных.  
  
 Если префикс не задан, по умолчанию пропускаются все адреса. При задании префикса разрешается прохождение данных только с соответствующего базового адреса для данной схемы.  
  
> [!NOTE]
>  Фильтр не поддерживает какие-либо подстановочные знаки. Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`. Эти адреса не фильтруются.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)
