---
title: Элемент <cryptoClass>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088661"
---
# <a name="cryptoclass-element"></a>\<cryptoClass > элемент
Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе [\<nameEntry>](nameentry-element.md).  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> mscorlib**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптонамемаппинг >** ](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптоклассес >** ](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptoClass >**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`customClassName`|Обязательный атрибут.<br /><br /> Содержит сведения о классе шифрования. Используйте этот атрибут, чтобы указать короткое имя для класса. Необходимо указать строку, которая соответствует требованиям, указанным в [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`cryptoClasses`|Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе [\<nameEntry>](nameentry-element.md).|  
|`cryptographySettings`|Содержит параметры шифрования.|  
|`cryptoNameMapping`|Содержит сопоставления классов с понятными именами.|  
|`mscorlib`|Содержит элемент [\<cryptographySettings>](cryptographysettings-element.md).|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать элемент **\<cryptoClass >** для ссылки на криптографический класс и настройки среды выполнения. Затем можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для возврата объекта `MyCryptoRSAClass`.  
  
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
- [Службы криптографии](../../../../standard/security/cryptographic-services.md)
- [Настройка криптографических классов](../../configure-cryptography-classes.md)
