---
title: Элемент <CompatSortNLSVersion>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 575d44ad9ecf445ba5d4b7fbe47032127ccb33ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252735"
---
# <a name="compatsortnlsversion-element"></a><span data-ttu-id="4119d-102">\<Элемент > Компатсортнлсверсион</span><span class="sxs-lookup"><span data-stu-id="4119d-102">\<CompatSortNLSVersion> Element</span></span>
<span data-ttu-id="4119d-103">Указывает, что при операциях сравнения строк среда выполнения должна использовать устаревший порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="4119d-103">Specifies that the runtime should use legacy sort orders when performing string comparisons.</span></span>  
  
<span data-ttu-id="4119d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4119d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4119d-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="4119d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="4119d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Компатсортнлсверсион >**</span><span class="sxs-lookup"><span data-stu-id="4119d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<CompatSortNLSVersion>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4119d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4119d-107">Syntax</span></span>  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4119d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4119d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4119d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4119d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4119d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4119d-110">Attributes</span></span>  
  
|<span data-ttu-id="4119d-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4119d-111">Attribute</span></span>|<span data-ttu-id="4119d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4119d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4119d-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4119d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4119d-114">Указывает код языка, порядок сортировки которого должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="4119d-114">Specifies the locale ID whose sort order is to be used.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4119d-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="4119d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4119d-116">Значение</span><span class="sxs-lookup"><span data-stu-id="4119d-116">Value</span></span>|<span data-ttu-id="4119d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4119d-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4119d-118">4096</span><span class="sxs-lookup"><span data-stu-id="4119d-118">4096</span></span>|<span data-ttu-id="4119d-119">Код языка, представляющий альтернативный порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="4119d-119">The locale ID that represents an alternate sort order.</span></span> <span data-ttu-id="4119d-120">В этом случае 4096 представляет порядок сортировки .NET Framework 3,5 и более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="4119d-120">In this case, 4096 represents the sort order of the .NET Framework 3.5 and earlier versions.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4119d-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4119d-121">Child Elements</span></span>  
 <span data-ttu-id="4119d-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="4119d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4119d-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4119d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4119d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="4119d-124">Element</span></span>|<span data-ttu-id="4119d-125">Описание</span><span class="sxs-lookup"><span data-stu-id="4119d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4119d-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4119d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4119d-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4119d-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4119d-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="4119d-128">Remarks</span></span>  
 <span data-ttu-id="4119d-129">Поскольку операции сравнения строк, сортировки и учета регистра, выполняемые <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> классом в .NET Framework 4, соответствуют стандарту Unicode 5,1, результаты методов сравнения строк, таких как <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> и, <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> могут отличаться от предыдущие версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4119d-129">Because string comparison, sorting, and casing operations performed by the <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> class in the .NET Framework 4 conform to the Unicode 5.1 standard, the results of string comparison methods such as <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> and <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> may differ from previous versions of the .NET Framework.</span></span> <span data-ttu-id="4119d-130">Если приложение зависит от устаревшего поведения, можно восстановить правила сравнения строк и сортировки, используемые в .NET Framework 3,5 и более ранних версиях, включив `<CompatSortNLSVersion>` элемент в файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4119d-130">If your application depends on legacy behavior, you can restore the string comparison and sorting rules used in the .NET Framework 3.5 and earlier versions by including the `<CompatSortNLSVersion>` element in your application's configuration file.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4119d-131">Для восстановления устаревших правил сравнения и сортировки строк также требуется, чтобы в локальной системе была доступна библиотека динамической компоновки sort00001000.dll.</span><span class="sxs-lookup"><span data-stu-id="4119d-131">Restoring legacy string comparison and sorting rules also requires the sort00001000.dll dynamic link library to be available on the local system.</span></span>  
  
 <span data-ttu-id="4119d-132">Устаревшие правила сортировки и сравнения строк можно также использовать в конкретном домене приложения, передав при создании этого домена строку "NetFx40_Legacy20SortingBehavior" в метод <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>.</span><span class="sxs-lookup"><span data-stu-id="4119d-132">You can also use legacy string sorting and comparison rules in a specific application domain by passing the string "NetFx40_Legacy20SortingBehavior" to the <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> method when you create the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4119d-133">Пример</span><span class="sxs-lookup"><span data-stu-id="4119d-133">Example</span></span>  
 <span data-ttu-id="4119d-134">В следующем примере создаются экземпляры двух объектов <xref:System.String> и вызывается метод <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>, чтобы сравнить их с использованием соглашений текущих языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="4119d-134">The following example instantiates two <xref:System.String> objects and calls the <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method to compare them by using the conventions of the current culture.</span></span>  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 <span data-ttu-id="4119d-135">При запуске примера на .NET Framework 4 отображаются следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4119d-135">When you run the example on the .NET Framework 4, it displays the following output.</span></span>  
  
```  
sta follows a in the sort order.  
```  
  
 <span data-ttu-id="4119d-136">Он совершенно отличается от выходных данных, отображаемых при выполнении примера на .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="4119d-136">This is completely different from the output that is displayed when you run the example on the .NET Framework 3.5.</span></span>  
  
```  
sta equals a in the sort order.  
```  
  
 <span data-ttu-id="4119d-137">Однако если добавить в каталог примера следующий файл конфигурации, а затем запустить пример на .NET Framework 4, то выходные данные идентичны тому, что были созданы в примере при его запуске на .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="4119d-137">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4, the output is identical to that produced by the example when it is run on the .NET Framework 3.5.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4119d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="4119d-138">See also</span></span>

- [<span data-ttu-id="4119d-139">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4119d-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4119d-140">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="4119d-140">Configuration File Schema</span></span>](../index.md)
