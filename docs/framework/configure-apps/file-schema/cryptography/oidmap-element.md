---
title: Элемент <oidMap>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: 5f055d6e665f68586191ab760fb5658eeb5c2cb2
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087985"
---
# <a name="oidmap-element"></a>\<Оидмап > элемент
Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> mscorlib**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<оидмап >**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Оидентри >](oidentry-element.md)|Сопоставляет идентификатор объекта ASN. 1 с понятным именем.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`cryptographySettings`|Содержит параметры шифрования.|  
|`mscorlib`|Содержит элемент `cryptographySettings`.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать элемент **\<оидмап >** для включения сопоставления OID для алгоритма хэширования RIPEMD-160 к реализации этого хэш-алгоритма.  
  
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
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема файла конфигурации](../index.md)
- [Схема параметров шифрования](index.md)
- [Службы криптографии](../../../../standard/security/cryptographic-services.md)
- [Настройка криптографических классов](../../configure-cryptography-classes.md)
- [Отображение идентификаторов объектов на криптографические алгоритмы](../../map-object-identifiers-to-cryptography-algorithms.md)
