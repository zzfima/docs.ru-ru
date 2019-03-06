---
title: Практическое руководство. Использование автоматической разметки для создания кнопки
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 2172aba80fe963be33036a7245f228e8d5bfedda
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370349"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="c81fd-102">Практическое руководство. Использование автоматической разметки для создания кнопки</span><span class="sxs-lookup"><span data-stu-id="c81fd-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="c81fd-103">В этом примере описывается, как использовать автоматическую разметку для создания кнопки в локализуемом приложении.</span><span class="sxs-lookup"><span data-stu-id="c81fd-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="c81fd-104">Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может занять много времени.</span><span class="sxs-lookup"><span data-stu-id="c81fd-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="c81fd-105">Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов.</span><span class="sxs-lookup"><span data-stu-id="c81fd-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="c81fd-106">В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился требовал коррекции.</span><span class="sxs-lookup"><span data-stu-id="c81fd-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="c81fd-107">Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разрабатывать элементы, сокращающие потребность в коррекции.</span><span class="sxs-lookup"><span data-stu-id="c81fd-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="c81fd-108">Подход к написанию приложений, в которых проще изменять размер и положение элементов, называется `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="c81fd-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
 <span data-ttu-id="c81fd-109">Следующие два [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры создания приложений, позволяющих создать экземпляр кнопки: один с англоязычным текстом и один с текстом на испанском языке.</span><span class="sxs-lookup"><span data-stu-id="c81fd-109">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="c81fd-110">Обратите внимание на то, что код является одинаковым, за исключением текста. Размер кнопки изменяется в соответствии с размером текста.</span><span class="sxs-lookup"><span data-stu-id="c81fd-110">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c81fd-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c81fd-111">Example</span></span>  
 [!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="c81fd-112">На приведенном ниже рисунке показан результат выполнения примеров кода.</span><span class="sxs-lookup"><span data-stu-id="c81fd-112">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="c81fd-113">![Та же кнопка с текстом на разных языках](./media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="c81fd-113">![The same button with text in different languages](./media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="c81fd-114">Кнопка с автоматически изменяемым размером</span><span class="sxs-lookup"><span data-stu-id="c81fd-114">Auto Resizable Button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81fd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c81fd-115">See also</span></span>
- [<span data-ttu-id="c81fd-116">Обзор использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="c81fd-116">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="c81fd-117">Использование сетки для автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="c81fd-117">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
