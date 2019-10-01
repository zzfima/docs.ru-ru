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
ms.openlocfilehash: 45d2da22a7c3486d4c7a638e92d1f3fce6f9883c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699719"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="f25bd-102">Элемент > @no__t 0cryptoNameMapping</span><span class="sxs-lookup"><span data-stu-id="f25bd-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="f25bd-103">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="f25bd-103">Contains mappings of classes to friendly names.</span></span>  
  
[<span data-ttu-id="f25bd-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f25bd-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f25bd-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f25bd-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="f25bd-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="f25bd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="f25bd-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<cryptoNameMapping >**</span><span class="sxs-lookup"><span data-stu-id="f25bd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f25bd-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f25bd-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f25bd-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f25bd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f25bd-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f25bd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f25bd-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f25bd-111">Attributes</span></span>  
 <span data-ttu-id="f25bd-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="f25bd-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f25bd-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f25bd-113">Child Elements</span></span>  
  
|<span data-ttu-id="f25bd-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f25bd-114">Element</span></span>|<span data-ttu-id="f25bd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f25bd-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="f25bd-116">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="f25bd-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="f25bd-117">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="f25bd-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f25bd-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f25bd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f25bd-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f25bd-119">Element</span></span>|<span data-ttu-id="f25bd-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f25bd-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f25bd-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f25bd-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f25bd-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="f25bd-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="f25bd-123">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="f25bd-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="f25bd-124">Содержит элемент > @no__t 0cryptographySettings.</span><span class="sxs-lookup"><span data-stu-id="f25bd-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f25bd-125">Пример</span><span class="sxs-lookup"><span data-stu-id="f25bd-125">Example</span></span>  
 <span data-ttu-id="f25bd-126">В следующем примере показано, как использовать элемент **\<cryptoNameMapping >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f25bd-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="f25bd-127">Затем можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для возврата объекта `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="f25bd-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f25bd-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f25bd-128">See also</span></span>

- [<span data-ttu-id="f25bd-129">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f25bd-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f25bd-130">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="f25bd-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f25bd-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="f25bd-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="f25bd-132">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="f25bd-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
