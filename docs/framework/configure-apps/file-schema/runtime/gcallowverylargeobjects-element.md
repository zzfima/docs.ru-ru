---
title: Элемент <gcAllowVeryLargeObjects>
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f638a880aaa21bc41d2575f3609dabae158c1a0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252573"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="28e47-102">\<Элемент > gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="28e47-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="28e47-103">На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="28e47-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="28e47-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="28e47-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="28e47-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="28e47-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="28e47-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcAllowVeryLargeObjects >**</span><span class="sxs-lookup"><span data-stu-id="28e47-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e47-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28e47-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28e47-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="28e47-108">Attributes and Elements</span></span>  
 <span data-ttu-id="28e47-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="28e47-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28e47-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="28e47-110">Attributes</span></span>  
  
|<span data-ttu-id="28e47-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="28e47-111">Attribute</span></span>|<span data-ttu-id="28e47-112">Описание</span><span class="sxs-lookup"><span data-stu-id="28e47-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="28e47-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="28e47-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="28e47-114">Указывает, включены ли на 64-разрядных платформах массивы размером более 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="28e47-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="28e47-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="28e47-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="28e47-116">Значение</span><span class="sxs-lookup"><span data-stu-id="28e47-116">Value</span></span>|<span data-ttu-id="28e47-117">Описание</span><span class="sxs-lookup"><span data-stu-id="28e47-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="28e47-118">Массивы объемом более 2 ГБ не включены.</span><span class="sxs-lookup"><span data-stu-id="28e47-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="28e47-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28e47-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="28e47-120">Массивы объемом более 2 ГБ включены на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="28e47-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28e47-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="28e47-121">Child Elements</span></span>  
 <span data-ttu-id="28e47-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="28e47-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28e47-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="28e47-123">Parent Elements</span></span>  
  
|<span data-ttu-id="28e47-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="28e47-124">Element</span></span>|<span data-ttu-id="28e47-125">Описание</span><span class="sxs-lookup"><span data-stu-id="28e47-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="28e47-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28e47-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="28e47-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="28e47-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28e47-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="28e47-128">Remarks</span></span>  
 <span data-ttu-id="28e47-129">Использование этого элемента в файле конфигурации приложения позволяет использовать массивы размером более 2 ГБ, но не изменяет другие ограничения на размер объекта или размер массива:</span><span class="sxs-lookup"><span data-stu-id="28e47-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="28e47-130">Максимальное число элементов в массиве — <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28e47-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="28e47-131">Максимальный индекс в любом отдельном измерении — 2 147 483 591 (0x7FFFFFC7) для массивов байтов и массивов однобайтовых структур, а также 2 146 435 071 (0X7FEFFFFF) для других типов.</span><span class="sxs-lookup"><span data-stu-id="28e47-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="28e47-132">Максимальный размер строк и других объектов, не являющихся массивами, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="28e47-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="28e47-133">Перед включением этой функции убедитесь, что приложение не включает в себя ненадежный код, который предполагает, что размер всех массивов меньше 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="28e47-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="28e47-134">Например, ненадежный код, использующий массивы как буферы, может быть уязвим для переполнения буфера, если он написан на основе предположения, что массивы не будут превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="28e47-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28e47-135">Пример</span><span class="sxs-lookup"><span data-stu-id="28e47-135">Example</span></span>  
 <span data-ttu-id="28e47-136">В следующем примере показано, как включить эту функцию для приложения.</span><span class="sxs-lookup"><span data-stu-id="28e47-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="28e47-137">Поддерживается в</span><span class="sxs-lookup"><span data-stu-id="28e47-137">Supported in</span></span>

<span data-ttu-id="28e47-138">.NET Framework 4,5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="28e47-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="28e47-139">См. также</span><span class="sxs-lookup"><span data-stu-id="28e47-139">See also</span></span>

- [<span data-ttu-id="28e47-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="28e47-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="28e47-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="28e47-141">Configuration File Schema</span></span>](../index.md)
