---
title: <mscorlib> Элемент для параметров криптографии
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: ec328bc4c63bd4754c6f975ac03e610718304245
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165156"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="4eedc-102">\<mscorlib > элемент для параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="4eedc-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="4eedc-103">Содержит [ \<cryptographySettings > элемент](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="4eedc-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="4eedc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4eedc-104">\<configuration></span></span>  
<span data-ttu-id="4eedc-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="4eedc-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eedc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4eedc-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4eedc-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4eedc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4eedc-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4eedc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4eedc-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4eedc-109">Attributes</span></span>  
 <span data-ttu-id="4eedc-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4eedc-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4eedc-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4eedc-111">Child Elements</span></span>  
  
|<span data-ttu-id="4eedc-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="4eedc-112">Element</span></span>|<span data-ttu-id="4eedc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4eedc-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="4eedc-114">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="4eedc-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4eedc-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4eedc-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4eedc-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="4eedc-116">Element</span></span>|<span data-ttu-id="4eedc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4eedc-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4eedc-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4eedc-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4eedc-119">Пример</span><span class="sxs-lookup"><span data-stu-id="4eedc-119">Example</span></span>  
 <span data-ttu-id="4eedc-120">В следующем примере показано, как использовать  **\<mscorlib >** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4eedc-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="4eedc-121">Затем можно передать строку «RSA» для <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использование <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="4eedc-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4eedc-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4eedc-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="4eedc-123">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="4eedc-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4eedc-124">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="4eedc-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="4eedc-125">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="4eedc-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="4eedc-126">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="4eedc-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
