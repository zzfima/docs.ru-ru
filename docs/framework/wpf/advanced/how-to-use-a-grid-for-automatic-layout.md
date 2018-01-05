---
title: "Практическое руководство. Использование сетки для автоматической разметки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbd8bd7e36b7b773837b839e77ec88a8e7c8f0d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="88027-102">Практическое руководство. Использование сетки для автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="88027-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="88027-103">В этот примере описаны способы использования сетки для автоматической разметки с целью создания локализуемого приложения.</span><span class="sxs-lookup"><span data-stu-id="88027-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="88027-104">Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может быть много времени.</span><span class="sxs-lookup"><span data-stu-id="88027-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="88027-105">Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов.</span><span class="sxs-lookup"><span data-stu-id="88027-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="88027-106">В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился необходимые корректировки.</span><span class="sxs-lookup"><span data-stu-id="88027-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="88027-107">Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разработать элементы, которые снижают потребность в коррекции.</span><span class="sxs-lookup"><span data-stu-id="88027-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="88027-108">Подход к написанию приложений, которые могут быть легко изменять размер и положение называется `auto layout`.</span><span class="sxs-lookup"><span data-stu-id="88027-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="88027-109">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере демонстрируется использование сетки для размещения нескольких кнопок и текста.</span><span class="sxs-lookup"><span data-stu-id="88027-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="88027-110">Обратите внимание, что высоты и ширины ячейки установлено значение `Auto`; поэтому ячейку, содержащую кнопку с изображением изменяется, чтобы вместить изображение.</span><span class="sxs-lookup"><span data-stu-id="88027-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="88027-111">Поскольку <xref:System.Windows.Controls.Grid> элемент можно скорректировать, чтобы его содержимое может быть полезно при использовании подхода автоматический макет для разработки приложений, которые могут быть локализованы.</span><span class="sxs-lookup"><span data-stu-id="88027-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88027-112">Пример</span><span class="sxs-lookup"><span data-stu-id="88027-112">Example</span></span>  
 <span data-ttu-id="88027-113">В приведенном ниже примере показано использование сетки.</span><span class="sxs-lookup"><span data-stu-id="88027-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="88027-114">На приведенном ниже рисунке показан результат выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="88027-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="88027-115">![Пример сетки](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="88027-115">![Grid example](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="88027-116">Grid</span><span class="sxs-lookup"><span data-stu-id="88027-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88027-117">См. также</span><span class="sxs-lookup"><span data-stu-id="88027-117">See Also</span></span>  
 [<span data-ttu-id="88027-118">Обзор использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="88027-118">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="88027-119">Использование автоматической разметки для создания кнопки</span><span class="sxs-lookup"><span data-stu-id="88027-119">Use Automatic Layout to Create a Button</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
