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
manager: markl
ms.openlocfilehash: 292937000eb1baca191c0960e8e496a128ee4696
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743567"
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a><span data-ttu-id="ff5ea-102">&lt;mscorlib&gt; элемент для параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="ff5ea-102">&lt;mscorlib&gt; Element for Cryptography Settings</span></span>
<span data-ttu-id="ff5ea-103">Содержит [ \<cryptographySettings > элемент](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="ff5ea-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="ff5ea-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ff5ea-104">\<configuration></span></span>  
<span data-ttu-id="ff5ea-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="ff5ea-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff5ea-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff5ea-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff5ea-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff5ea-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ff5ea-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ff5ea-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff5ea-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff5ea-109">Attributes</span></span>  
 <span data-ttu-id="ff5ea-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff5ea-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff5ea-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff5ea-111">Child Elements</span></span>  
  
|<span data-ttu-id="ff5ea-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff5ea-112">Element</span></span>|<span data-ttu-id="ff5ea-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ff5ea-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="ff5ea-114">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="ff5ea-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff5ea-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff5ea-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ff5ea-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff5ea-116">Element</span></span>|<span data-ttu-id="ff5ea-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ff5ea-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ff5ea-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff5ea-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff5ea-119">Пример</span><span class="sxs-lookup"><span data-stu-id="ff5ea-119">Example</span></span>  
 <span data-ttu-id="ff5ea-120">В следующем примере показано, как использовать  **\<mscorlib >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ff5ea-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="ff5ea-121">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="ff5ea-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff5ea-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ff5ea-122">See Also</span></span>  
 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="ff5ea-123">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ff5ea-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="ff5ea-124">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="ff5ea-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="ff5ea-125">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="ff5ea-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="ff5ea-126">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="ff5ea-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
