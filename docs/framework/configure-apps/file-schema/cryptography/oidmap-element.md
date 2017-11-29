---
title: "&lt;oidMap&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: eab9be57b6f8fac5f208e39a6aaa8eb7be92558d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="7bb80-102">&lt;oidMap&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="7bb80-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="7bb80-103">Содержит сопоставления идентификатора объекта ASN.1 с классами.</span><span class="sxs-lookup"><span data-stu-id="7bb80-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="7bb80-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7bb80-104">\<configuration></span></span>  
<span data-ttu-id="7bb80-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="7bb80-105">\<mscorlib></span></span>  
<span data-ttu-id="7bb80-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="7bb80-106">\<cryptographySettings></span></span>  
<span data-ttu-id="7bb80-107">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="7bb80-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bb80-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bb80-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bb80-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7bb80-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7bb80-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7bb80-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bb80-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7bb80-111">Attributes</span></span>  
 <span data-ttu-id="7bb80-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7bb80-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7bb80-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7bb80-113">Child Elements</span></span>  
  
|<span data-ttu-id="7bb80-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="7bb80-114">Element</span></span>|<span data-ttu-id="7bb80-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7bb80-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7bb80-116">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="7bb80-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="7bb80-117">Сопоставление идентификатора объекта ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="7bb80-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7bb80-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7bb80-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7bb80-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="7bb80-119">Element</span></span>|<span data-ttu-id="7bb80-120">Описание</span><span class="sxs-lookup"><span data-stu-id="7bb80-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7bb80-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7bb80-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="7bb80-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="7bb80-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="7bb80-123">Содержит `cryptographySettings` элемента.</span><span class="sxs-lookup"><span data-stu-id="7bb80-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7bb80-124">Пример</span><span class="sxs-lookup"><span data-stu-id="7bb80-124">Example</span></span>  
 <span data-ttu-id="7bb80-125">В следующем примере показано, как использовать  **\<oidMap >** элемент для сопоставления идентификатора объекта хэш-алгоритма RIPEMD-160 с реализацией этого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="7bb80-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7bb80-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7bb80-126">See Also</span></span>  
 [<span data-ttu-id="7bb80-127">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="7bb80-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="7bb80-128">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="7bb80-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="7bb80-129">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="7bb80-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="7bb80-130">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="7bb80-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="7bb80-131">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="7bb80-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
