---
title: Элемент <gcAllowVeryLargeObjects>
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154131"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="00873-102">\<gcAllowVeryLargeObjects> Элемент</span><span class="sxs-lookup"><span data-stu-id="00873-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="00873-103">На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="00873-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="00873-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00873-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00873-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="00873-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="00873-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span><span class="sxs-lookup"><span data-stu-id="00873-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00873-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00873-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00873-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="00873-108">Attributes and Elements</span></span>  
 <span data-ttu-id="00873-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="00873-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00873-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="00873-110">Attributes</span></span>  
  
|<span data-ttu-id="00873-111">attribute</span><span class="sxs-lookup"><span data-stu-id="00873-111">Attribute</span></span>|<span data-ttu-id="00873-112">Описание</span><span class="sxs-lookup"><span data-stu-id="00873-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="00873-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="00873-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="00873-114">Уточняется, включены ли массивы, превышают 2 ГБ общего размера, на 64-битных платформах.</span><span class="sxs-lookup"><span data-stu-id="00873-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="00873-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="00873-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="00873-116">Значение</span><span class="sxs-lookup"><span data-stu-id="00873-116">Value</span></span>|<span data-ttu-id="00873-117">Описание</span><span class="sxs-lookup"><span data-stu-id="00873-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="00873-118">Массивы размером более 2 ГБ не включены.</span><span class="sxs-lookup"><span data-stu-id="00873-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="00873-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00873-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="00873-120">На 64-битных платформах включены массивы, превышают 2 ГБ общего размера.</span><span class="sxs-lookup"><span data-stu-id="00873-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00873-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="00873-121">Child Elements</span></span>  
 <span data-ttu-id="00873-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="00873-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00873-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="00873-123">Parent Elements</span></span>  
  
|<span data-ttu-id="00873-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="00873-124">Element</span></span>|<span data-ttu-id="00873-125">Описание</span><span class="sxs-lookup"><span data-stu-id="00873-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="00873-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00873-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="00873-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="00873-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00873-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="00873-128">Remarks</span></span>  
 <span data-ttu-id="00873-129">Использование этого элемента в файле конфигурации приложения позволяет массивы размером больше 2 ГБ, но не изменяют другие ограничения на размер объекта или размер массива:</span><span class="sxs-lookup"><span data-stu-id="00873-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="00873-130">Максимальное количество элементов в <xref:System.UInt32.MaxValue?displayProperty=nameWithType>массиве.</span><span class="sxs-lookup"><span data-stu-id="00873-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="00873-131">Максимальный индекс в любом измерении составляет 2 147 483 591 (0x7FFFFFF7) для байт-массивов и массивов однобайных структур и 2 146 435 071 (0X7FEFFFFF) для других типов.</span><span class="sxs-lookup"><span data-stu-id="00873-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="00873-132">Максимальный размер строк и других объектов, не связанных с массивом, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="00873-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="00873-133">Прежде чем включить эту функцию, убедитесь, что приложение не содержит небезопасный код, который предполагает, что все массивы меньше 2 ГБ в размерах.</span><span class="sxs-lookup"><span data-stu-id="00873-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="00873-134">Например, небезопасный код, в использовании массивов в качестве буферов, может быть подвержен перерасходу буферов, если он будет записан исходя из предположения, что массивы не превысят 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="00873-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00873-135">Пример</span><span class="sxs-lookup"><span data-stu-id="00873-135">Example</span></span>  
 <span data-ttu-id="00873-136">В следующем примере показано, как включить эту функцию для приложения.</span><span class="sxs-lookup"><span data-stu-id="00873-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="00873-137">Поддерживается в</span><span class="sxs-lookup"><span data-stu-id="00873-137">Supported in</span></span>

<span data-ttu-id="00873-138">.NET Framework 4.5 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="00873-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="00873-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="00873-139">See also</span></span>

- [<span data-ttu-id="00873-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="00873-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="00873-141">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="00873-141">Configuration File Schema</span></span>](../index.md)
