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
ms.openlocfilehash: dbe46e0b36d247005f933c82ee83687886b283d1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659657"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="6cd2d-102">\<Элемент > Криптоклассес</span><span class="sxs-lookup"><span data-stu-id="6cd2d-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="6cd2d-103">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="6cd2d-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="6cd2d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6cd2d-104">\<configuration></span></span>  
<span data-ttu-id="6cd2d-105">\<> mscorlib</span><span class="sxs-lookup"><span data-stu-id="6cd2d-105">\<mscorlib></span></span>  
<span data-ttu-id="6cd2d-106">\<Криптографисеттингс ></span><span class="sxs-lookup"><span data-stu-id="6cd2d-106">\<cryptographySettings></span></span>  
<span data-ttu-id="6cd2d-107">\<Криптонамемаппинг ></span><span class="sxs-lookup"><span data-stu-id="6cd2d-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="6cd2d-108">\<Криптоклассес ></span><span class="sxs-lookup"><span data-stu-id="6cd2d-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cd2d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cd2d-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cd2d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6cd2d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6cd2d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6cd2d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cd2d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6cd2d-112">Attributes</span></span>  
 <span data-ttu-id="6cd2d-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="6cd2d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6cd2d-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6cd2d-114">Child Elements</span></span>  
  
|<span data-ttu-id="6cd2d-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="6cd2d-115">Element</span></span>|<span data-ttu-id="6cd2d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6cd2d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cd2d-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="6cd2d-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="6cd2d-118">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="6cd2d-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6cd2d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6cd2d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6cd2d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6cd2d-120">Element</span></span>|<span data-ttu-id="6cd2d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6cd2d-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6cd2d-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6cd2d-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="6cd2d-123">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="6cd2d-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="6cd2d-124">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="6cd2d-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="6cd2d-125">`cryptographySettings` Содержит элемент.</span><span class="sxs-lookup"><span data-stu-id="6cd2d-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6cd2d-126">Пример</span><span class="sxs-lookup"><span data-stu-id="6cd2d-126">Example</span></span>  
 <span data-ttu-id="6cd2d-127">В следующем примере показано, как использовать  **\<элемент cryptoClass >** для ссылки на криптографический класс и для настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6cd2d-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="6cd2d-128">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> использовать метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="6cd2d-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6cd2d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6cd2d-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="6cd2d-130">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="6cd2d-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6cd2d-131">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="6cd2d-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6cd2d-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="6cd2d-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="6cd2d-133">System. Security. Cryptography. CryptoConfig. CreateFromName</span><span class="sxs-lookup"><span data-stu-id="6cd2d-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="6cd2d-134">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="6cd2d-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
