---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 57fbdd2cf7c398e611f835eeb4e924fb4f3e0c9e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270307"
---
# <a name="service"></a>\<службы >
Элемент `service` содержит параметры для службы Windows Communication Foundation (WCF). Он также содержит конечные точки, предоставляющие доступ к службе.  
  
 \<system.ServiceModel>  
\<Services >  
\<службы >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|behaviorConfiguration|Строка, содержащая имя поведения, которое следует использовать для создания экземпляра службы. Имя поведения должно входить в область действия в точке определения службы. Значение по умолчанию - пустая строка.|  
|имя|Требуемый строковый атрибут, указывающий тип службы, экземпляр которой создается. Этот параметр должен иметь значение допустимого типа. Формат должен быть `Namespace.Class.`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Конечная точка >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|Коллекция элементов `endpoint`, которые обеспечивают доступ к данной службе.|  
|[\<узел >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Задает узел данного экземпляра службы. Это элемент типа <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Корневой элемент всех элементов конфигурации WCF.|  
  
## <a name="remarks"></a>Примечания  
 Службы задаются в разделе `services` файла конфигурации. Сборка может содержать любое число служб. Для каждой службы используется собственный раздел конфигурации `service`. В этом разделе определяются контракт, поведение и конечные точки конкретной службы.  
  
 Элемент `behaviorConfiguration` также является необязательным. Он указывает поведение, используемое службой. Поведение, заданное в данном атрибуте, должно быть связано с поведением в области в том же файле конфигурации.  
  
 Каждая служба предоставляет доступ к одной или нескольким конечным точкам, которые имеют собственные адреса и привязки. Все привязки в файле конфигурации должны быть определены в области файла. Привязки связаны с конечными точками с помощью сочетания атрибутов `name` и `bindingConfiguration`. Атрибут `name` описывает раздел, в котором определена привязка. Атрибут `bindingConfiguration` указывает, какая конфигурация из раздела привязок используется. В разделе привязки может определяться несколько конфигураций.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример конфигурации службы.  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.ServiceElement>
- [Настройка служб](../../../../../docs/framework/wcf/configuring-services.md)
