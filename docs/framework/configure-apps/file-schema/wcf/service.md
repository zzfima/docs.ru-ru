---
title: '&lt;Службы&gt;'
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 6e83e988920d24c6fe7615e40334919caf21652e
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2018
ms.locfileid: "34059034"
---
# <a name="ltservicegt"></a>&lt;Службы&gt;
Элемент `service` содержит параметры для службы Windows Communication Foundation (WCF). Он также содержит конечные точки, предоставляющие доступ к службе.  
  
 \<система. ServiceModel >  
\<службы >  
\<Служба >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<service behaviorConfiguration=String"  
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
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Конечная точка >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|Коллекция элементов `endpoint`, которые обеспечивают доступ к данной службе.|  
|[\<узел >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Задает узел данного экземпляра службы. Это элемент типа <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<службы >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Корневой элемент всех элементов конфигурации WCF.|  
  
## <a name="remarks"></a>Примечания  
 Службы задаются в разделе `services` файла конфигурации. Сборка может содержать любое число служб. Для каждой службы используется собственный раздел конфигурации `service`. В этом разделе определяются контракт, поведение и конечные точки конкретной службы.  
  
 Элемент `behaviorConfiguration` также является необязательным. Он указывает поведение, используемое службой. Поведение, заданное в данном атрибуте, должно быть связано с поведением в области в том же файле конфигурации.  
  
 Каждая служба предоставляет доступ к одной или нескольким конечным точкам, которые имеют собственные адреса и привязки. Все привязки в файле конфигурации должны быть определены в области файла. Привязки связаны с конечными точками с помощью сочетания атрибутов `name` и `bindingConfiguration`. Атрибут `name` описывает раздел, в котором определена привязка. Атрибут `bindingConfiguration` указывает, какая конфигурация из раздела привязок используется. В разделе привязки может определяться несколько конфигураций.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример конфигурации службы.  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [Настройка служб](../../../../../docs/framework/wcf/configuring-services.md)
