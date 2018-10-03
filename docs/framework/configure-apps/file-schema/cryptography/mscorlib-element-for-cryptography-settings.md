---
title: '&lt;mscorlib&gt; элемент для параметров криптографии'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b5da49ff22cfa6bd1c3e4d574865eb5e61dc73fb
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028366"
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a><span data-ttu-id="e3408-102">&lt;mscorlib&gt; элемент для параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="e3408-102">&lt;mscorlib&gt; Element for Cryptography Settings</span></span>
<span data-ttu-id="e3408-103">Содержит [ \<cryptographySettings > элемент](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="e3408-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="e3408-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e3408-104">\<configuration></span></span>  
<span data-ttu-id="e3408-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="e3408-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3408-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3408-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3408-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3408-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e3408-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3408-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3408-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3408-109">Attributes</span></span>  
 <span data-ttu-id="e3408-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e3408-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3408-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3408-111">Child Elements</span></span>  
  
|<span data-ttu-id="e3408-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3408-112">Element</span></span>|<span data-ttu-id="e3408-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e3408-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="e3408-114">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="e3408-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3408-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3408-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e3408-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3408-116">Element</span></span>|<span data-ttu-id="e3408-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e3408-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e3408-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3408-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e3408-119">Пример</span><span class="sxs-lookup"><span data-stu-id="e3408-119">Example</span></span>  
 <span data-ttu-id="e3408-120">В следующем примере показано, как использовать  **\<mscorlib >** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e3408-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e3408-121">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="e3408-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3408-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e3408-122">See Also</span></span>  
 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="e3408-123">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3408-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="e3408-124">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="e3408-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="e3408-125">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="e3408-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="e3408-126">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="e3408-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
