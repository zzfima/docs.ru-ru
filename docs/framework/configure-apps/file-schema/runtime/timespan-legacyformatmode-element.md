---
title: '&lt;TimeSpan_LegacyFormatMode&gt; элемент'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0faf2876680ef5ec3fc7373cae9f81eb091f47a1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753974"
---
# <a name="lttimespanlegacyformatmodegt-element"></a><span data-ttu-id="18f73-102">&lt;TimeSpan_LegacyFormatMode&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="18f73-102">&lt;TimeSpan_LegacyFormatMode&gt; Element</span></span>
<span data-ttu-id="18f73-103">Определяет, сохраняет ли среда выполнения устаревшее поведение при операциях форматирования со <xref:System.TimeSpan?displayProperty=nameWithType> значения.</span><span class="sxs-lookup"><span data-stu-id="18f73-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="18f73-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="18f73-104">\<configuration></span></span>  
<span data-ttu-id="18f73-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="18f73-105">\<runtime></span></span>  
<span data-ttu-id="18f73-106"><TimeSpan_LegacyFormatMode></span><span class="sxs-lookup"><span data-stu-id="18f73-106"><TimeSpan_LegacyFormatMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f73-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18f73-107">Syntax</span></span>  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18f73-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18f73-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18f73-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18f73-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18f73-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18f73-110">Attributes</span></span>  
  
|<span data-ttu-id="18f73-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18f73-111">Attribute</span></span>|<span data-ttu-id="18f73-112">Описание</span><span class="sxs-lookup"><span data-stu-id="18f73-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="18f73-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="18f73-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="18f73-114">Указывает, использует ли среда выполнения устаревшее поведение форматирования с <xref:System.TimeSpan?displayProperty=nameWithType> значения.</span><span class="sxs-lookup"><span data-stu-id="18f73-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="18f73-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="18f73-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="18f73-116">Значение</span><span class="sxs-lookup"><span data-stu-id="18f73-116">Value</span></span>|<span data-ttu-id="18f73-117">Описание</span><span class="sxs-lookup"><span data-stu-id="18f73-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="18f73-118">Среда выполнения не восстанавливает устаревшее поведение форматирования.</span><span class="sxs-lookup"><span data-stu-id="18f73-118">The runtime does not restore legacy formatting behavior.</span></span>|  
|`true`|<span data-ttu-id="18f73-119">Среда выполнения восстанавливает устаревшее поведение форматирования.</span><span class="sxs-lookup"><span data-stu-id="18f73-119">The runtime restores legacy formatting behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18f73-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18f73-120">Child Elements</span></span>  
 <span data-ttu-id="18f73-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="18f73-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18f73-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18f73-122">Parent Elements</span></span>  
  
|<span data-ttu-id="18f73-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="18f73-123">Element</span></span>|<span data-ttu-id="18f73-124">Описание</span><span class="sxs-lookup"><span data-stu-id="18f73-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="18f73-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18f73-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="18f73-126">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="18f73-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18f73-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="18f73-127">Remarks</span></span>  
 <span data-ttu-id="18f73-128">Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> структура реализует <xref:System.IFormattable> интерфейс и поддерживает операций со строками стандартных и пользовательских форматов форматирования.</span><span class="sxs-lookup"><span data-stu-id="18f73-128">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="18f73-129">Если метод синтаксического анализа встречает спецификатор неподдерживаемого формата или строку формата, он выдает <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="18f73-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="18f73-130">В предыдущих версиях платформы .NET Framework <xref:System.TimeSpan> структура не реализует <xref:System.IFormattable> и не поддерживает строки формата.</span><span class="sxs-lookup"><span data-stu-id="18f73-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="18f73-131">Тем не менее, многие разработчики ошибочно полагают, что <xref:System.TimeSpan> поддерживали набор строк формата и использовать их в [составного форматирования операций](../../../../../docs/standard/base-types/composite-formatting.md) с помощью методов, таких как <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="18f73-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="18f73-132">Как правило если тип реализует <xref:System.IFormattable> и поддерживает строк формата, вызовы методов форматирования с неподдерживаемый формат строки обычно throw <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="18f73-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="18f73-133">Тем не менее поскольку <xref:System.TimeSpan> не реализовал <xref:System.IFormattable>, среда выполнения учитывается строка формата и вместо этого вызов <xref:System.TimeSpan.ToString?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="18f73-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="18f73-134">Это означает, что, несмотря на то, что строки формата не оказывает никакого влияния на операции форматирования, их присутствие не привел к <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="18f73-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="18f73-135">Для случаев, в которых устаревший код передает составной метод форматирования и недопустимую строку формата, и этот код не может быть перекомпилирован, можно использовать `<TimeSpan_LegacyFormatMode>` элемент для восстановления предыдущих версий <xref:System.TimeSpan> поведение.</span><span class="sxs-lookup"><span data-stu-id="18f73-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="18f73-136">При задании `enabled` атрибут этого элемента для `true`, составного форматирования результаты метода при вызове <xref:System.TimeSpan.ToString?displayProperty=nameWithType> вместо <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>и <xref:System.FormatException> не возникает.</span><span class="sxs-lookup"><span data-stu-id="18f73-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18f73-137">Пример</span><span class="sxs-lookup"><span data-stu-id="18f73-137">Example</span></span>  
 <span data-ttu-id="18f73-138">В следующем примере создается <xref:System.TimeSpan> объекта и предпринимает попытку отформатируйте его с <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> метода с использованием строки стандартного формата, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="18f73-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 <span data-ttu-id="18f73-139">При выполнении примера в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] или в более ранней версии, он отображает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="18f73-139">When you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] or on an earlier version, it displays the following output:</span></span>  
  
```  
12:30:45  
```  
  
 <span data-ttu-id="18f73-140">Они сильно отличаются от выходных данных, получаемых при выполнении примера в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] или более поздней версии:</span><span class="sxs-lookup"><span data-stu-id="18f73-140">This differs markedly from the output if you run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version:</span></span>  
  
```  
Invalid Format  
```  
  
 <span data-ttu-id="18f73-141">Однако если в каталог примера добавить представленный ниже файл конфигурации и запустить пример в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] или более поздней версии, выходные данные будут идентичны данным, созданным примером при его запуске в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18f73-141">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version, the output is identical to that produced by the example when it is run on [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18f73-142">См. также</span><span class="sxs-lookup"><span data-stu-id="18f73-142">See Also</span></span>  
 [<span data-ttu-id="18f73-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="18f73-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="18f73-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="18f73-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
