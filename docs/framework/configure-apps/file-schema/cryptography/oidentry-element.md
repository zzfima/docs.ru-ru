---
title: "&lt;oidEntry&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 12c3b87f1cec72798ea92357f34ecc25b7e6edcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltoidentrygt-element"></a><span data-ttu-id="a7909-102">&lt;oidEntry&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="a7909-102">&lt;oidEntry&gt; Element</span></span>
<span data-ttu-id="a7909-103">Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="a7909-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="a7909-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a7909-104">\<configuration></span></span>  
<span data-ttu-id="a7909-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="a7909-105">\<mscorlib></span></span>  
<span data-ttu-id="a7909-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="a7909-106">\<cryptographySettings></span></span>  
<span data-ttu-id="a7909-107">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="a7909-107">\<oidMap></span></span>  
<span data-ttu-id="a7909-108">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="a7909-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7909-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7909-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7909-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a7909-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a7909-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a7909-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7909-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7909-112">Attributes</span></span>  
  
|<span data-ttu-id="a7909-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a7909-113">Attribute</span></span>|<span data-ttu-id="a7909-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a7909-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7909-115">**ИДЕНТИФИКАТОР ОБЪЕКТА**</span><span class="sxs-lookup"><span data-stu-id="a7909-115">**OID**</span></span>|<span data-ttu-id="a7909-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a7909-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="a7909-117">Указывает идентификатор Объекта ASN.1, соответствующий алгоритм, реализованный класс.</span><span class="sxs-lookup"><span data-stu-id="a7909-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="a7909-118">**name**</span><span class="sxs-lookup"><span data-stu-id="a7909-118">**name**</span></span>|<span data-ttu-id="a7909-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a7909-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="a7909-120">Указывает значение для **имя** атрибута в [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) тег.</span><span class="sxs-lookup"><span data-stu-id="a7909-120">Specifies the value for the **name** attribute in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7909-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a7909-121">Child Elements</span></span>  
 <span data-ttu-id="a7909-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a7909-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7909-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a7909-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a7909-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="a7909-124">Element</span></span>|<span data-ttu-id="a7909-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a7909-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a7909-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a7909-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="a7909-127">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="a7909-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="a7909-128">Содержит `cryptographySettings` элемента.</span><span class="sxs-lookup"><span data-stu-id="a7909-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="a7909-129">Содержит сопоставления идентификатора объекта ASN.1 с классами.</span><span class="sxs-lookup"><span data-stu-id="a7909-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7909-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7909-130">Remarks</span></span>  
 <span data-ttu-id="a7909-131">Идентификаторы объектов ASN.1 определяют алгоритмы в некоторых криптографических форматах.</span><span class="sxs-lookup"><span data-stu-id="a7909-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="a7909-132">Понятные имена алгоритмов, которые нужно определить сопоставления идентификаторов объектов.</span><span class="sxs-lookup"><span data-stu-id="a7909-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7909-133">Пример</span><span class="sxs-lookup"><span data-stu-id="a7909-133">Example</span></span>  
 <span data-ttu-id="a7909-134">В следующем примере показано, как использовать  **\<oidEntry >** элемент для сопоставления идентификатора объекта хэш-алгоритма RIPEMD-160 с реализацией этого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="a7909-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7909-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a7909-135">See Also</span></span>  
 [<span data-ttu-id="a7909-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a7909-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a7909-137">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="a7909-137">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="a7909-138">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="a7909-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="a7909-139">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="a7909-139">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="a7909-140">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="a7909-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
