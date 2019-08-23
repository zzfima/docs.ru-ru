---
title: Элемент <oidMap>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: d2929167f5a7de96a868cd1ac884d2203d09dfb6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927525"
---
# <a name="oidmap-element"></a><span data-ttu-id="23345-102">\<Элемент > Оидмап</span><span class="sxs-lookup"><span data-stu-id="23345-102">\<oidMap> Element</span></span>
<span data-ttu-id="23345-103">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="23345-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="23345-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="23345-104">\<configuration></span></span>  
<span data-ttu-id="23345-105">\<> mscorlib</span><span class="sxs-lookup"><span data-stu-id="23345-105">\<mscorlib></span></span>  
<span data-ttu-id="23345-106">\<Криптографисеттингс ></span><span class="sxs-lookup"><span data-stu-id="23345-106">\<cryptographySettings></span></span>  
<span data-ttu-id="23345-107">\<Оидмап ></span><span class="sxs-lookup"><span data-stu-id="23345-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23345-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23345-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23345-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="23345-109">Attributes and Elements</span></span>  
 <span data-ttu-id="23345-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="23345-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23345-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="23345-111">Attributes</span></span>  
 <span data-ttu-id="23345-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="23345-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="23345-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="23345-113">Child Elements</span></span>  
  
|<span data-ttu-id="23345-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="23345-114">Element</span></span>|<span data-ttu-id="23345-115">Описание</span><span class="sxs-lookup"><span data-stu-id="23345-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23345-116">\<Оидентри ></span><span class="sxs-lookup"><span data-stu-id="23345-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="23345-117">Сопоставляет идентификатор объекта ASN. 1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="23345-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23345-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="23345-118">Parent Elements</span></span>  
  
|<span data-ttu-id="23345-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="23345-119">Element</span></span>|<span data-ttu-id="23345-120">Описание</span><span class="sxs-lookup"><span data-stu-id="23345-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="23345-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="23345-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="23345-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="23345-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="23345-123">`cryptographySettings` Содержит элемент.</span><span class="sxs-lookup"><span data-stu-id="23345-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23345-124">Пример</span><span class="sxs-lookup"><span data-stu-id="23345-124">Example</span></span>  
 <span data-ttu-id="23345-125">В следующем примере показано, как использовать  **\<элемент оидмап >** для включения сопоставления OID для алгоритма хэширования RIPEMD-160 к реализации этого хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="23345-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23345-126">См. также</span><span class="sxs-lookup"><span data-stu-id="23345-126">See also</span></span>

- [<span data-ttu-id="23345-127">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="23345-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="23345-128">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="23345-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="23345-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="23345-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="23345-130">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="23345-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="23345-131">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="23345-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
