---
title: Элемент <xmlSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 2919e8d4c1af858973ff3d2b58b4d3bc4f925527
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258257"
---
# <a name="xmlserializer-element"></a>\<xmlSerializer > элемент
Указывает, выполнена ли дополнительная проверка хода выполнения <xref:System.Xml.Serialization.XmlSerializer>.  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**checkDeserializeAdvances**|Указывает, выполнена ли проверка хода выполнения <xref:System.Xml.Serialization.XmlSerializer>. Присвойте атрибуту значение "true" или "false". Значение по умолчанию - "true".|  
|**useLegacySerializationGeneration**|Укажите, следует ли объекту <xref:System.Xml.Serialization.XmlSerializer> использовать установленную сериализацию прежней версии, которая создает сборки путем написания кода на C# в файле и компиляции его в сборку. Значение по умолчанию — **false**.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)|Содержит параметры конфигурации для классов <xref:System.Xml.Serialization.XmlSerializer> и <xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию <xref:System.Xml.Serialization.XmlSerializer> обеспечивает дополнительный уровень безопасности в отношении возможных атак типа "отказ в обслуживании" во время десериализации ненадежных данных. Такие атаки отслеживаются путем определения бесконечных циклов во время десериализации. При обнаружении таких условий, исключение со следующим сообщением: «Внутренняя ошибка: сбой десериализации при перемещении по базовому потоку.»  
  
 Такое сообщение еще не означает, что система подвергается атаке типа "отказ в обслуживании". В редких случаях механизм определения бесконечного цикла сообщает о ложном положительном результате, и выдается исключение для допустимых входящих сообщений. Если обнаружится, что некоторые допустимые сообщения приложения отклоняются из-за использования такого дополнительного уровня защиты, задайте атрибут **checkDeserializeAdvances** со значением false.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере кода атрибут **checkDeserializeAdvances** задан как false.  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Serialization.XmlSerializer>
- [Элемент \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)
