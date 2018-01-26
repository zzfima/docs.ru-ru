---
title: "&lt;oidEntry&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2d6dfe38f8e632a31f7a20191678f1fff7fd88ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltoidentrygt-element"></a>&lt;oidEntry&gt; элемент
Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.  
  
 \<configuration>  
\<mscorlib >  
\<cryptographySettings >  
\<oidMap >  
\<oidEntry >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|**ИДЕНТИФИКАТОР ОБЪЕКТА**|Обязательный атрибут.<br /><br /> Указывает идентификатор Объекта ASN.1, соответствующий алгоритм, реализованный класс.|  
|**name**|Обязательный атрибут.<br /><br /> Указывает значение для **имя** атрибута в [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) тег.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`cryptographySettings`|Содержит параметры шифрования.|  
|`mscorlib`|Содержит `cryptographySettings` элемента.|  
|`oidMap`|Содержит сопоставления идентификатора объекта ASN.1 с классами.|  
  
## <a name="remarks"></a>Примечания  
 Идентификаторы объектов ASN.1 определяют алгоритмы в некоторых криптографических форматах. Понятные имена алгоритмов, которые нужно определить сопоставления идентификаторов объектов.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать  **\<oidEntry >** элемент для сопоставления идентификатора объекта хэш-алгоритма RIPEMD-160 с реализацией этого алгоритма.  
  
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
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Схема параметров шифрования](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [Службы криптографии](../../../../../docs/standard/security/cryptographic-services.md)  
 [Настройка криптографических классов](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Отображение идентификаторов объектов на криптографические алгоритмы](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
