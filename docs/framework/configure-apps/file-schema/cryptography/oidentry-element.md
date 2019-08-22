---
title: Элемент <oidEntry>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 013994e36c4c63410a753967cbac92c38783ae62
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659592"
---
# <a name="oidentry-element"></a>\<Элемент > Оидентри
Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.  
  
 \<configuration>  
\<> mscorlib  
\<Криптографисеттингс >  
\<Оидмап >  
\<Оидентри >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**КОДА**|Обязательный атрибут.<br /><br /> Указывает идентификатор объекта ASN. 1, соответствующий алгоритму, реализуемому вашим классом.|  
|**name**|Обязательный атрибут.<br /><br /> Задает значение для атрибута **Name** в [ \<теге элементе nameentry >](nameentry-element.md) .|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`cryptographySettings`|Содержит параметры шифрования.|  
|`mscorlib`|`cryptographySettings` Содержит элемент.|  
|`oidMap`|Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.|  
  
## <a name="remarks"></a>Примечания  
 Идентификаторы объектов ASN. 1 обозначают алгоритмы в некоторых криптографических форматах. Сопоставьте идентификаторы объектов с понятными именами для алгоритмов, которые необходимо опознать.  
  
## <a name="example"></a>Пример  
 В следующем примере показано,  **\<** как использовать элемент оидентри >, чтобы связать идентификатор объекта для алгоритма хэширования RIPEMD-160 с реализацией этого хэш-алгоритма.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема файла конфигурации](../index.md)
- [Схема параметров шифрования](index.md)
- [Cryptographic Services](../../../../../docs/standard/security/cryptographic-services.md)
- [Настройка криптографических классов](../../configure-cryptography-classes.md)
- [Отображение идентификаторов объектов на криптографические алгоритмы](../../map-object-identifiers-to-cryptography-algorithms.md)
