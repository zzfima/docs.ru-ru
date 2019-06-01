---
title: Элемент <UseRandomizedStringHashAlgorithm>
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
ms.openlocfilehash: 91983a0910b272e621783f0fdb68242ddbd20f03
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456182"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="610ba-102">\<UseRandomizedStringHashAlgorithm > элемент</span><span class="sxs-lookup"><span data-stu-id="610ba-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="610ba-103">Определяет, вычисляет ли среда CLR хэш-коды для строк на основе доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="610ba-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="610ba-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="610ba-104">\<configuration></span></span>  
<span data-ttu-id="610ba-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="610ba-105">\<runtime></span></span>  
<span data-ttu-id="610ba-106">\<UseRandomizedStringHashAlgorithm ></span><span class="sxs-lookup"><span data-stu-id="610ba-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610ba-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="610ba-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="610ba-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="610ba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="610ba-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="610ba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="610ba-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="610ba-110">Attributes</span></span>  
  
|<span data-ttu-id="610ba-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="610ba-111">Attribute</span></span>|<span data-ttu-id="610ba-112">Описание</span><span class="sxs-lookup"><span data-stu-id="610ba-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="610ba-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="610ba-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="610ba-114">Указывает, вычисляются ли хэш-коды для строк на основе доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="610ba-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="610ba-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="610ba-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="610ba-116">Значение</span><span class="sxs-lookup"><span data-stu-id="610ba-116">Value</span></span>|<span data-ttu-id="610ba-117">Описание</span><span class="sxs-lookup"><span data-stu-id="610ba-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="610ba-118">Среда CLR не вычисляет хэш-коды для строк для каждого домена приложения; для вычисления хэш-кодов строк используется один алгоритм.</span><span class="sxs-lookup"><span data-stu-id="610ba-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="610ba-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="610ba-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="610ba-120">Среда CLR вычисляет хэш-коды для строк на основе доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="610ba-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="610ba-121">Одинаковых строк в различных доменах приложений и в различных процессах будут иметь разные хэш-коды.</span><span class="sxs-lookup"><span data-stu-id="610ba-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="610ba-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="610ba-122">Child Elements</span></span>  
 <span data-ttu-id="610ba-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="610ba-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="610ba-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="610ba-124">Parent Elements</span></span>  
  
|<span data-ttu-id="610ba-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="610ba-125">Element</span></span>|<span data-ttu-id="610ba-126">Описание</span><span class="sxs-lookup"><span data-stu-id="610ba-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="610ba-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="610ba-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="610ba-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="610ba-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="610ba-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="610ba-129">Remarks</span></span>  
 <span data-ttu-id="610ba-130">По умолчанию <xref:System.StringComparer> класс и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод использования один алгоритм хэширования, который создает последовательный хэш-код между доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="610ba-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="610ba-131">Это эквивалентно параметр `enabled` атрибут `<UseRandomizedStringHashAlgorithm>` элемент `0`.</span><span class="sxs-lookup"><span data-stu-id="610ba-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="610ba-132">Это алгоритм хэширования, используемый в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="610ba-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="610ba-133"><xref:System.StringComparer> Класс и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод можно также использовать другой алгоритм хэширования, который вычисляет хэш-коды для каждого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="610ba-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="610ba-134">В результате хэш-коды для эквивалентных строк будут отличаться в разных доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="610ba-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="610ba-135">Это функция в; Чтобы воспользоваться его преимуществами, необходимо задать `enabled` атрибут `<UseRandomizedStringHashAlgorithm>` элемент `1`.</span><span class="sxs-lookup"><span data-stu-id="610ba-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="610ba-136">Поиск строки в хэш-таблицы обычно является операцией O(1).</span><span class="sxs-lookup"><span data-stu-id="610ba-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="610ba-137">Тем не менее, если не возникает большое количество конфликтов, поиск может стать операцией O (n<sup>2</sup>) операции.</span><span class="sxs-lookup"><span data-stu-id="610ba-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="610ba-138">Можно использовать `<UseRandomizedStringHashAlgorithm>` элемент конфигурации, чтобы создать случайный алгоритм хэширования в каждом домене приложения, который в свою очередь ограничивает число потенциальных конфликтов, особенно в том случае, если ключи, из которых вычисляется хэш-кодов, основаны на входных данных пользователями.</span><span class="sxs-lookup"><span data-stu-id="610ba-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="610ba-139">Пример</span><span class="sxs-lookup"><span data-stu-id="610ba-139">Example</span></span>  
 <span data-ttu-id="610ba-140">В следующем примере определяется `DisplayString` класс, который включает закрытую строковую константу, `s`, значение которого равно «This is a string».</span><span class="sxs-lookup"><span data-stu-id="610ba-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="610ba-141">Он также включает `ShowStringHashCode` метод, отображающий значение строки и ее хэш-код вместе с именем домена приложения, в котором метод выполняется.</span><span class="sxs-lookup"><span data-stu-id="610ba-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="610ba-142">При выполнении примера без указания файла конфигурации отображается результат, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="610ba-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="610ba-143">Обратите внимание на то, что хэш-коды для строки идентичны в обоих доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="610ba-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="610ba-144">Тем не менее если добавить следующий файл конфигурации в каталог примеров и запустить пример, хэш-коды для той же строки будут отличаться по домену приложения.</span><span class="sxs-lookup"><span data-stu-id="610ba-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="610ba-145">Если присутствует в файле конфигурации, пример отображает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="610ba-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="610ba-146">См. также</span><span class="sxs-lookup"><span data-stu-id="610ba-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
