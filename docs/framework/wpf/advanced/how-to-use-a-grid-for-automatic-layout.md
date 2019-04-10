---
title: Практическое руководство. Использование сетки для автоматического макета
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 590ad7292fea572b20ccaa09ce2886724e004a6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227136"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="cdc4e-102">Практическое руководство. Использование сетки для автоматического макета</span><span class="sxs-lookup"><span data-stu-id="cdc4e-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="cdc4e-103">В этот примере описаны способы использования сетки для автоматической разметки с целью создания локализуемого приложения.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="cdc4e-104">Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может занять много времени.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="cdc4e-105">Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="cdc4e-106">В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился требовал коррекции.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="cdc4e-107">Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разрабатывать элементы, сокращающие потребность в коррекции.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="cdc4e-108">Подход к написанию приложений, в которых проще изменять размер и положение элементов, называется `auto layout`.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="cdc4e-109">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере демонстрируется использование сетки для размещения нескольких кнопок и текста.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="cdc4e-110">Обратите внимание на то, что высоты и ширины ячейки установлено значение `Auto`; поэтому ячейку, которая содержит кнопку с изображением, изменяется в соответствии изображение.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="cdc4e-111">Так как <xref:System.Windows.Controls.Grid> элемента можно настроить на его содержимое, бывает полезно при использовании автоматической разметки для разработки приложений, которые могут быть локализованы.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdc4e-112">Пример</span><span class="sxs-lookup"><span data-stu-id="cdc4e-112">Example</span></span>  
 <span data-ttu-id="cdc4e-113">В приведенном ниже примере показано использование сетки.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="cdc4e-114">На приведенном ниже рисунке показан результат выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="cdc4e-115">![Пример сетки](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="cdc4e-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="cdc4e-116">Grid</span><span class="sxs-lookup"><span data-stu-id="cdc4e-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc4e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cdc4e-117">See also</span></span>

- [<span data-ttu-id="cdc4e-118">Обзор использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="cdc4e-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="cdc4e-119">Использование автоматического макета для создания кнопки</span><span class="sxs-lookup"><span data-stu-id="cdc4e-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
