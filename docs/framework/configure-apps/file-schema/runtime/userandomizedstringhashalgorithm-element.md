---
title: '&lt;UseRandomizedStringHashAlgorithm&gt; элемент'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a515c3011905c4f5c18ed9d3e8edf489428c04d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a><span data-ttu-id="c2a48-102">&lt;UseRandomizedStringHashAlgorithm&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="c2a48-102">&lt;UseRandomizedStringHashAlgorithm&gt; Element</span></span>
<span data-ttu-id="c2a48-103">Определяет, вычисляет ли среда хэш-кодов для строк для каждого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c2a48-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="c2a48-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c2a48-104">\<configuration></span></span>  
<span data-ttu-id="c2a48-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="c2a48-105">\<runtime></span></span>  
<span data-ttu-id="c2a48-106">\<UseRandomizedStringHashAlgorithm ></span><span class="sxs-lookup"><span data-stu-id="c2a48-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a48-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2a48-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2a48-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c2a48-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c2a48-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c2a48-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2a48-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c2a48-110">Attributes</span></span>  
  
|<span data-ttu-id="c2a48-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c2a48-111">Attribute</span></span>|<span data-ttu-id="c2a48-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c2a48-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c2a48-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c2a48-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c2a48-114">Указывает, вычисляются ли хэш-кодов для строк на каждого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c2a48-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c2a48-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="c2a48-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c2a48-116">Значение</span><span class="sxs-lookup"><span data-stu-id="c2a48-116">Value</span></span>|<span data-ttu-id="c2a48-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c2a48-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="c2a48-118">Общеязыковая среда выполнения не вычисляет хэш-кодов для строк для каждого домена приложения; один алгоритм используется для вычисления хэш-кодов строки.</span><span class="sxs-lookup"><span data-stu-id="c2a48-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="c2a48-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c2a48-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="c2a48-120">Общеязыковая среда выполнения вычисляет хэш-кодов для строк для каждого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c2a48-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="c2a48-121">Одинаковых строк в различных доменах приложений и в разных процессах будет иметь другой хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="c2a48-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2a48-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c2a48-122">Child Elements</span></span>  
 <span data-ttu-id="c2a48-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c2a48-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2a48-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c2a48-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c2a48-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="c2a48-125">Element</span></span>|<span data-ttu-id="c2a48-126">Описание</span><span class="sxs-lookup"><span data-stu-id="c2a48-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c2a48-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2a48-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c2a48-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c2a48-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2a48-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2a48-129">Remarks</span></span>  
 <span data-ttu-id="c2a48-130">По умолчанию <xref:System.StringComparer> класса и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод использования один алгоритм хэширования, который создает согласованные хэш-код в доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="c2a48-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="c2a48-131">Это значение эквивалентно значению параметра `enabled` атрибут `<UseRandomizedStringHashAlgorithm>` элемент `0`.</span><span class="sxs-lookup"><span data-stu-id="c2a48-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="c2a48-132">Это алгоритм хэширования, используемый в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2a48-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="c2a48-133"><xref:System.StringComparer> Класса и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод также можно использовать другой алгоритм хэширования, который вычисляет хэш-коды для каждого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c2a48-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="c2a48-134">В результате хэш-кодов для строк, эквивалентный будут отличаться в доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="c2a48-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="c2a48-135">Это функция, включаемая; Чтобы использовать его, необходимо задать `enabled` атрибут `<UseRandomizedStringHashAlgorithm>` элемент `1`.</span><span class="sxs-lookup"><span data-stu-id="c2a48-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="c2a48-136">Поиск строки в хэш-таблицы, обычно является операцией o(1).</span><span class="sxs-lookup"><span data-stu-id="c2a48-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="c2a48-137">Однако при возникновении большое число конфликтов, уточняющего запроса может стать O (n<sup>2</sup>) операции.</span><span class="sxs-lookup"><span data-stu-id="c2a48-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="c2a48-138">Можно использовать `<UseRandomizedStringHashAlgorithm>` элемента конфигурации для формирования случайных алгоритма хэширования, домена приложения, в свою очередь ограничивает число потенциальные конфликты, особенно в том случае, если ключи, из которых вычисляется хэш-кодов, основаны на входных данных пользователями.</span><span class="sxs-lookup"><span data-stu-id="c2a48-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2a48-139">Пример</span><span class="sxs-lookup"><span data-stu-id="c2a48-139">Example</span></span>  
 <span data-ttu-id="c2a48-140">В следующем примере определяется `DisplayString` класс, который содержит частную строковую константу, `s`, значение которого является «Это строка».</span><span class="sxs-lookup"><span data-stu-id="c2a48-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="c2a48-141">Он также включает `ShowStringHashCode` метод, отображающий строковый параметр и его хэш-код, вместе с именем домена приложения, в котором выполняется метод.</span><span class="sxs-lookup"><span data-stu-id="c2a48-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="c2a48-142">При запуске примера без указания файла конфигурации будет выведен текст следующего вида.</span><span class="sxs-lookup"><span data-stu-id="c2a48-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="c2a48-143">Обратите внимание, что хэш-кодов для строки идентичны в двух доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="c2a48-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="c2a48-144">Однако если добавить следующий файл конфигурации в каталога примера и запустить пример, хэш-кодов для строк будут отличаться по доменам приложений.</span><span class="sxs-lookup"><span data-stu-id="c2a48-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c2a48-145">Если присутствует в файле конфигурации, в примере отображается следующий результат:</span><span class="sxs-lookup"><span data-stu-id="c2a48-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2a48-146">См. также</span><span class="sxs-lookup"><span data-stu-id="c2a48-146">See Also</span></span>  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
