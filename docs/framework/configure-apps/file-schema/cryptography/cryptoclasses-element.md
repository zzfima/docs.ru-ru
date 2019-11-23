---
title: Элемент <cryptoClasses>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 89f1d89ea397794e366b53205ac23b94d7892869
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699757"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="c19f9-102">\<Криптоклассес > элемент</span><span class="sxs-lookup"><span data-stu-id="c19f9-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="c19f9-103">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="c19f9-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="c19f9-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c19f9-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c19f9-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c19f9-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="c19f9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="c19f9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="c19f9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптонамемаппинг >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="c19f9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="c19f9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<криптоклассес >**</span><span class="sxs-lookup"><span data-stu-id="c19f9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c19f9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c19f9-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c19f9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c19f9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c19f9-111">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c19f9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c19f9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c19f9-112">Attributes</span></span>  
 <span data-ttu-id="c19f9-113">Нет</span><span class="sxs-lookup"><span data-stu-id="c19f9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c19f9-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c19f9-114">Child Elements</span></span>  
  
|<span data-ttu-id="c19f9-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c19f9-115">Element</span></span>|<span data-ttu-id="c19f9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c19f9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c19f9-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="c19f9-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="c19f9-118">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="c19f9-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c19f9-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c19f9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c19f9-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="c19f9-120">Element</span></span>|<span data-ttu-id="c19f9-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c19f9-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c19f9-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c19f9-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="c19f9-123">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="c19f9-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="c19f9-124">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="c19f9-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="c19f9-125">Содержит элемент `cryptographySettings`.</span><span class="sxs-lookup"><span data-stu-id="c19f9-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c19f9-126">Пример</span><span class="sxs-lookup"><span data-stu-id="c19f9-126">Example</span></span>  
 <span data-ttu-id="c19f9-127">В следующем примере показано, как использовать элемент **\<cryptoClass >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c19f9-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="c19f9-128">Затем можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для возврата объекта `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="c19f9-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c19f9-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="c19f9-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="c19f9-130">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="c19f9-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c19f9-131">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="c19f9-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c19f9-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="c19f9-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="c19f9-133">System. Security. Cryptography. CryptoConfig. CreateFromName</span><span class="sxs-lookup"><span data-stu-id="c19f9-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="c19f9-134">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="c19f9-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
