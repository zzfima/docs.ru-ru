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
ms.openlocfilehash: 0615a68add60b02a875921b1abb3776267db1731
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527592"
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a><span data-ttu-id="50a1c-102">&lt;mscorlib&gt; элемент для параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="50a1c-102">&lt;mscorlib&gt; Element for Cryptography Settings</span></span>
<span data-ttu-id="50a1c-103">Содержит [ \<cryptographySettings > элемент](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="50a1c-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="50a1c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="50a1c-104">\<configuration></span></span>  
<span data-ttu-id="50a1c-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="50a1c-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a1c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50a1c-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50a1c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="50a1c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="50a1c-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="50a1c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50a1c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="50a1c-109">Attributes</span></span>  
 <span data-ttu-id="50a1c-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="50a1c-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50a1c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="50a1c-111">Child Elements</span></span>  
  
|<span data-ttu-id="50a1c-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="50a1c-112">Element</span></span>|<span data-ttu-id="50a1c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="50a1c-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="50a1c-114">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="50a1c-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50a1c-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="50a1c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="50a1c-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="50a1c-116">Element</span></span>|<span data-ttu-id="50a1c-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="50a1c-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="50a1c-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50a1c-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="50a1c-119">Пример</span><span class="sxs-lookup"><span data-stu-id="50a1c-119">Example</span></span>  
 <span data-ttu-id="50a1c-120">В следующем примере показано, как использовать  **\<mscorlib >** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="50a1c-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="50a1c-121">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="50a1c-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="50a1c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="50a1c-122">See also</span></span>
- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="50a1c-123">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="50a1c-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="50a1c-124">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="50a1c-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="50a1c-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="50a1c-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="50a1c-126">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="50a1c-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
