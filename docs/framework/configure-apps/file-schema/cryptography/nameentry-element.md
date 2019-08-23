---
title: Элемент <nameEntry>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: d8f4d4aa9c80990cdf858da9fcdf6465438866cf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927559"
---
# <a name="nameentry-element"></a>\<Элемент > элементе nameentry
Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.  
  
 \<configuration>  
\<> mscorlib  
\<Криптографисеттингс >  
\<Криптонамемаппинг >  
\<Элементе nameentry >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**name**|Обязательный атрибут.<br /><br /> Указывает понятное имя алгоритма, реализуемого криптографическим классом.|  
|**class**|Обязательный атрибут.<br /><br /> Задает значение для атрибута **Name** в [ \<элементе > cryptoClass](cryptoclass-element.md) .|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.web`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
  
## <a name="remarks"></a>Примечания  
 Атрибут **Name** может быть именем одного из абстрактных классов, <xref:System.Security.Cryptography> найденных в пространстве имен. При вызове метода **CREATE** для абстрактного криптографического класса имя абстрактного класса передается <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> в метод. **CreateFromName** возвращает экземпляр типа, указанного атрибутом **класса** . Если атрибут **Name** имеет короткое имя, например RSA, это имя можно использовать при вызове метода **CreateFromName** .  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать  **\<элемент элементе nameentry >** для ссылки на криптографический класс и настройки среды выполнения. Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> использовать метод для возврата `MyCryptoRSAClass` объекта.  
  
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

- [Схема файла конфигурации](../index.md)
- [Схема параметров шифрования](index.md)
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
- [Настройка криптографических классов](../../configure-cryptography-classes.md)
