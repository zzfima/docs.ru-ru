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
# <a name="cryptoclass-element"></a><span data-ttu-id="123dc-102">\<cryptoClass > элемент</span><span class="sxs-lookup"><span data-stu-id="123dc-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="123dc-103">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="123dc-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

<span data-ttu-id="123dc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="123dc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="123dc-105">&nbsp;&nbsp;[ **\<> mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="123dc-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="123dc-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="123dc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="123dc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптонамемаппинг >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="123dc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="123dc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптоклассес >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="123dc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="123dc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptoClass >**</span><span class="sxs-lookup"><span data-stu-id="123dc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**</span></span>

## <a name="syntax"></a><span data-ttu-id="123dc-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="123dc-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="123dc-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="123dc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="123dc-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="123dc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="123dc-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="123dc-113">Attributes</span></span>  
  
|<span data-ttu-id="123dc-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="123dc-114">Attribute</span></span>|<span data-ttu-id="123dc-115">Описание</span><span class="sxs-lookup"><span data-stu-id="123dc-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="123dc-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="123dc-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="123dc-117">Содержит сведения о классе шифрования.</span><span class="sxs-lookup"><span data-stu-id="123dc-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="123dc-118">Используйте этот атрибут, чтобы указать короткое имя для класса.</span><span class="sxs-lookup"><span data-stu-id="123dc-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="123dc-119">Необходимо указать строку, которая соответствует требованиям, указанным в [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="123dc-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="123dc-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="123dc-120">Child Elements</span></span>  
 <span data-ttu-id="123dc-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="123dc-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="123dc-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="123dc-122">Parent Elements</span></span>  
  
|<span data-ttu-id="123dc-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="123dc-123">Element</span></span>|<span data-ttu-id="123dc-124">Описание</span><span class="sxs-lookup"><span data-stu-id="123dc-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="123dc-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="123dc-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="123dc-126">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="123dc-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="123dc-127">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="123dc-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="123dc-128">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="123dc-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="123dc-129">Содержит элемент [\<cryptographySettings>](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="123dc-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="123dc-130">Пример</span><span class="sxs-lookup"><span data-stu-id="123dc-130">Example</span></span>  
 <span data-ttu-id="123dc-131">В следующем примере показано, как использовать элемент **\<cryptoClass >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="123dc-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="123dc-132">Затем можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для возврата объекта `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="123dc-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="123dc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="123dc-133">See also</span></span>

- [<span data-ttu-id="123dc-134">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="123dc-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="123dc-135">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="123dc-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="123dc-136">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="123dc-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="123dc-137">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="123dc-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
