---
title: Практическое руководство. Использование автоматического макета для создания кнопки
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 8eb1e93dd87c210812c9b7758c744a616ef2d862
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052395"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="9861b-102">Практическое руководство. Использование автоматического макета для создания кнопки</span><span class="sxs-lookup"><span data-stu-id="9861b-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="9861b-103">В этом примере описывается, как использовать автоматическую разметку для создания кнопки в локализуемом приложении.</span><span class="sxs-lookup"><span data-stu-id="9861b-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="9861b-104">Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может занять много времени.</span><span class="sxs-lookup"><span data-stu-id="9861b-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="9861b-105">Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов.</span><span class="sxs-lookup"><span data-stu-id="9861b-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="9861b-106">В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился требовал коррекции.</span><span class="sxs-lookup"><span data-stu-id="9861b-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="9861b-107">Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разрабатывать элементы, сокращающие потребность в коррекции.</span><span class="sxs-lookup"><span data-stu-id="9861b-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="9861b-108">Подход к написанию приложений, в которых проще изменять размер и положение элементов, называется `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="9861b-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9861b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="9861b-109">Example</span></span>  

<span data-ttu-id="9861b-110">Следующие два [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры создания приложений, позволяющих создать экземпляр кнопки: один с англоязычным текстом и один с текстом на испанском языке.</span><span class="sxs-lookup"><span data-stu-id="9861b-110">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="9861b-111">Обратите внимание на то, что код является одинаковым, за исключением текста. Размер кнопки изменяется в соответствии с размером текста.</span><span class="sxs-lookup"><span data-stu-id="9861b-111">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="9861b-112">На следующем рисунке показан выходные данные примеры кода с изменяемыми размерами автоматически кнопками:</span><span class="sxs-lookup"><span data-stu-id="9861b-112">The following graphic shows the output of the code samples with auto-resizable buttons:</span></span>
  
 ![Та же кнопка с текстовой подписью на различных языках](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a><span data-ttu-id="9861b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9861b-114">See also</span></span>

- [<span data-ttu-id="9861b-115">Обзор использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="9861b-115">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="9861b-116">Использование сетки для автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="9861b-116">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
