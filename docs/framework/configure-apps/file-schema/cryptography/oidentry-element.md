---
title: Элемент <oidEntry>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: eed2a4d06906d2928be62aed20a75484c3eea946
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699771"
---
# <a name="oidentry-element"></a><span data-ttu-id="eaf3f-102">Элемент > @no__t 0oidEntry</span><span class="sxs-lookup"><span data-stu-id="eaf3f-102">\<oidEntry> Element</span></span>
<span data-ttu-id="eaf3f-103">Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
[<span data-ttu-id="eaf3f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="eaf3f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="eaf3f-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="eaf3f-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="eaf3f-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaf3f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="eaf3f-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaf3f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>  
<span data-ttu-id="eaf3f-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 **\<oidEntry >**</span><span class="sxs-lookup"><span data-stu-id="eaf3f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf3f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eaf3f-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaf3f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eaf3f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eaf3f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaf3f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eaf3f-112">Attributes</span></span>  
  
|<span data-ttu-id="eaf3f-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eaf3f-113">Attribute</span></span>|<span data-ttu-id="eaf3f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="eaf3f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eaf3f-115">**КОДА**</span><span class="sxs-lookup"><span data-stu-id="eaf3f-115">**OID**</span></span>|<span data-ttu-id="eaf3f-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="eaf3f-117">Указывает идентификатор объекта ASN. 1, соответствующий алгоритму, реализуемому вашим классом.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="eaf3f-118">**name**</span><span class="sxs-lookup"><span data-stu-id="eaf3f-118">**name**</span></span>|<span data-ttu-id="eaf3f-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="eaf3f-120">Задает значение для атрибута **Name** в теге [\<nameEntry >](nameentry-element.md) .</span><span class="sxs-lookup"><span data-stu-id="eaf3f-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eaf3f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eaf3f-121">Child Elements</span></span>  
 <span data-ttu-id="eaf3f-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eaf3f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eaf3f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eaf3f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="eaf3f-124">Element</span></span>|<span data-ttu-id="eaf3f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="eaf3f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eaf3f-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="eaf3f-127">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="eaf3f-128">`cryptographySettings` Содержит элемент.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="eaf3f-129">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaf3f-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="eaf3f-130">Remarks</span></span>  
 <span data-ttu-id="eaf3f-131">Идентификаторы объектов ASN. 1 обозначают алгоритмы в некоторых криптографических форматах.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="eaf3f-132">Сопоставьте идентификаторы объектов с понятными именами для алгоритмов, которые необходимо опознать.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaf3f-133">Пример</span><span class="sxs-lookup"><span data-stu-id="eaf3f-133">Example</span></span>  
 <span data-ttu-id="eaf3f-134">В следующем примере показано, как использовать элемент **\<oidEntry >** , чтобы связать идентификатор объекта для алгоритма хэширования RIPEMD-160 с реализацией этого хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="eaf3f-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eaf3f-135">См. также</span><span class="sxs-lookup"><span data-stu-id="eaf3f-135">See also</span></span>

- [<span data-ttu-id="eaf3f-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="eaf3f-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="eaf3f-137">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="eaf3f-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eaf3f-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="eaf3f-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="eaf3f-139">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="eaf3f-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="eaf3f-140">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="eaf3f-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
