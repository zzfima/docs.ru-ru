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
ms.openlocfilehash: 4564cf59e3b6cfbdcd9dca06cd0f966d524834de
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088552"
---
# <a name="oidentry-element"></a><span data-ttu-id="7f419-102">\<Оидентри > элемент</span><span class="sxs-lookup"><span data-stu-id="7f419-102">\<oidEntry> Element</span></span>
<span data-ttu-id="7f419-103">Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="7f419-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

<span data-ttu-id="7f419-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f419-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f419-105">&nbsp;&nbsp;[ **\<> mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7f419-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="7f419-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<криптографисеттингс >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f419-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="7f419-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<оидмап >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f419-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="7f419-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<оидентри >**</span><span class="sxs-lookup"><span data-stu-id="7f419-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7f419-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f419-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f419-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7f419-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f419-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7f419-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f419-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f419-112">Attributes</span></span>  
  
|<span data-ttu-id="7f419-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7f419-113">Attribute</span></span>|<span data-ttu-id="7f419-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7f419-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f419-115">**КОДА**</span><span class="sxs-lookup"><span data-stu-id="7f419-115">**OID**</span></span>|<span data-ttu-id="7f419-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="7f419-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="7f419-117">Указывает идентификатор объекта ASN. 1, соответствующий алгоритму, реализуемому вашим классом.</span><span class="sxs-lookup"><span data-stu-id="7f419-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="7f419-118">**name**</span><span class="sxs-lookup"><span data-stu-id="7f419-118">**name**</span></span>|<span data-ttu-id="7f419-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="7f419-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="7f419-120">Задает значение для атрибута **Name** в теге [\<элементе nameentry >](nameentry-element.md) .</span><span class="sxs-lookup"><span data-stu-id="7f419-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f419-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7f419-121">Child Elements</span></span>  
 <span data-ttu-id="7f419-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7f419-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f419-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7f419-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7f419-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f419-124">Element</span></span>|<span data-ttu-id="7f419-125">Описание</span><span class="sxs-lookup"><span data-stu-id="7f419-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7f419-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f419-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="7f419-127">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="7f419-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="7f419-128">Содержит элемент `cryptographySettings`.</span><span class="sxs-lookup"><span data-stu-id="7f419-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="7f419-129">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="7f419-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f419-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="7f419-130">Remarks</span></span>  
 <span data-ttu-id="7f419-131">Идентификаторы объектов ASN. 1 обозначают алгоритмы в некоторых криптографических форматах.</span><span class="sxs-lookup"><span data-stu-id="7f419-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="7f419-132">Сопоставьте идентификаторы объектов с понятными именами для алгоритмов, которые необходимо опознать.</span><span class="sxs-lookup"><span data-stu-id="7f419-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f419-133">Пример</span><span class="sxs-lookup"><span data-stu-id="7f419-133">Example</span></span>  
 <span data-ttu-id="7f419-134">В следующем примере показано, как использовать элемент **\<оидентри >** , чтобы связать идентификатор объекта для алгоритма хэширования RIPEMD-160 с реализацией этого хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="7f419-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f419-135">См. также</span><span class="sxs-lookup"><span data-stu-id="7f419-135">See also</span></span>

- [<span data-ttu-id="7f419-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="7f419-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7f419-137">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="7f419-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7f419-138">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="7f419-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="7f419-139">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="7f419-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="7f419-140">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="7f419-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
