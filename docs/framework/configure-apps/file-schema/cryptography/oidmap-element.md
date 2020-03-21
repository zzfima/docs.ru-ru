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
ms.openlocfilehash: a28eaf68fe1e6ab3f26592eee5ae2d0f2e7a3256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155171"
---
# <a name="oidmap-element"></a><span data-ttu-id="3f125-102">\<oidMap> Элемент</span><span class="sxs-lookup"><span data-stu-id="3f125-102">\<oidMap> Element</span></span>
<span data-ttu-id="3f125-103">Содержит отображение идентификатора объектов ASN.1 (OID) для классов.</span><span class="sxs-lookup"><span data-stu-id="3f125-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

<span data-ttu-id="3f125-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f125-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3f125-105">&nbsp;&nbsp;[**\<мскориб>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3f125-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="3f125-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<криптографияНастройки>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f125-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="3f125-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="3f125-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3f125-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f125-108">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f125-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3f125-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3f125-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3f125-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f125-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3f125-111">Attributes</span></span>  
 <span data-ttu-id="3f125-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="3f125-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3f125-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3f125-113">Child Elements</span></span>  
  
|<span data-ttu-id="3f125-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f125-114">Element</span></span>|<span data-ttu-id="3f125-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3f125-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f125-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="3f125-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="3f125-117">Карты ASN.1 OID с дружественным именем.</span><span class="sxs-lookup"><span data-stu-id="3f125-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3f125-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3f125-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3f125-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f125-119">Element</span></span>|<span data-ttu-id="3f125-120">Описание</span><span class="sxs-lookup"><span data-stu-id="3f125-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3f125-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f125-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="3f125-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="3f125-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="3f125-123">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="3f125-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3f125-124">Пример</span><span class="sxs-lookup"><span data-stu-id="3f125-124">Example</span></span>  
 <span data-ttu-id="3f125-125">Ниже приводится, как использовать \*\* \<элемент oidMap>\*\* содержать отображение OID для алгоритма хэша RIPEMD-160 для реализации этого хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="3f125-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3f125-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3f125-126">See also</span></span>

- [<span data-ttu-id="3f125-127">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="3f125-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3f125-128">Криптография Настройки Схема</span><span class="sxs-lookup"><span data-stu-id="3f125-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3f125-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="3f125-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="3f125-130">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="3f125-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="3f125-131">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="3f125-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
