---
title: '&lt; add&gt; элемента &lt;declaredTypes&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 90eaf11ce8b9e3675a23ed3875680b03f149b56b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754123"
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a>&lt; add&gt; элемента &lt;declaredTypes&gt;
Добавляет тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации. В каждый объявленный тип включены известные типы, которые будут возвращены как поле или свойство объявленного типа.  
  
 system.runtime.serialization  
\<dataContractSerializer >  
\<declaredTypes >  
\<Добавить > из \<declaredTypes >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|тип|Обязательный строковый атрибут.<br /><br /> Задает имя типа (в том числе пространство имен), имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<knownType >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Задает известный тип для добавляемого объявленного типа. Если объявленный тип является универсальным типом, необходимо также добавить элемент параметра к элементу `<knownType>`, чтобы указать, какой универсальный параметр будет использоваться для возвращения известного типа.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<declaredTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Содержит типы, для которых необходимы известные типы во время десериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об известных типах см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 В разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.  
  
> [!NOTE]
>  При добавлении типа <xref:System.Object> как `<declaredType>` возникает <xref:System.Configuration.ConfigurationErrorsException>. Это обусловлено тем, что тип <xref:System.Object> нельзя использовать как объявленный тип в конфигурации.  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<Добавить > из \<declaredTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
