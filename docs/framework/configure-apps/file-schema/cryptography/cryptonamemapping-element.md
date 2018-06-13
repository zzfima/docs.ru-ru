---
title: '&lt;cryptoNameMapping&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f6811a2dbd8859a8765c5e855e0fe423bd31f287
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359391"
---
# <a name="ltcryptonamemappinggt-element"></a><span data-ttu-id="ad595-102">&lt;cryptoNameMapping&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="ad595-102">&lt;cryptoNameMapping&gt; Element</span></span>
<span data-ttu-id="ad595-103">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="ad595-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="ad595-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ad595-104">\<configuration></span></span>  
<span data-ttu-id="ad595-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="ad595-105">\<mscorlib></span></span>  
<span data-ttu-id="ad595-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="ad595-106">\<cryptographySettings></span></span>  
<span data-ttu-id="ad595-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="ad595-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad595-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad595-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad595-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ad595-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ad595-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ad595-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad595-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad595-111">Attributes</span></span>  
 <span data-ttu-id="ad595-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ad595-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad595-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad595-113">Child Elements</span></span>  
  
|<span data-ttu-id="ad595-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad595-114">Element</span></span>|<span data-ttu-id="ad595-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ad595-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="ad595-116">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="ad595-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="ad595-117">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="ad595-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad595-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad595-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ad595-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad595-119">Element</span></span>|<span data-ttu-id="ad595-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ad595-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ad595-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad595-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="ad595-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="ad595-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="ad595-123">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="ad595-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="ad595-124">Содержит \<cryptographySettings > элемент.</span><span class="sxs-lookup"><span data-stu-id="ad595-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ad595-125">Пример</span><span class="sxs-lookup"><span data-stu-id="ad595-125">Example</span></span>  
 <span data-ttu-id="ad595-126">В следующем примере показано, как использовать  **\<cryptoNameMapping >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad595-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="ad595-127">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="ad595-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ad595-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ad595-128">See Also</span></span>  
 [<span data-ttu-id="ad595-129">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ad595-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="ad595-130">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="ad595-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="ad595-131">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="ad595-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="ad595-132">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="ad595-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
