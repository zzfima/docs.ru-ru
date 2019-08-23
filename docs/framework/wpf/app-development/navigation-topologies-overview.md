---
title: Общие сведения о топологии переходов
ms.date: 03/30/2017
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
ms.openlocfilehash: b62432d64393f4fb749af2e25c42e2e0161de219
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950739"
---
# <a name="navigation-topologies-overview"></a><span data-ttu-id="8a53c-102">Общие сведения о топологии переходов</span><span class="sxs-lookup"><span data-stu-id="8a53c-102">Navigation Topologies Overview</span></span>
<a name="introduction"></a><span data-ttu-id="8a53c-103">В этом обзоре содержатся общие сведения о топологиях [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]навигации в.</span><span class="sxs-lookup"><span data-stu-id="8a53c-103">This overview provides an introduction to navigation topologies in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="8a53c-104">Последовательно рассматриваются три общие топологии навигации с примерами.</span><span class="sxs-lookup"><span data-stu-id="8a53c-104">Three common navigation topologies, with samples, are subsequently discussed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a53c-105">Прежде чем читать этот раздел, необходимо ознакомиться с понятием структурированной навигации в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] с помощью функций страницы.</span><span class="sxs-lookup"><span data-stu-id="8a53c-105">Before reading this topic, you should be familiar with the concept of structured navigation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] using page functions.</span></span> <span data-ttu-id="8a53c-106">Дополнительные сведения об этих разделах см. в разделе [Общие сведения о структурной навигации](structured-navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8a53c-106">For more information on both of these topics, see [Structured Navigation Overview](structured-navigation-overview.md).</span></span>  
  
 <span data-ttu-id="8a53c-107">В этом разделе содержатся следующие подразделы.</span><span class="sxs-lookup"><span data-stu-id="8a53c-107">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="8a53c-108">Топологии навигации</span><span class="sxs-lookup"><span data-stu-id="8a53c-108">Navigation Topologies</span></span>](#Navigation_Topologies)  
  
- [<span data-ttu-id="8a53c-109">Топологии структурной навигации</span><span class="sxs-lookup"><span data-stu-id="8a53c-109">Structured Navigation Topologies</span></span>](#Structured_Navigation_Topologies)  
  
- [<span data-ttu-id="8a53c-110">Навигация при фиксированной линейной топологии</span><span class="sxs-lookup"><span data-stu-id="8a53c-110">Navigation over a Fixed Linear Topology</span></span>](#Navigation_over_a_Fixed_Linear_Topology)  
  
- [<span data-ttu-id="8a53c-111">Динамическая навигация при фиксированной иерархической топологии</span><span class="sxs-lookup"><span data-stu-id="8a53c-111">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
- [<span data-ttu-id="8a53c-112">Навигация при динамически создаваемой топологии</span><span class="sxs-lookup"><span data-stu-id="8a53c-112">Navigation over a Dynamically Generated Topology</span></span>](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a><span data-ttu-id="8a53c-113">Топологии навигации</span><span class="sxs-lookup"><span data-stu-id="8a53c-113">Navigation Topologies</span></span>  
 <span data-ttu-id="8a53c-114">В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]переход, как правило, состоит из<xref:System.Windows.Controls.Page>страниц () с гиперссылками<xref:System.Windows.Documents.Hyperlink>(), которые переходить к другим страницам при щелчке.</span><span class="sxs-lookup"><span data-stu-id="8a53c-114">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], navigation typically consists of pages (<xref:System.Windows.Controls.Page>) with hyperlinks (<xref:System.Windows.Documents.Hyperlink>) that navigate to other pages when clicked.</span></span> <span data-ttu-id="8a53c-115">Страницы, к которым осуществляется переход, определяются [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] с помощью (см. раздел [Pack URI в WPF](pack-uris-in-wpf.md)).</span><span class="sxs-lookup"><span data-stu-id="8a53c-115">Pages that are navigated to are identified by [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (see [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span> <span data-ttu-id="8a53c-116">Рассмотрим следующий простой пример, в котором показаны страницы, гиперссылки и [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8a53c-116">Consider the following simple example that shows pages, hyperlinks, and [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:</span></span>  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 <span data-ttu-id="8a53c-117">Эти страницы упорядочены в *топологии навигации* , структура которой определяется тем, как можно перемещаться между страницами.</span><span class="sxs-lookup"><span data-stu-id="8a53c-117">These pages are arranged in a *navigation topology* whose structure is determined by how you can navigate between the pages.</span></span> <span data-ttu-id="8a53c-118">Эта конкретная топология навигации подходит для простых сценариев, хотя навигация может требовать более сложные топологии, некоторые из которых могут быть определены только при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="8a53c-118">This particular navigation topology is suitable in simple scenarios, although navigation can require more complex topologies, some of which can only be defined when an application is running.</span></span>  
  
 <span data-ttu-id="8a53c-119">В этом разделе рассматриваются три общие топологии навигации: *фиксированная линейная*, *фиксированная иерархическая*и *динамически создаваемая*.</span><span class="sxs-lookup"><span data-stu-id="8a53c-119">This topic covers three common navigation topologies: *fixed linear*, *fixed hierarchical*, and *dynamically generated*.</span></span> <span data-ttu-id="8a53c-120">Каждая топология навигации показана с примером, который имеет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] следующий пример, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="8a53c-120">Each navigation topology is demonstrated with a sample that has a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] like the one that is shown in the following figure:</span></span>  
  
 ![Страницы задач с элементами данных и кнопками навигации.](./media/navigation-topologies-overview/navigation-topology-data-items.png)  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a><span data-ttu-id="8a53c-122">Топологии структурной навигации</span><span class="sxs-lookup"><span data-stu-id="8a53c-122">Structured Navigation Topologies</span></span>  
 <span data-ttu-id="8a53c-123">Существует два широко известных типа топологии навигации.</span><span class="sxs-lookup"><span data-stu-id="8a53c-123">There are two broad types of navigation topologies:</span></span>  
  
- <span data-ttu-id="8a53c-124">**Фиксированная топология**: определяется во время компиляции и не изменяется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a53c-124">**Fixed Topology**: defined at compile time and does not change at run time.</span></span> <span data-ttu-id="8a53c-125">Фиксированные топологии полезны для перехода по фиксированной последовательности страниц в линейном или иерархическом порядке.</span><span class="sxs-lookup"><span data-stu-id="8a53c-125">Fixed topologies are useful for navigation through a fixed sequence of pages in either a linear or hierarchical order.</span></span>  
  
- <span data-ttu-id="8a53c-126">**Динамическая топология**: определяется во время выполнения на основе входных данных, собираемых от пользователей, приложений или системы.</span><span class="sxs-lookup"><span data-stu-id="8a53c-126">**Dynamic Topology**: defined at run time based on input that is collected from the user, the application, or the system.</span></span> <span data-ttu-id="8a53c-127">Динамические топологии полезны в тех случаях, когда на страницы можно переходить в разных последовательностях.</span><span class="sxs-lookup"><span data-stu-id="8a53c-127">Dynamic topologies are useful when pages can be navigated in different sequences.</span></span>  
  
 <span data-ttu-id="8a53c-128">Хотя возможно создание топологии навигации с помощью страниц, в примерах используются страничные функции, поскольку они предоставляют дополнительные возможности, которые упрощают поддержку передачи и возврата данных по страницам топологии.</span><span class="sxs-lookup"><span data-stu-id="8a53c-128">Although it is possible to create navigation topologies using pages, the samples use page functions because they provide additional support that simplifies support for passing and returning data through the pages of a topology.</span></span>  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a><span data-ttu-id="8a53c-129">Навигация при фиксированной линейной топологии</span><span class="sxs-lookup"><span data-stu-id="8a53c-129">Navigation over a Fixed Linear Topology</span></span>  
 <span data-ttu-id="8a53c-130">Фиксированная линейная топология является аналогом структуры мастера с одной или несколькими страницами, по которым можно переходить в фиксированной последовательности.</span><span class="sxs-lookup"><span data-stu-id="8a53c-130">A fixed linear topology is analogous to the structure of a wizard that has one or more wizard pages that are navigated in a fixed sequence.</span></span> <span data-ttu-id="8a53c-131">На следующем рисунке показана высокоуровневая структура и поток мастера с фиксированной линейной топологией.</span><span class="sxs-lookup"><span data-stu-id="8a53c-131">The following figure shows the high-level structure and flow of a wizard with a fixed linear topology:</span></span>  
  
 ![Схема, на которой показана фиксированная линейная топология.](./media/navigation-topologies-overview/navigation-topology-fixed-linear.png)  
  
 <span data-ttu-id="8a53c-133">Типичные варианты поведения для навигации по фиксированной линейной топологии могут быть следующие.</span><span class="sxs-lookup"><span data-stu-id="8a53c-133">The typical behaviors for navigating over a fixed linear topology include the following:</span></span>  
  
- <span data-ttu-id="8a53c-134">Переход из вызывающей страницы на страницу средства запуска, которое инициализирует мастер и переходит к первой странице мастера.</span><span class="sxs-lookup"><span data-stu-id="8a53c-134">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="8a53c-135">Страница запуска ( [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]не меньше <xref:System.Windows.Navigation.PageFunction%601>) не требуется, так как вызывающая страница может напрямую вызывать первую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="8a53c-135">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="8a53c-136">Однако используя страницу средства запуска, можно упростить инициализацию мастера, особенно если инициализация сложна.</span><span class="sxs-lookup"><span data-stu-id="8a53c-136">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="8a53c-137">Пользователи могут переходить между страницами с помощью кнопок "Назад" и "Вперед" (или гиперссылок).</span><span class="sxs-lookup"><span data-stu-id="8a53c-137">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="8a53c-138">Пользователи могут переходить по страницам с помощью журнала.</span><span class="sxs-lookup"><span data-stu-id="8a53c-138">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="8a53c-139">Пользователи могут отменить работу мастера на любой странице, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="8a53c-139">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="8a53c-140">Пользователи могут принять работу мастера на последней странице, нажав кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="8a53c-140">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="8a53c-141">Если мастер отменяется, то он возвращает соответствующий результат и не возвращает никаких данных.</span><span class="sxs-lookup"><span data-stu-id="8a53c-141">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="8a53c-142">Если пользователь принимает работу мастера, мастер возвращает соответствующий результат и возвращает собранные им данные.</span><span class="sxs-lookup"><span data-stu-id="8a53c-142">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="8a53c-143">По завершении мастера (принятия или отмены) страницы, которые составляли мастер, будут удалены из журнала.</span><span class="sxs-lookup"><span data-stu-id="8a53c-143">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="8a53c-144">Это сохраняет каждый экземпляр мастера изолированным, тем самым позволяя избежать потенциальных ошибок данных или состояния.</span><span class="sxs-lookup"><span data-stu-id="8a53c-144">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a><span data-ttu-id="8a53c-145">Динамическая навигация при фиксированной иерархической топологии</span><span class="sxs-lookup"><span data-stu-id="8a53c-145">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>  
 <span data-ttu-id="8a53c-146">В некоторых приложениях страницы позволяют переходить на две или более страницы, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="8a53c-146">In some applications, pages allow navigation to two or more other pages, as shown in the following figure:</span></span> 
  
 ![Схема, на которой показана страница, которая может переходить на несколько страниц.](./media/navigation-topologies-overview/navigation-topology-multiple-pages.png)  
  
 <span data-ttu-id="8a53c-148">Эта структура называется фиксированной иерархической топологией, и последовательность обхода иерархии часто определяется во время выполнения приложением или пользователем.</span><span class="sxs-lookup"><span data-stu-id="8a53c-148">This structure is known as a fixed hierarchical topology, and the sequence in which the hierarchy is traversed is often determined at run time by either the application or the user.</span></span> <span data-ttu-id="8a53c-149">Во время выполнения каждая страница в иерархии, позволяющая выполнять переходы на несколько страниц, собирает данные, необходимые для определения страниц для перехода.</span><span class="sxs-lookup"><span data-stu-id="8a53c-149">At run time, each page in the hierarchy that allows navigation to two or more other pages gathers the data required to determine which page to navigate to.</span></span> <span data-ttu-id="8a53c-150">На следующем рисунке показана одна из нескольких возможных последовательностей навигации на предыдущем рисунке.</span><span class="sxs-lookup"><span data-stu-id="8a53c-150">The following figure illustrates one of several possible navigation sequences based on the previous figure:</span></span>  
  
 ![Схема, на которой показана возможная последовательность навигации.](./media/navigation-topologies-overview/navigation-topology-fixed-hierarchical.png)  
  
 <span data-ttu-id="8a53c-152">Несмотря на то, что последовательность переходов по страницам в фиксированной иерархической структуре определяется во время выполнения, взаимодействие с пользователем такое же, как в фиксированной линейной топологии.</span><span class="sxs-lookup"><span data-stu-id="8a53c-152">Even though the sequence in which pages in a fixed hierarchical structure are navigated is determined at run time, the user experience is the same as the user experience for a fixed linear topology:</span></span>  
  
- <span data-ttu-id="8a53c-153">Переход из вызывающей страницы на страницу средства запуска, которое инициализирует мастер и переходит к первой странице мастера.</span><span class="sxs-lookup"><span data-stu-id="8a53c-153">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="8a53c-154">Страница запуска ( [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]не меньше <xref:System.Windows.Navigation.PageFunction%601>) не требуется, так как вызывающая страница может напрямую вызывать первую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="8a53c-154">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="8a53c-155">Однако используя страницу средства запуска, можно упростить инициализацию мастера, особенно если инициализация сложна.</span><span class="sxs-lookup"><span data-stu-id="8a53c-155">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="8a53c-156">Пользователи могут переходить между страницами с помощью кнопок "Назад" и "Вперед" (или гиперссылок).</span><span class="sxs-lookup"><span data-stu-id="8a53c-156">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="8a53c-157">Пользователи могут переходить по страницам с помощью журнала.</span><span class="sxs-lookup"><span data-stu-id="8a53c-157">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="8a53c-158">Пользователи могут изменять последовательность навигации, если они перемещаются назад по журналу.</span><span class="sxs-lookup"><span data-stu-id="8a53c-158">Users can change the navigation sequence if they navigate back through the journal.</span></span>  
  
- <span data-ttu-id="8a53c-159">Пользователи могут отменить работу мастера на любой странице, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="8a53c-159">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="8a53c-160">Пользователи могут принять работу мастера на последней странице, нажав кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="8a53c-160">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="8a53c-161">Если мастер отменяется, то он возвращает соответствующий результат и не возвращает никаких данных.</span><span class="sxs-lookup"><span data-stu-id="8a53c-161">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="8a53c-162">Если пользователь принимает работу мастера, мастер возвращает соответствующий результат и возвращает собранные им данные.</span><span class="sxs-lookup"><span data-stu-id="8a53c-162">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="8a53c-163">По завершении мастера (принятия или отмены) страницы, которые составляли мастер, будут удалены из журнала.</span><span class="sxs-lookup"><span data-stu-id="8a53c-163">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="8a53c-164">Это сохраняет каждый экземпляр мастера изолированным, тем самым позволяя избежать потенциальных ошибок данных или состояния.</span><span class="sxs-lookup"><span data-stu-id="8a53c-164">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a><span data-ttu-id="8a53c-165">Навигация при динамически создаваемой топологии</span><span class="sxs-lookup"><span data-stu-id="8a53c-165">Navigation over a Dynamically Generated Topology</span></span>  
 <span data-ttu-id="8a53c-166">В некоторых приложениях последовательность, в которой осуществляется переход на две или более страниц, может быть определена только во время выполнения пользователем, приложением или внешними данными.</span><span class="sxs-lookup"><span data-stu-id="8a53c-166">In some applications, the sequence in which two or more pages are navigated can only be determined at run time, whether by the user, the application, or external data.</span></span> <span data-ttu-id="8a53c-167">На следующем рисунке показан набор страниц с неопределенной последовательностью навигации:</span><span class="sxs-lookup"><span data-stu-id="8a53c-167">The following figure illustrates a set of pages with an undetermined navigation sequence:</span></span>  
  
 ![Набор страниц с неопределенной последовательностью навигации.](./media/navigation-topologies-overview/navigation-topology-dynamically-generated.png)  
  
 <span data-ttu-id="8a53c-169">На следующем рисунке показана последовательность переходов, которая была выбрана пользователем во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="8a53c-169">The next figure illustrates a navigation sequence that was chosen by the user at run time:</span></span>  
  
 ![Схема, на которой показана последовательность навигации, выбранная во время выполнения.](./media/navigation-topologies-overview/navigation-topology-sequence-chosen-run-time.png)  
  
 <span data-ttu-id="8a53c-171">Эта последовательность навигации называется динамически создаваемой топологией.</span><span class="sxs-lookup"><span data-stu-id="8a53c-171">The navigation sequence is known as a dynamically generated topology.</span></span> <span data-ttu-id="8a53c-172">Взаимодействие с пользователем такое же, как и в предыдущих топологиях навигации.</span><span class="sxs-lookup"><span data-stu-id="8a53c-172">For the user, as with the other navigation topologies, the user experience is the same as it is for the previous topologies:</span></span>  
  
- <span data-ttu-id="8a53c-173">Переход из вызывающей страницы на страницу средства запуска, которое инициализирует мастер и переходит к первой странице мастера.</span><span class="sxs-lookup"><span data-stu-id="8a53c-173">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="8a53c-174">Страница запуска ( [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]не меньше <xref:System.Windows.Navigation.PageFunction%601>) не требуется, так как вызывающая страница может напрямую вызывать первую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="8a53c-174">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="8a53c-175">Однако используя страницу средства запуска, можно упростить инициализацию мастера, особенно если инициализация сложна.</span><span class="sxs-lookup"><span data-stu-id="8a53c-175">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="8a53c-176">Пользователи могут переходить между страницами с помощью кнопок "Назад" и "Вперед" (или гиперссылок).</span><span class="sxs-lookup"><span data-stu-id="8a53c-176">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="8a53c-177">Пользователи могут переходить по страницам с помощью журнала.</span><span class="sxs-lookup"><span data-stu-id="8a53c-177">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="8a53c-178">Пользователи могут отменить работу мастера на любой странице, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="8a53c-178">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="8a53c-179">Пользователи могут принять работу мастера на последней странице, нажав кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="8a53c-179">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="8a53c-180">Если мастер отменяется, то он возвращает соответствующий результат и не возвращает никаких данных.</span><span class="sxs-lookup"><span data-stu-id="8a53c-180">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="8a53c-181">Если пользователь принимает работу мастера, мастер возвращает соответствующий результат и возвращает собранные им данные.</span><span class="sxs-lookup"><span data-stu-id="8a53c-181">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="8a53c-182">По завершении мастера (принятия или отмены) страницы, которые составляли мастер, будут удалены из журнала.</span><span class="sxs-lookup"><span data-stu-id="8a53c-182">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="8a53c-183">Это сохраняет каждый экземпляр мастера изолированным, тем самым позволяя избежать потенциальных ошибок данных или состояния.</span><span class="sxs-lookup"><span data-stu-id="8a53c-183">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a53c-184">См. также</span><span class="sxs-lookup"><span data-stu-id="8a53c-184">See also</span></span>

- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [<span data-ttu-id="8a53c-185">Общие сведения о структурной навигации</span><span class="sxs-lookup"><span data-stu-id="8a53c-185">Structured Navigation Overview</span></span>](structured-navigation-overview.md)
