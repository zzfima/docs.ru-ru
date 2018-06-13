---
title: '&lt;nameEntry&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1bffb72e7c68d10e2c0edd5ec3cb9bcff10cbc0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743057"
---
# <a name="ltnameentrygt-element"></a>&lt;nameEntry&gt; элемент
Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.  
  
 \<configuration>  
\<mscorlib >  
\<cryptographySettings >  
\<cryptoNameMapping >  
\<nameEntry >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**name**|Обязательный атрибут.<br /><br /> Указывает понятное имя для алгоритма, который реализует криптографический класс.|  
|**class**|Обязательный атрибут.<br /><br /> Указывает значение для **имя** атрибута в [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) элемента.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.web`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
  
## <a name="remarks"></a>Примечания  
 **Имя** атрибут может быть имя абстрактные классы, находящиеся в <xref:System.Security.Cryptography> пространства имен. При вызове **создать** метода криптографии абстрактного класса, абстрактный класс имя передается <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> метод. **CreateFromName** возвращает экземпляр типа, указанного **класса** атрибута. Если **имя** атрибут — это краткое имя, например RSA, можно использовать это имя при вызове **CreateFromName** метод.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать  **\<nameEntry >** для ссылки на криптографический класс и настройки среды выполнения. Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Схема параметров шифрования](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [Службы криптографии](../../../../../docs/standard/security/cryptographic-services.md)  
 [Настройка криптографических классов](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
