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
ms.openlocfilehash: ca0a9a4b37f28eb03f58de4fd9b120cb7e654e0c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088645"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="8a0d5-102">\<Криптографисеттингс > элемент</span><span class="sxs-lookup"><span data-stu-id="8a0d5-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="8a0d5-103">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-103">Contains cryptography settings.</span></span>  

<span data-ttu-id="8a0d5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8a0d5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8a0d5-105">&nbsp;&nbsp;[ **\<> mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8a0d5-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="8a0d5-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<криптографисеттингс >**</span><span class="sxs-lookup"><span data-stu-id="8a0d5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8a0d5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a0d5-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a0d5-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8a0d5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8a0d5-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a0d5-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8a0d5-110">Attributes</span></span>  
 <span data-ttu-id="8a0d5-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8a0d5-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8a0d5-112">Child Elements</span></span>  
  
|<span data-ttu-id="8a0d5-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a0d5-113">Element</span></span>|<span data-ttu-id="8a0d5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8a0d5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a0d5-115">\<Криптонамемаппинг ></span><span class="sxs-lookup"><span data-stu-id="8a0d5-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="8a0d5-116">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="8a0d5-117">\<Оидмап ></span><span class="sxs-lookup"><span data-stu-id="8a0d5-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="8a0d5-118">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a0d5-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8a0d5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8a0d5-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a0d5-120">Element</span></span>|<span data-ttu-id="8a0d5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8a0d5-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8a0d5-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="8a0d5-123">Содержит элемент `cryptographySettings`.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a0d5-124">Пример</span><span class="sxs-lookup"><span data-stu-id="8a0d5-124">Example</span></span>  
 <span data-ttu-id="8a0d5-125">В следующем примере показано, как использовать элемент **\<криптографисеттингс >** для хранения сопоставлений имен криптографии и сопоставления OID.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="8a0d5-126">В этом примере среда выполнения настраивается так, чтобы <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> возвращал объект `MyHashClass`, а класс `MyCryptoClass` сопоставляется с идентификатором объекта 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="8a0d5-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8a0d5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8a0d5-127">See also</span></span>

- [<span data-ttu-id="8a0d5-128">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8a0d5-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8a0d5-129">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="8a0d5-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8a0d5-130">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="8a0d5-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
