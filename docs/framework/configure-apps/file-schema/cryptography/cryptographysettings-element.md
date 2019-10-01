---
title: Элемент <cryptographySettings>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: 96a8c9accc56274b5cc13dc2a871165857b3a2d9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699821"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="b2e64-102">Элемент > @no__t 0cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="b2e64-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="b2e64-103">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="b2e64-103">Contains cryptography settings.</span></span>  
  
[<span data-ttu-id="b2e64-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b2e64-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b2e64-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b2e64-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="b2e64-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<cryptographySettings >**</span><span class="sxs-lookup"><span data-stu-id="b2e64-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2e64-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2e64-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2e64-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2e64-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b2e64-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b2e64-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2e64-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2e64-110">Attributes</span></span>  
 <span data-ttu-id="b2e64-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="b2e64-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b2e64-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2e64-112">Child Elements</span></span>  
  
|<span data-ttu-id="b2e64-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2e64-113">Element</span></span>|<span data-ttu-id="b2e64-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b2e64-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2e64-115">@no__t 1cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="b2e64-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="b2e64-116">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="b2e64-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="b2e64-117">@no__t 1oidMap ></span><span class="sxs-lookup"><span data-stu-id="b2e64-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="b2e64-118">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="b2e64-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2e64-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2e64-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b2e64-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2e64-120">Element</span></span>|<span data-ttu-id="b2e64-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b2e64-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b2e64-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b2e64-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="b2e64-123">`cryptographySettings` Содержит элемент.</span><span class="sxs-lookup"><span data-stu-id="b2e64-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2e64-124">Пример</span><span class="sxs-lookup"><span data-stu-id="b2e64-124">Example</span></span>  
 <span data-ttu-id="b2e64-125">В следующем примере показано, как использовать элемент **\<cryptographySettings >** , чтобы содержать сопоставления имен криптографии и сопоставления OID.</span><span class="sxs-lookup"><span data-stu-id="b2e64-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="b2e64-126">В этом примере среда выполнения настраивается таким образом, чтобы <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> возвращал объект `MyHashClass`, а класс `MyCryptoClass` сопоставляется с идентификатором объекта 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="b2e64-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2e64-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b2e64-127">See also</span></span>

- [<span data-ttu-id="b2e64-128">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b2e64-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b2e64-129">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="b2e64-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b2e64-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b2e64-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
