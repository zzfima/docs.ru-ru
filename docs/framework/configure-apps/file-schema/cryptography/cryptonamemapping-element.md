---
title: Элемент <cryptoNameMapping>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: c2652ac73c1d55f09a1f8511603003dc6d7291f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659640"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="9052a-102">\<Элемент > Криптонамемаппинг</span><span class="sxs-lookup"><span data-stu-id="9052a-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="9052a-103">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="9052a-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="9052a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9052a-104">\<configuration></span></span>  
<span data-ttu-id="9052a-105">\<> mscorlib</span><span class="sxs-lookup"><span data-stu-id="9052a-105">\<mscorlib></span></span>  
<span data-ttu-id="9052a-106">\<Криптографисеттингс ></span><span class="sxs-lookup"><span data-stu-id="9052a-106">\<cryptographySettings></span></span>  
<span data-ttu-id="9052a-107">\<Криптонамемаппинг ></span><span class="sxs-lookup"><span data-stu-id="9052a-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9052a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9052a-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9052a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9052a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9052a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9052a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9052a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9052a-111">Attributes</span></span>  
 <span data-ttu-id="9052a-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="9052a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9052a-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9052a-113">Child Elements</span></span>  
  
|<span data-ttu-id="9052a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="9052a-114">Element</span></span>|<span data-ttu-id="9052a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9052a-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="9052a-116">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="9052a-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="9052a-117">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="9052a-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9052a-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9052a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9052a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="9052a-119">Element</span></span>|<span data-ttu-id="9052a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9052a-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9052a-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9052a-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="9052a-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="9052a-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="9052a-123">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="9052a-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="9052a-124">Содержит элемент > криптографисеттингс. \<</span><span class="sxs-lookup"><span data-stu-id="9052a-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9052a-125">Пример</span><span class="sxs-lookup"><span data-stu-id="9052a-125">Example</span></span>  
 <span data-ttu-id="9052a-126">В следующем примере показано, как использовать  **\<элемент криптонамемаппинг >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9052a-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="9052a-127">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> использовать метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="9052a-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9052a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9052a-128">See also</span></span>

- [<span data-ttu-id="9052a-129">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="9052a-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9052a-130">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="9052a-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9052a-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="9052a-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="9052a-132">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="9052a-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
