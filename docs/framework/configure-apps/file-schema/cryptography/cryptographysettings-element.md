---
title: <cryptographySettings> Элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: ec3a5a73caa901a21e22dbec7500af9153e01ef4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164142"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="1fa54-102">\<cryptographySettings > элемент</span><span class="sxs-lookup"><span data-stu-id="1fa54-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="1fa54-103">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="1fa54-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="1fa54-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1fa54-104">\<configuration></span></span>  
<span data-ttu-id="1fa54-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="1fa54-105">\<mscorlib></span></span>  
<span data-ttu-id="1fa54-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="1fa54-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fa54-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fa54-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fa54-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1fa54-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1fa54-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1fa54-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fa54-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1fa54-110">Attributes</span></span>  
 <span data-ttu-id="1fa54-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1fa54-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1fa54-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1fa54-112">Child Elements</span></span>  
  
|<span data-ttu-id="1fa54-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="1fa54-113">Element</span></span>|<span data-ttu-id="1fa54-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1fa54-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fa54-115">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="1fa54-115">\<cryptoNameMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="1fa54-116">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="1fa54-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="1fa54-117">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="1fa54-117">\<oidMap></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="1fa54-118">Содержит сопоставления идентификатора объекта ASN.1 с классами.</span><span class="sxs-lookup"><span data-stu-id="1fa54-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fa54-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1fa54-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1fa54-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="1fa54-120">Element</span></span>|<span data-ttu-id="1fa54-121">Описание</span><span class="sxs-lookup"><span data-stu-id="1fa54-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1fa54-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1fa54-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="1fa54-123">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="1fa54-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1fa54-124">Пример</span><span class="sxs-lookup"><span data-stu-id="1fa54-124">Example</span></span>  
 <span data-ttu-id="1fa54-125">Приведенный ниже, показано, как использовать  **\<cryptographySettings >** элемент сопоставления имен криптографии и сопоставления идентификатора Объекта.</span><span class="sxs-lookup"><span data-stu-id="1fa54-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="1fa54-126">В этом примере настраивается среда выполнения, чтобы <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> возвращает `MyHashClass` объекта и `MyCryptoClass` класса сопоставляется 1.3.36.2.1 идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="1fa54-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1fa54-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1fa54-127">See also</span></span>

- [<span data-ttu-id="1fa54-128">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="1fa54-128">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="1fa54-129">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="1fa54-129">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="1fa54-130">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="1fa54-130">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
