---
title: '&lt;comContract&gt;'
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b15d40c5933776676c605e71c77453442ad3e339
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749066"
---
# <a name="ltcomcontractgt"></a>&lt;comContract&gt;
Указывает контракт службы интеграции COM+.  
  
 \<система. ServiceModel >  
\<comContracts >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|контракт|Строка, содержащая тип контракта.|  
|имя|Строка, содержащая имя контракта.|  
|namespace|Строка, содержащая пространство имен контракта.|  
|requiresSession|Логическое значение, указывающее, ограничено ли использование контракта только сеансовыми привязками. При инициализации службы среда выполнения интеграции обеспечивает согласованность этого параметра с типом используемой привязки. В случае конфликта одной или нескольких привязок для контракта создается исключение. Если это свойство имеет значение `false`, то при использовании одностороннего канала и наличии параметров [out] также создается исключение.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|persistableTypes|Все сохраняемые типы.|  
|userDefinedTypes|Коллекция пользовательских типов (UDT), подлежащая включению в контракт службы.|  
|exposedMethods|Коллекция методов COM+, которые предоставляются при предоставлении интерфейса компонента COM+ как веб-службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|comContracts|Содержит коллекцию элементов `comContract`.|  
  
## <a name="remarks"></a>Примечания  
 Контракты службы интеграции COM + в настоящее время ограничены "http://tempuri.org" пространство имен, а имя контракта является производным от поддерживающего COM-интерфейса. Однако можно указать альтернативы, используя раздел `comContracts`, а также элемент `comContract` в файле конфигурации. Например, для указания пространства имен, имени контракта и подлежащих включению пользовательских типов, а также других параметров контракта службы можно использовать следующую конфигурацию.  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [\<comContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [Интеграция с приложениями COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [Практическое руководство. Настройка параметров службы COM+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
