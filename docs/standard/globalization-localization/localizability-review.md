---
title: Обзор локализуемости
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b19bc78f44781923df6873ccc9720f4605731976
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086509"
---
# <a name="localizability-review"></a><span data-ttu-id="2ba69-102">Обзор локализуемости</span><span class="sxs-lookup"><span data-stu-id="2ba69-102">Localizability Review</span></span>
<span data-ttu-id="2ba69-103">Проверка локализуемости — промежуточный шаг в разработке международных приложений.</span><span class="sxs-lookup"><span data-stu-id="2ba69-103">The localizability review is an intermediate step in the development of a world-ready application.</span></span> <span data-ttu-id="2ba69-104">Это проверка, что международное приложение готово к локализации, которая позволяет определить код и элементы пользовательского интерфейса, требующие специальной обработки.</span><span class="sxs-lookup"><span data-stu-id="2ba69-104">It verifies that a globalized application is ready for localization and identifies any code or any aspects of the user interface that require special handling.</span></span> <span data-ttu-id="2ba69-105">Этот шаг также помогает удостовериться, что процесс локализации не внесет в приложение функциональных дефектов.</span><span class="sxs-lookup"><span data-stu-id="2ba69-105">This step also helps ensure that the localization process will not introduce any functional defects into your application.</span></span> <span data-ttu-id="2ba69-106">Когда все проблемы, выявленные при анализе локализуемости, устранены, приложение готово для локализации.</span><span class="sxs-lookup"><span data-stu-id="2ba69-106">When all the issues raised by the localizability review have been addressed, your application is ready for localization.</span></span> <span data-ttu-id="2ba69-107">Исчерпывающая проверка локализуемости позволяет не изменять исходный код при локализации.</span><span class="sxs-lookup"><span data-stu-id="2ba69-107">If the localizability review is thorough, you should not have to modify any source code during the localization process.</span></span>  
  
 <span data-ttu-id="2ba69-108">Проверка локализуемости состоит из трех следующих проверок.</span><span class="sxs-lookup"><span data-stu-id="2ba69-108">The localizability review consists of the following three checks:</span></span>  
  
