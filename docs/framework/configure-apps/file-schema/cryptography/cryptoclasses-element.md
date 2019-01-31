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
ms.openlocfilehash: aa649a0ea83279a1b2bdb2dff33794002b8a6b7d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274085"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="25735-102">\<cryptoClasses > элемент</span><span class="sxs-lookup"><span data-stu-id="25735-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="25735-103">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="25735-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="25735-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="25735-104">\<configuration></span></span>  
<span data-ttu-id="25735-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="25735-105">\<mscorlib></span></span>  
<span data-ttu-id="25735-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="25735-106">\<cryptographySettings></span></span>  
<span data-ttu-id="25735-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="25735-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="25735-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="25735-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25735-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25735-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25735-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="25735-110">Attributes and Elements</span></span>  
 <span data-ttu-id="25735-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="25735-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25735-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="25735-112">Attributes</span></span>  
 <span data-ttu-id="25735-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="25735-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="25735-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="25735-114">Child Elements</span></span>  
  
|<span data-ttu-id="25735-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="25735-115">Element</span></span>|<span data-ttu-id="25735-116">Описание</span><span class="sxs-lookup"><span data-stu-id="25735-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25735-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="25735-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="25735-118">Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="25735-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25735-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="25735-119">Parent Elements</span></span>  
  
|<span data-ttu-id="25735-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="25735-120">Element</span></span>|<span data-ttu-id="25735-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="25735-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="25735-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="25735-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="25735-123">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="25735-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="25735-124">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="25735-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="25735-125">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="25735-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="25735-126">Пример</span><span class="sxs-lookup"><span data-stu-id="25735-126">Example</span></span>  
 <span data-ttu-id="25735-127">Приведенный ниже, показано, как использовать  **\<cryptoClass >** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="25735-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="25735-128">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="25735-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25735-129">См. также</span><span class="sxs-lookup"><span data-stu-id="25735-129">See also</span></span>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="25735-130">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="25735-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="25735-131">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="25735-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="25735-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="25735-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="25735-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="25735-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="25735-134">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="25735-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
