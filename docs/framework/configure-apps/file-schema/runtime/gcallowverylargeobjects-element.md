---
title: Элемент <gcAllowVeryLargeObjects>
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19103b2ac6e6dbba930050074fcea3cfd5a97661
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098020"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="caeef-102">\<gcAllowVeryLargeObjects > элемент</span><span class="sxs-lookup"><span data-stu-id="caeef-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="caeef-103">На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="caeef-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="caeef-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="caeef-104">\<configuration> Element</span></span>  
<span data-ttu-id="caeef-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="caeef-105">\<runtime> Element</span></span>  
<span data-ttu-id="caeef-106">\<gcAllowVeryLargeObjects > элемент</span><span class="sxs-lookup"><span data-stu-id="caeef-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caeef-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caeef-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caeef-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="caeef-108">Attributes and Elements</span></span>  
 <span data-ttu-id="caeef-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="caeef-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caeef-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="caeef-110">Attributes</span></span>  
  
|<span data-ttu-id="caeef-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="caeef-111">Attribute</span></span>|<span data-ttu-id="caeef-112">Описание</span><span class="sxs-lookup"><span data-stu-id="caeef-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="caeef-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="caeef-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="caeef-114">Указывает, включены ли массивов, размер которых превышает 2 ГБ в общий размер на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="caeef-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="caeef-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="caeef-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="caeef-116">Значение</span><span class="sxs-lookup"><span data-stu-id="caeef-116">Value</span></span>|<span data-ttu-id="caeef-117">Описание</span><span class="sxs-lookup"><span data-stu-id="caeef-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="caeef-118">Больше, чем 2 ГБ, общий размер массивов не включены.</span><span class="sxs-lookup"><span data-stu-id="caeef-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="caeef-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="caeef-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="caeef-120">Больше, чем 2 ГБ, общий размер массивов включены на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="caeef-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="caeef-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="caeef-121">Child Elements</span></span>  
 <span data-ttu-id="caeef-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="caeef-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="caeef-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="caeef-123">Parent Elements</span></span>  
  
|<span data-ttu-id="caeef-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="caeef-124">Element</span></span>|<span data-ttu-id="caeef-125">Описание</span><span class="sxs-lookup"><span data-stu-id="caeef-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="caeef-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="caeef-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="caeef-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="caeef-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caeef-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="caeef-128">Remarks</span></span>  
 <span data-ttu-id="caeef-129">С помощью этого элемента в файле конфигурации приложения позволяет использовать массивы, размер которых превышает 2 ГБ, но не изменяет другие ограничения на размер объекта или массива:</span><span class="sxs-lookup"><span data-stu-id="caeef-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
-   <span data-ttu-id="caeef-130">Максимальное количество элементов в массиве является <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="caeef-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="caeef-131">Максимальный индекс в любом измерении единый — 2,147,483,591 (0x7FFFFFC7) для массивов байтов и массивы структур однобайтовых и 2,146,435,071 (0X7FEFFFFF) для других типов.</span><span class="sxs-lookup"><span data-stu-id="caeef-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
-   <span data-ttu-id="caeef-132">Максимальный размер строки и другие не являющиеся массивами объекты не изменяется.</span><span class="sxs-lookup"><span data-stu-id="caeef-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="caeef-133">Прежде чем включать эту функцию, убедитесь, что приложение не содержит небезопасный код, который предполагается, что все массивы меньше, чем размером 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="caeef-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="caeef-134">Например небезопасный код, который использует массивы в качестве буфера, можно привести к переполнению буфера записывается на предположении, что массивы не может превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="caeef-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caeef-135">Пример</span><span class="sxs-lookup"><span data-stu-id="caeef-135">Example</span></span>  
 <span data-ttu-id="caeef-136">В следующем примере показано, как включить эту функцию для приложения.</span><span class="sxs-lookup"><span data-stu-id="caeef-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="caeef-137">См. также</span><span class="sxs-lookup"><span data-stu-id="caeef-137">See also</span></span>

- [<span data-ttu-id="caeef-138">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="caeef-138">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="caeef-139">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="caeef-139">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
