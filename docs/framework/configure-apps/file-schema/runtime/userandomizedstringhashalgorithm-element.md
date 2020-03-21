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
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153781"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="4f368-102">\<UseRandomizedStringHashAlgorithm> элемент</span><span class="sxs-lookup"><span data-stu-id="4f368-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="4f368-103">Определяет, вычисляет ли общее время выполнения языка хэш-коды для строк на основе домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4f368-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="4f368-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f368-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f368-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f368-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="4f368-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span><span class="sxs-lookup"><span data-stu-id="4f368-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f368-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f368-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f368-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4f368-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4f368-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4f368-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f368-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4f368-110">Attributes</span></span>  
  
|<span data-ttu-id="4f368-111">attribute</span><span class="sxs-lookup"><span data-stu-id="4f368-111">Attribute</span></span>|<span data-ttu-id="4f368-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4f368-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4f368-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4f368-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4f368-114">Уточняется, рассчитываются ли хэш-коды для строк на основе домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4f368-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4f368-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="4f368-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4f368-116">Значение</span><span class="sxs-lookup"><span data-stu-id="4f368-116">Value</span></span>|<span data-ttu-id="4f368-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4f368-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="4f368-118">Общее время выполнения языка не вычисляет хэш-коды для строк на основе домена в приложении; для расчета кодов хэша строк используется один алгоритм.</span><span class="sxs-lookup"><span data-stu-id="4f368-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="4f368-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4f368-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="4f368-120">Общий язык runtime вычисляет коды хэша для строк на основе домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4f368-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="4f368-121">Идентичные строки в разных доменах приложений и в разных процессах будут иметь разные хэш-коды.</span><span class="sxs-lookup"><span data-stu-id="4f368-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f368-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4f368-122">Child Elements</span></span>  
 <span data-ttu-id="4f368-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="4f368-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f368-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4f368-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4f368-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f368-125">Element</span></span>|<span data-ttu-id="4f368-126">Описание</span><span class="sxs-lookup"><span data-stu-id="4f368-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4f368-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f368-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4f368-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f368-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f368-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f368-129">Remarks</span></span>  
 <span data-ttu-id="4f368-130">По умолчанию <xref:System.StringComparer> класс <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> и метод используют единый алгоритм хэширования, который производит согласованный хэш-код в доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="4f368-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="4f368-131">Это эквивалентно настройке атрибута `enabled` элемента. `<UseRandomizedStringHashAlgorithm>` `0`</span><span class="sxs-lookup"><span data-stu-id="4f368-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="4f368-132">Это алгоритм хэширования, используемый в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="4f368-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="4f368-133">Класс <xref:System.StringComparer> и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод также могут использовать другой алгоритм хэширования, который вычисляет хэш-коды на основе домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4f368-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="4f368-134">В результате хэш-коды для эквивалентных строк будут отличаться в разных доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="4f368-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="4f368-135">Это функция выбора; чтобы воспользоваться им, вы `enabled` должны установить `1`атрибут элемента. `<UseRandomizedStringHashAlgorithm>`</span><span class="sxs-lookup"><span data-stu-id="4f368-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="4f368-136">Поиск строки в таблице хэша обычно является операцией O(1).</span><span class="sxs-lookup"><span data-stu-id="4f368-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="4f368-137">Однако при большом количестве столкновений поиск может стать операцией O(n<sup>2).</sup></span><span class="sxs-lookup"><span data-stu-id="4f368-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="4f368-138">Элемент `<UseRandomizedStringHashAlgorithm>` конфигурации можно использовать для генерации алгоритма случайного хэширования в домене приложения, что, в свою очередь, ограничивает количество потенциальных столкновений, особенно когда ключи, из которых рассчитываются хэш-коды, основаны на ввода данных пользователями.</span><span class="sxs-lookup"><span data-stu-id="4f368-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f368-139">Пример</span><span class="sxs-lookup"><span data-stu-id="4f368-139">Example</span></span>  
 <span data-ttu-id="4f368-140">Следующий пример определяет `DisplayString` класс, который включает `s`в себя константу частной строки, значение которого "Это строка".</span><span class="sxs-lookup"><span data-stu-id="4f368-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="4f368-141">Он также включает метод `ShowStringHashCode`, который отображает значение строки и ее хэш-код вместе с именем домена приложения, в котором метод выполняется.</span><span class="sxs-lookup"><span data-stu-id="4f368-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="4f368-142">При выполнении примера без указания файла конфигурации он отображает подобный следующему вывод.</span><span class="sxs-lookup"><span data-stu-id="4f368-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="4f368-143">Обратите внимание, что хэш-коды для строки идентичны в обоих доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="4f368-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="4f368-144">Однако при добавлении следующего файла конфигурации в каталог примеров и запуске примера, хэш-коды для той же строки будут отличаться по домену приложения.</span><span class="sxs-lookup"><span data-stu-id="4f368-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="4f368-145">Если файл конфигурации существует, пример отображает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="4f368-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f368-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4f368-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
