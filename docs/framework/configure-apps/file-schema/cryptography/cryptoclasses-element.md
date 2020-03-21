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
ms.openlocfilehash: c93fadf51297d59ab499e25de283700364903049
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155250"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="f3d67-102">\<криптоклассы> элемент</span><span class="sxs-lookup"><span data-stu-id="f3d67-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="f3d67-103">Содержит список классов криптографии, которые имеют отображение на дружественное имя в [ \<nameEntry>](nameentry-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="f3d67-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="f3d67-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="f3d67-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f3d67-105">&nbsp;&nbsp;[**\<мскориб>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f3d67-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="f3d67-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<криптографияНастройки>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="f3d67-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="f3d67-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="f3d67-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="f3d67-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<криптоклассы>**</span><span class="sxs-lookup"><span data-stu-id="f3d67-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d67-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3d67-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3d67-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3d67-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f3d67-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3d67-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3d67-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3d67-112">Attributes</span></span>  
 <span data-ttu-id="f3d67-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="f3d67-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f3d67-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3d67-114">Child Elements</span></span>  
  
|<span data-ttu-id="f3d67-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3d67-115">Element</span></span>|<span data-ttu-id="f3d67-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f3d67-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3d67-117">\<криптокласс></span><span class="sxs-lookup"><span data-stu-id="f3d67-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="f3d67-118">Содержит класс криптографии, который имеет отображение на дружественное имя в \*\* \<nameEntry>\*\* элемент.</span><span class="sxs-lookup"><span data-stu-id="f3d67-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3d67-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3d67-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f3d67-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3d67-120">Element</span></span>|<span data-ttu-id="f3d67-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f3d67-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f3d67-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3d67-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f3d67-123">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="f3d67-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="f3d67-124">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="f3d67-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="f3d67-125">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="f3d67-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f3d67-126">Пример</span><span class="sxs-lookup"><span data-stu-id="f3d67-126">Example</span></span>  
 <span data-ttu-id="f3d67-127">В следующем примере показано, как использовать элемент \*\* \<cryptoClass>\*\* для ссылки на класс криптографии и для настройки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3d67-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="f3d67-128">Затем можно передать строку "RSA" <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> методу <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> и использовать `MyCryptoRSAClass` метод для возврата объекта.</span><span class="sxs-lookup"><span data-stu-id="f3d67-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3d67-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f3d67-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="f3d67-130">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="f3d67-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f3d67-131">Криптография Настройки Схема</span><span class="sxs-lookup"><span data-stu-id="f3d67-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f3d67-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="f3d67-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="f3d67-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="f3d67-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="f3d67-134">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="f3d67-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
