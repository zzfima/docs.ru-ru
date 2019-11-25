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
ms.openlocfilehash: 4b3495d17e07ca611a384bf958ee06e928eb2506
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088019"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="ed247-102">\<Криптонамемаппинг > элемент</span><span class="sxs-lookup"><span data-stu-id="ed247-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="ed247-103">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="ed247-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="ed247-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ed247-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ed247-105">&nbsp;&nbsp;[ **\<> mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ed247-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="ed247-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="ed247-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="ed247-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<криптонамемаппинг >**</span><span class="sxs-lookup"><span data-stu-id="ed247-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ed247-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed247-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed247-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ed247-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ed247-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ed247-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed247-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed247-111">Attributes</span></span>  
 <span data-ttu-id="ed247-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ed247-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ed247-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ed247-113">Child Elements</span></span>  
  
|<span data-ttu-id="ed247-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed247-114">Element</span></span>|<span data-ttu-id="ed247-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ed247-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="ed247-116">Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="ed247-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="ed247-117">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="ed247-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed247-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ed247-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ed247-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed247-119">Element</span></span>|<span data-ttu-id="ed247-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ed247-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ed247-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ed247-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="ed247-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="ed247-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="ed247-123">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="ed247-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="ed247-124">Содержит элемент \<Криптографисеттингс >.</span><span class="sxs-lookup"><span data-stu-id="ed247-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ed247-125">Пример</span><span class="sxs-lookup"><span data-stu-id="ed247-125">Example</span></span>  
 <span data-ttu-id="ed247-126">В следующем примере показано, как использовать элемент **\<криптонамемаппинг >** для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed247-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="ed247-127">Затем можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для возврата объекта `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="ed247-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ed247-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ed247-128">See also</span></span>

- [<span data-ttu-id="ed247-129">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ed247-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ed247-130">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="ed247-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ed247-131">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="ed247-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="ed247-132">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="ed247-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