-   [<span data-ttu-id="2ba69-109">Реализованы ли рекомендации по глобализации?</span><span class="sxs-lookup"><span data-stu-id="2ba69-109">Are the globalization recommendations implemented?</span></span>](#global)  
  
-   [<span data-ttu-id="2ba69-110">Правильно ли обрабатываются компоненты, чувствительные к языку и региональным параметрам?</span><span class="sxs-lookup"><span data-stu-id="2ba69-110">Are culture-sensitive features handled correctly?</span></span>](#culture)  
  
-   [<span data-ttu-id="2ba69-111">Проводилось ли тестирование приложения с данными на других языках?</span><span class="sxs-lookup"><span data-stu-id="2ba69-111">Have you tested your application with international data?</span></span>](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a><span data-ttu-id="2ba69-112">Реализация рекомендаций по глобализации</span><span class="sxs-lookup"><span data-stu-id="2ba69-112">Implementing globalization recommendations</span></span>  
 <span data-ttu-id="2ba69-113">Если при проектировании и разработке приложения вы не забывали о локализации и соблюдали все рекомендации, описанные в статье [Глобализация](../../../docs/standard/globalization-localization/globalization.md), анализ локализуемости станет лишь формальным этапом контроля качества.</span><span class="sxs-lookup"><span data-stu-id="2ba69-113">If you have designed and developed your application with localization in mind, and if you have followed the recommendations discussed in the [Globalization](../../../docs/standard/globalization-localization/globalization.md) article, the localizability review will largely be a quality assurance pass.</span></span> <span data-ttu-id="2ba69-114">В противном случае на этом этапа вам предстоит изучить и внедрить рекомендации по [глобализации](../../../docs/standard/globalization-localization/globalization.md), а также исправить все проблемы в исходном коде, которые будут мешать локализации.</span><span class="sxs-lookup"><span data-stu-id="2ba69-114">Otherwise, during this stage you should review and implement the recommendations for [globalization](../../../docs/standard/globalization-localization/globalization.md), and fix the errors in source code that prevent localization.</span></span>  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a><span data-ttu-id="2ba69-115">Обработка возможностей, чувствительных к языковым и региональным параметрам</span><span class="sxs-lookup"><span data-stu-id="2ba69-115">Handling culture-sensitive features</span></span>  
 <span data-ttu-id="2ba69-116">Платформа .NET Framework не обеспечивает программную поддержку в нескольких областях, которые значительно отличаются в зависимости от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="2ba69-116">The .NET Framework does not provide programmatic support in a number of areas that vary widely by culture.</span></span> <span data-ttu-id="2ba69-117">В большинстве случаев для обработки следующих функциональных областей необходимо писать собственный код.</span><span class="sxs-lookup"><span data-stu-id="2ba69-117">In most cases, you have to write custom code to handle feature areas like the following:</span></span>  
  
-   <span data-ttu-id="2ba69-118">Адреса.</span><span class="sxs-lookup"><span data-stu-id="2ba69-118">Addresses.</span></span>  
  
-   <span data-ttu-id="2ba69-119">Телефонные номера.</span><span class="sxs-lookup"><span data-stu-id="2ba69-119">Telephone numbers.</span></span>  
  
-   <span data-ttu-id="2ba69-120">Размеры бумаги.</span><span class="sxs-lookup"><span data-stu-id="2ba69-120">Paper sizes.</span></span>  
  
-   <span data-ttu-id="2ba69-121">Единицы измерения длины, веса, площади, объема и температуры.</span><span class="sxs-lookup"><span data-stu-id="2ba69-121">Units of measure used for lengths, weights, area, volume, and temperatures.</span></span> <span data-ttu-id="2ba69-122">Хотя в платформе .NET Framework нет встроенной поддержки преобразования единиц измерения, можно использовать свойство <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType>, чтобы определить, использует ли определенная страна или регион метрическую систему, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2ba69-122">Although the .NET Framework does not offer built-in support for converting between units of measure, you can use the <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> property to determine whether a particular country or region uses the metric system, as the following example illustrates.</span></span>  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a><span data-ttu-id="2ba69-123">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="2ba69-123">Testing your application</span></span>  
 <span data-ttu-id="2ba69-124">Перед локализацией приложения необходимо протестировать его с использованием данных на других языках в международных версиях операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2ba69-124">Before you localize your application, you should test it by using international data on international versions of the operating system.</span></span> <span data-ttu-id="2ba69-125">Хотя большая часть пользовательского интерфейса еще не локализована, можно будет обнаружить различные проблемы, например следующие.</span><span class="sxs-lookup"><span data-stu-id="2ba69-125">Although most of the user interface will not be localized at this point, you will be able to detect problems such as the following:</span></span>  
  
-   <span data-ttu-id="2ba69-126">Сериализованные данные, которые неправильно десериализуются в разных версиях операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2ba69-126">Serialized data that does not deserialize correctly across operating system versions.</span></span>  
  
-   <span data-ttu-id="2ba69-127">Числовые данные, которые не соответствуют правилам текущих языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="2ba69-127">Numeric data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="2ba69-128">Например, числа могут отображаться с неверными разделителями групп, десятичными разделителями или обозначениями денежных единиц.</span><span class="sxs-lookup"><span data-stu-id="2ba69-128">For example, numbers may be displayed with inaccurate group separators, decimal separators, or currency symbols.</span></span>  
  
-   <span data-ttu-id="2ba69-129">Сведения о дате и времени, которые не соответствуют правилам текущих языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="2ba69-129">Date and time data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="2ba69-130">Например, числа, представляющие месяц и день, могут следовать в неверном порядке, могут быть неправильными разделители компонентов даты или данные часового пояса.</span><span class="sxs-lookup"><span data-stu-id="2ba69-130">For example, numbers that represent the month and day may appear in the wrong order, date separators may be incorrect, or time zone information may be incorrect.</span></span>  
  
-   <span data-ttu-id="2ba69-131">Ресурсы, которые не удается найти, поскольку для приложения не заданы язык и региональные параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ba69-131">Resources that cannot be found because you have not identified a default culture for your application.</span></span>  
  
-   <span data-ttu-id="2ba69-132">Строки, которые отображаются в нестандартном порядке для определенных языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="2ba69-132">Strings that are displayed in an unusual order for the specific culture.</span></span>  
  
-   <span data-ttu-id="2ba69-133">Сравнения строк или сравнения на равенство, возвращающие непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="2ba69-133">String comparisons or comparisons for equality that return unexpected results.</span></span>  
  
 <span data-ttu-id="2ba69-134">Если при разработке приложения вы соблюдали все рекомендации по глобализации, правильно обрабатывали функции, чувствительные к языковым и региональным параметрам, выявляли и устраняли проблемы локализации на этапе тестирования, то теперь можете смело переходить к следующему шагу: [Локализация](../../../docs/standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="2ba69-134">If you've followed the globalization recommendations when developing your application, handled culture-sensitive features correctly, and identified and addressed the localization issues that arose during testing, you can proceed to the next step, [Localization](../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba69-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2ba69-135">See also</span></span>

- [<span data-ttu-id="2ba69-136">Глобализация и локализация</span><span class="sxs-lookup"><span data-stu-id="2ba69-136">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
- [<span data-ttu-id="2ba69-137">Локализация</span><span class="sxs-lookup"><span data-stu-id="2ba69-137">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
- [<span data-ttu-id="2ba69-138">Глобализация</span><span class="sxs-lookup"><span data-stu-id="2ba69-138">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
- [<span data-ttu-id="2ba69-139">Ресурсы в приложениях для настольных систем</span><span class="sxs-lookup"><span data-stu-id="2ba69-139">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
