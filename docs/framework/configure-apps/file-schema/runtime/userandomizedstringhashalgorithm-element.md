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
ms.openlocfilehash: 49b53dcd4db7e0ac1e9079e763b8ed76c1088e0e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252203"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="c4a6f-102">\<Элемент > UseRandomizedStringHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="c4a6f-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="c4a6f-103">Определяет, вычисляет ли среда CLR хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="c4a6f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4a6f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4a6f-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4a6f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c4a6f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseRandomizedStringHashAlgorithm >**</span><span class="sxs-lookup"><span data-stu-id="c4a6f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4a6f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4a6f-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4a6f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c4a6f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c4a6f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4a6f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4a6f-110">Attributes</span></span>  
  
|<span data-ttu-id="c4a6f-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c4a6f-111">Attribute</span></span>|<span data-ttu-id="c4a6f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c4a6f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c4a6f-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c4a6f-114">Указывает, рассчитываются ли хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c4a6f-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="c4a6f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c4a6f-116">Значение</span><span class="sxs-lookup"><span data-stu-id="c4a6f-116">Value</span></span>|<span data-ttu-id="c4a6f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c4a6f-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="c4a6f-118">Среда CLR не выполняет вычисление хэш-кодов для строк на уровне отдельных приложений. для вычисления хэш-кодов строк используется один алгоритм.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="c4a6f-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="c4a6f-120">Среда CLR выдает хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="c4a6f-121">Идентичные строки в разных доменах приложений и в разных процессах будут иметь разные хэш-коды.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4a6f-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c4a6f-122">Child Elements</span></span>  
 <span data-ttu-id="c4a6f-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4a6f-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c4a6f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c4a6f-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="c4a6f-125">Element</span></span>|<span data-ttu-id="c4a6f-126">Описание</span><span class="sxs-lookup"><span data-stu-id="c4a6f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c4a6f-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c4a6f-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4a6f-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4a6f-129">Remarks</span></span>  
 <span data-ttu-id="c4a6f-130">По умолчанию <xref:System.StringComparer> класс <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> и метод используют один алгоритм хэширования, который создает согласованный хэш-код между доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="c4a6f-131">Это эквивалентно присвоению `enabled` атрибуту `<UseRandomizedStringHashAlgorithm>` элемента `0`значения.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="c4a6f-132">Это алгоритм хэширования, используемый в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="c4a6f-133"><xref:System.StringComparer> Класс<xref:System.String.GetHashCode%2A?displayProperty=nameWithType> и метод могут также использовать другой алгоритм хэширования, который выполняет вычисление хэш-кодов для каждого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="c4a6f-134">В результате хэш-коды для эквивалентных строк будут различаться в разных доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="c4a6f-135">Эта функция является обязательной. чтобы воспользоваться его преимуществами, необходимо задать `enabled` атрибуту `<UseRandomizedStringHashAlgorithm>` элемента `1`значение.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="c4a6f-136">Поиск строки в хэш-таблице обычно является операцией O (1).</span><span class="sxs-lookup"><span data-stu-id="c4a6f-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="c4a6f-137">Однако при возникновении большого количества конфликтов Поиск может стать операцией O (n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="c4a6f-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="c4a6f-138">Элемент `<UseRandomizedStringHashAlgorithm>` Configuration можно использовать для создания алгоритма случайного хэширования на домен приложения, который, в свою очередь, ограничивает количество потенциальных конфликтов, особенно если ключи, из которых рассчитываются хэш-коды, основаны на вводе данных. пользователями.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4a6f-139">Пример</span><span class="sxs-lookup"><span data-stu-id="c4a6f-139">Example</span></span>  
 <span data-ttu-id="c4a6f-140">В следующем примере определяется `DisplayString` класс, включающий закрытую строковую `s`константу, значение которой равно «это строка».</span><span class="sxs-lookup"><span data-stu-id="c4a6f-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="c4a6f-141">Он также включает `ShowStringHashCode` метод, который отображает строковое значение и его хэш-код, а также имя домена приложения, в котором выполняется метод.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="c4a6f-142">При запуске примера без указания файла конфигурации отображаются выходные данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="c4a6f-143">Обратите внимание, что хэш-коды строк идентичны в двух доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="c4a6f-144">Однако, если добавить следующий файл конфигурации в каталог примера, а затем запустить пример, хэш-коды для одной и той же строки будут отличаться для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c4a6f-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c4a6f-145">При наличии файла конфигурации в примере выводятся следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c4a6f-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4a6f-146">См. также</span><span class="sxs-lookup"><span data-stu-id="c4a6f-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
