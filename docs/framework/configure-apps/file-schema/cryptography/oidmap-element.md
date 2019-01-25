---
title: '&lt;oidMap&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 19983e4d17ac2843385685a6b8b247d16f4cc081
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700472"
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="b625b-102">&lt;oidMap&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="b625b-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="b625b-103">Содержит сопоставления идентификатора объекта ASN.1 с классами.</span><span class="sxs-lookup"><span data-stu-id="b625b-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="b625b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b625b-104">\<configuration></span></span>  
<span data-ttu-id="b625b-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="b625b-105">\<mscorlib></span></span>  
<span data-ttu-id="b625b-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="b625b-106">\<cryptographySettings></span></span>  
<span data-ttu-id="b625b-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="b625b-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b625b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b625b-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b625b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b625b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b625b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b625b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b625b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b625b-111">Attributes</span></span>  
 <span data-ttu-id="b625b-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b625b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b625b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b625b-113">Child Elements</span></span>  
  
|<span data-ttu-id="b625b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="b625b-114">Element</span></span>|<span data-ttu-id="b625b-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="b625b-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b625b-116">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="b625b-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="b625b-117">Сопоставление идентификатора объекта ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="b625b-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b625b-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b625b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b625b-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="b625b-119">Element</span></span>|<span data-ttu-id="b625b-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="b625b-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b625b-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b625b-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="b625b-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="b625b-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="b625b-123">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="b625b-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b625b-124">Пример</span><span class="sxs-lookup"><span data-stu-id="b625b-124">Example</span></span>  
 <span data-ttu-id="b625b-125">В следующем примере показано, как использовать  **\<oidMap >** элемент для сопоставления идентификатора объекта хэш-алгоритма RIPEMD-160 с реализацией этого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="b625b-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b625b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b625b-126">See also</span></span>
- [<span data-ttu-id="b625b-127">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b625b-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b625b-128">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="b625b-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="b625b-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b625b-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="b625b-130">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="b625b-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="b625b-131">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="b625b-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
