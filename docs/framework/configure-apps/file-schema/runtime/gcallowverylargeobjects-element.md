---
title: Элемент <gcAllowVeryLargeObjects>
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6db26d250de191559fdae0479aca9f41c147502
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663712"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="6d5d6-102">\<Элемент > gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="6d5d6-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="6d5d6-103">На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="6d5d6-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="6d5d6-104">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="6d5d6-104">\<configuration> Element</span></span>  
<span data-ttu-id="6d5d6-105">\<Элемент > среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6d5d6-105">\<runtime> Element</span></span>  
<span data-ttu-id="6d5d6-106">\<Элемент > gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="6d5d6-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d5d6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d5d6-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d5d6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6d5d6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6d5d6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d5d6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6d5d6-110">Attributes</span></span>  
  
|<span data-ttu-id="6d5d6-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6d5d6-111">Attribute</span></span>|<span data-ttu-id="6d5d6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6d5d6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6d5d6-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6d5d6-114">Указывает, включены ли на 64-разрядных платформах массивы размером более 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6d5d6-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="6d5d6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6d5d6-116">Значение</span><span class="sxs-lookup"><span data-stu-id="6d5d6-116">Value</span></span>|<span data-ttu-id="6d5d6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6d5d6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6d5d6-118">Массивы объемом более 2 ГБ не включены.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="6d5d6-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="6d5d6-120">Массивы объемом более 2 ГБ включены на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d5d6-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6d5d6-121">Child Elements</span></span>  
 <span data-ttu-id="6d5d6-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d5d6-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6d5d6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6d5d6-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d5d6-124">Element</span></span>|<span data-ttu-id="6d5d6-125">Описание</span><span class="sxs-lookup"><span data-stu-id="6d5d6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6d5d6-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6d5d6-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d5d6-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d5d6-128">Remarks</span></span>  
 <span data-ttu-id="6d5d6-129">Использование этого элемента в файле конфигурации приложения позволяет использовать массивы размером более 2 ГБ, но не изменяет другие ограничения на размер объекта или размер массива:</span><span class="sxs-lookup"><span data-stu-id="6d5d6-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="6d5d6-130">Максимальное число элементов в массиве — <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="6d5d6-131">Максимальный индекс в любом отдельном измерении — 2 147 483 591 (0x7FFFFFC7) для массивов байтов и массивов однобайтовых структур, а также 2 146 435 071 (0X7FEFFFFF) для других типов.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="6d5d6-132">Максимальный размер строк и других объектов, не являющихся массивами, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6d5d6-133">Перед включением этой функции убедитесь, что приложение не включает в себя ненадежный код, который предполагает, что размер всех массивов меньше 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="6d5d6-134">Например, ненадежный код, использующий массивы как буферы, может быть уязвим для переполнения буфера, если он написан на основе предположения, что массивы не будут превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d5d6-135">Пример</span><span class="sxs-lookup"><span data-stu-id="6d5d6-135">Example</span></span>  
 <span data-ttu-id="6d5d6-136">В следующем примере показано, как включить эту функцию для приложения.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="6d5d6-137">Поддерживается в</span><span class="sxs-lookup"><span data-stu-id="6d5d6-137">Supported in</span></span>

<span data-ttu-id="6d5d6-138">.NET Framework 4,5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="6d5d6-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="6d5d6-139">См. также</span><span class="sxs-lookup"><span data-stu-id="6d5d6-139">See also</span></span>

- [<span data-ttu-id="6d5d6-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6d5d6-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6d5d6-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="6d5d6-141">Configuration File Schema</span></span>](../index.md)
