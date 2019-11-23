---
title: Элемент <mscorlib> для параметров шифрования
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: 4e2159cda5f35b5795804dede09ec17d07d71b23
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699735"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="685ca-102">\<элемента > mscorlib для параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="685ca-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="685ca-103">Содержит [элемент\<криптографисеттингс >](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="685ca-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="685ca-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="685ca-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="685ca-105">&nbsp;&nbsp; **\<mscorlib >**</span><span class="sxs-lookup"><span data-stu-id="685ca-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685ca-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="685ca-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="685ca-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="685ca-107">Attributes and Elements</span></span>  
 <span data-ttu-id="685ca-108">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="685ca-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="685ca-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="685ca-109">Attributes</span></span>  
 <span data-ttu-id="685ca-110">Нет</span><span class="sxs-lookup"><span data-stu-id="685ca-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="685ca-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="685ca-111">Child Elements</span></span>  
  
|<span data-ttu-id="685ca-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="685ca-112">Element</span></span>|<span data-ttu-id="685ca-113">Описание</span><span class="sxs-lookup"><span data-stu-id="685ca-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="685ca-114">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="685ca-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="685ca-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="685ca-115">Parent Elements</span></span>  
  
|<span data-ttu-id="685ca-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="685ca-116">Element</span></span>|<span data-ttu-id="685ca-117">Описание</span><span class="sxs-lookup"><span data-stu-id="685ca-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="685ca-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="685ca-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="685ca-119">Пример</span><span class="sxs-lookup"><span data-stu-id="685ca-119">Example</span></span>  
 <span data-ttu-id="685ca-120">В следующем примере показано, как использовать элемент **\<mscorlib >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="685ca-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="685ca-121">Затем можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для возврата объекта `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="685ca-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="685ca-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="685ca-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="685ca-123">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="685ca-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="685ca-124">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="685ca-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="685ca-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="685ca-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="685ca-126">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="685ca-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
