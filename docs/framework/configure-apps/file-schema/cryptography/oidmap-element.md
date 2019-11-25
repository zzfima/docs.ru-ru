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
ms.openlocfilehash: 5f055d6e665f68586191ab760fb5658eeb5c2cb2
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087985"
---
# <a name="oidmap-element"></a><span data-ttu-id="d3923-102">\<Оидмап > элемент</span><span class="sxs-lookup"><span data-stu-id="d3923-102">\<oidMap> Element</span></span>
<span data-ttu-id="d3923-103">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="d3923-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

<span data-ttu-id="d3923-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d3923-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d3923-105">&nbsp;&nbsp;[ **\<> mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d3923-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="d3923-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="d3923-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="d3923-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<оидмап >**</span><span class="sxs-lookup"><span data-stu-id="d3923-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d3923-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3923-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3923-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d3923-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d3923-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d3923-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3923-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3923-111">Attributes</span></span>  
 <span data-ttu-id="d3923-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d3923-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d3923-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d3923-113">Child Elements</span></span>  
  
|<span data-ttu-id="d3923-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3923-114">Element</span></span>|<span data-ttu-id="d3923-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d3923-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3923-116">\<Оидентри ></span><span class="sxs-lookup"><span data-stu-id="d3923-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="d3923-117">Сопоставляет идентификатор объекта ASN. 1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="d3923-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3923-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d3923-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d3923-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3923-119">Element</span></span>|<span data-ttu-id="d3923-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d3923-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d3923-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3923-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="d3923-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="d3923-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="d3923-123">Содержит элемент `cryptographySettings`.</span><span class="sxs-lookup"><span data-stu-id="d3923-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3923-124">Пример</span><span class="sxs-lookup"><span data-stu-id="d3923-124">Example</span></span>  
 <span data-ttu-id="d3923-125">В следующем примере показано, как использовать элемент **\<оидмап >** для включения сопоставления OID для алгоритма хэширования RIPEMD-160 к реализации этого хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="d3923-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d3923-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d3923-126">See also</span></span>

- [<span data-ttu-id="d3923-127">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d3923-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d3923-128">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="d3923-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d3923-129">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="d3923-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="d3923-130">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="d3923-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="d3923-131">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="d3923-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
