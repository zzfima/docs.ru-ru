---
title: '&lt;cryptoClasses&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 671302003c3a1f3a37e1773aeeae9cb09a457d13
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47107757"
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="82788-102">&lt;cryptoClasses&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="82788-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="82788-103">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="82788-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="82788-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="82788-104">\<configuration></span></span>  
<span data-ttu-id="82788-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="82788-105">\<mscorlib></span></span>  
<span data-ttu-id="82788-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="82788-106">\<cryptographySettings></span></span>  
<span data-ttu-id="82788-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="82788-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="82788-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="82788-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82788-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82788-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82788-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82788-110">Attributes and Elements</span></span>  
 <span data-ttu-id="82788-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82788-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82788-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82788-112">Attributes</span></span>  
 <span data-ttu-id="82788-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="82788-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82788-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82788-114">Child Elements</span></span>  
  
|<span data-ttu-id="82788-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="82788-115">Element</span></span>|<span data-ttu-id="82788-116">Описание</span><span class="sxs-lookup"><span data-stu-id="82788-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82788-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="82788-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="82788-118">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="82788-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82788-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82788-119">Parent Elements</span></span>  
  
|<span data-ttu-id="82788-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="82788-120">Element</span></span>|<span data-ttu-id="82788-121">Описание</span><span class="sxs-lookup"><span data-stu-id="82788-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="82788-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82788-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="82788-123">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="82788-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="82788-124">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="82788-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="82788-125">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="82788-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="82788-126">Пример</span><span class="sxs-lookup"><span data-stu-id="82788-126">Example</span></span>  
 <span data-ttu-id="82788-127">Приведенный ниже, показано, как использовать  **\<cryptoClass >** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="82788-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="82788-128">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="82788-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82788-129">См. также</span><span class="sxs-lookup"><span data-stu-id="82788-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="82788-130">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="82788-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="82788-131">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="82788-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="82788-132">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="82788-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="82788-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="82788-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)  
 [<span data-ttu-id="82788-134">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="82788-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
