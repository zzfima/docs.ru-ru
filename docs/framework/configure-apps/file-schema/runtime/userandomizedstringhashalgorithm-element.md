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
ms.openlocfilehash: 3863bc1376d89ef804022fb9c87fac3a25fc910f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968835"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="ede4b-102">\<UseRandomizedStringHashAlgorithm > элемент</span><span class="sxs-lookup"><span data-stu-id="ede4b-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="ede4b-103">Определяет, вычисляет ли среда CLR хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ede4b-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="ede4b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ede4b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ede4b-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="ede4b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ede4b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseRandomizedStringHashAlgorithm >**</span><span class="sxs-lookup"><span data-stu-id="ede4b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede4b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ede4b-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ede4b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ede4b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ede4b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ede4b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ede4b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ede4b-110">Attributes</span></span>  
  
|<span data-ttu-id="ede4b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ede4b-111">Attribute</span></span>|<span data-ttu-id="ede4b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ede4b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ede4b-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ede4b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ede4b-114">Указывает, рассчитываются ли хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ede4b-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ede4b-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="ede4b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ede4b-116">значения</span><span class="sxs-lookup"><span data-stu-id="ede4b-116">Value</span></span>|<span data-ttu-id="ede4b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ede4b-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="ede4b-118">Среда CLR не выполняет вычисление хэш-кодов для строк на уровне отдельных приложений. для вычисления хэш-кодов строк используется один алгоритм.</span><span class="sxs-lookup"><span data-stu-id="ede4b-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="ede4b-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ede4b-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="ede4b-120">Среда CLR выдает хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ede4b-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="ede4b-121">Идентичные строки в разных доменах приложений и в разных процессах будут иметь разные хэш-коды.</span><span class="sxs-lookup"><span data-stu-id="ede4b-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ede4b-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ede4b-122">Child Elements</span></span>  
 <span data-ttu-id="ede4b-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ede4b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ede4b-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ede4b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ede4b-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="ede4b-125">Element</span></span>|<span data-ttu-id="ede4b-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ede4b-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ede4b-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ede4b-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ede4b-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ede4b-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ede4b-129">Заметки</span><span class="sxs-lookup"><span data-stu-id="ede4b-129">Remarks</span></span>  
 <span data-ttu-id="ede4b-130">По умолчанию класс <xref:System.StringComparer> и метод <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> используют один алгоритм хэширования, который создает согласованный хэш-код между доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="ede4b-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="ede4b-131">Это эквивалентно установке атрибута `enabled` элемента `<UseRandomizedStringHashAlgorithm>` для `0`.</span><span class="sxs-lookup"><span data-stu-id="ede4b-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="ede4b-132">Это алгоритм хэширования, используемый в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ede4b-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="ede4b-133">Класс <xref:System.StringComparer> и метод <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> также могут использовать другой алгоритм хэширования, который выполняет вычисление хэш-кодов для каждого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ede4b-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="ede4b-134">В результате хэш-коды для эквивалентных строк будут различаться в разных доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="ede4b-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="ede4b-135">Эта функция является обязательной. чтобы воспользоваться его преимуществами, необходимо задать атрибуту `enabled` элемента `<UseRandomizedStringHashAlgorithm>` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="ede4b-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="ede4b-136">Поиск строки в хэш-таблице обычно является операцией O (1).</span><span class="sxs-lookup"><span data-stu-id="ede4b-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="ede4b-137">Однако при возникновении большого количества конфликтов Поиск может стать операцией O (n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="ede4b-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="ede4b-138">Можно использовать элемент конфигурации `<UseRandomizedStringHashAlgorithm>`, чтобы создать случайный алгоритм хэширования для каждого домена приложений, который, в свою очередь, ограничивает количество потенциальных конфликтов, особенно когда ключи, из которых вычисляется хэш-коды, основываются на вводе данных. пользователей.</span><span class="sxs-lookup"><span data-stu-id="ede4b-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ede4b-139">Пример</span><span class="sxs-lookup"><span data-stu-id="ede4b-139">Example</span></span>  
 <span data-ttu-id="ede4b-140">В следующем примере определяется класс `DisplayString`, содержащий закрытую строковую константу, `s`, значением которой является строка.</span><span class="sxs-lookup"><span data-stu-id="ede4b-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="ede4b-141">Он также включает метод `ShowStringHashCode`, который отображает строковое значение и его хэш-код, а также имя домена приложения, в котором выполняется метод.</span><span class="sxs-lookup"><span data-stu-id="ede4b-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="ede4b-142">При запуске примера без указания файла конфигурации отображаются выходные данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="ede4b-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="ede4b-143">Обратите внимание, что хэш-коды строк идентичны в двух доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="ede4b-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="ede4b-144">Однако, если добавить следующий файл конфигурации в каталог примера, а затем запустить пример, хэш-коды для одной и той же строки будут отличаться для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ede4b-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="ede4b-145">При наличии файла конфигурации в примере выводятся следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="ede4b-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="ede4b-146">См. также</span><span class="sxs-lookup"><span data-stu-id="ede4b-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
