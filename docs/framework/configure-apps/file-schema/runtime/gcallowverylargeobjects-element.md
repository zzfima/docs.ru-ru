---
title: Элемент <gcAllowVeryLargeObjects>
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: b6230833808ec45d702502e36f929db4e03173e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116791"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="af7ee-102">\<gcAllowVeryLargeObjects > элемент</span><span class="sxs-lookup"><span data-stu-id="af7ee-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="af7ee-103">На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="af7ee-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="af7ee-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af7ee-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af7ee-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="af7ee-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="af7ee-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcAllowVeryLargeObjects >**</span><span class="sxs-lookup"><span data-stu-id="af7ee-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af7ee-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af7ee-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af7ee-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="af7ee-108">Attributes and Elements</span></span>  
 <span data-ttu-id="af7ee-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="af7ee-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af7ee-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="af7ee-110">Attributes</span></span>  
  
|<span data-ttu-id="af7ee-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="af7ee-111">Attribute</span></span>|<span data-ttu-id="af7ee-112">Описание</span><span class="sxs-lookup"><span data-stu-id="af7ee-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="af7ee-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="af7ee-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="af7ee-114">Указывает, включены ли на 64-разрядных платформах массивы размером более 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="af7ee-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="af7ee-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="af7ee-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="af7ee-116">значения</span><span class="sxs-lookup"><span data-stu-id="af7ee-116">Value</span></span>|<span data-ttu-id="af7ee-117">Описание</span><span class="sxs-lookup"><span data-stu-id="af7ee-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="af7ee-118">Массивы объемом более 2 ГБ не включены.</span><span class="sxs-lookup"><span data-stu-id="af7ee-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="af7ee-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="af7ee-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="af7ee-120">Массивы объемом более 2 ГБ включены на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="af7ee-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af7ee-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="af7ee-121">Child Elements</span></span>  
 <span data-ttu-id="af7ee-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="af7ee-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af7ee-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="af7ee-123">Parent Elements</span></span>  
  
|<span data-ttu-id="af7ee-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="af7ee-124">Element</span></span>|<span data-ttu-id="af7ee-125">Описание</span><span class="sxs-lookup"><span data-stu-id="af7ee-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="af7ee-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af7ee-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="af7ee-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="af7ee-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af7ee-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="af7ee-128">Remarks</span></span>  
 <span data-ttu-id="af7ee-129">Использование этого элемента в файле конфигурации приложения позволяет использовать массивы размером более 2 ГБ, но не изменяет другие ограничения на размер объекта или размер массива:</span><span class="sxs-lookup"><span data-stu-id="af7ee-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="af7ee-130">Максимальное число элементов в массиве — <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af7ee-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="af7ee-131">Максимальный индекс в любом отдельном измерении — 2 147 483 591 (0x7FFFFFC7) для массивов байтов и массивов однобайтовых структур, а также 2 146 435 071 (0X7FEFFFFF) для других типов.</span><span class="sxs-lookup"><span data-stu-id="af7ee-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="af7ee-132">Максимальный размер строк и других объектов, не являющихся массивами, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="af7ee-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="af7ee-133">Перед включением этой функции убедитесь, что приложение не включает в себя ненадежный код, который предполагает, что размер всех массивов меньше 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="af7ee-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="af7ee-134">Например, ненадежный код, использующий массивы как буферы, может быть уязвим для переполнения буфера, если он написан на основе предположения, что массивы не будут превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="af7ee-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af7ee-135">Пример</span><span class="sxs-lookup"><span data-stu-id="af7ee-135">Example</span></span>  
 <span data-ttu-id="af7ee-136">В следующем примере показано, как включить эту функцию для приложения.</span><span class="sxs-lookup"><span data-stu-id="af7ee-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="af7ee-137">Поддерживается в</span><span class="sxs-lookup"><span data-stu-id="af7ee-137">Supported in</span></span>

<span data-ttu-id="af7ee-138">.NET Framework 4,5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="af7ee-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="af7ee-139">См. также</span><span class="sxs-lookup"><span data-stu-id="af7ee-139">See also</span></span>

- [<span data-ttu-id="af7ee-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="af7ee-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="af7ee-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="af7ee-141">Configuration File Schema</span></span>](../index.md)
