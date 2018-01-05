---
title: "Практическое руководство. Использование автоматической разметки для создания кнопки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c642e6491722e9bfe35337d066e3870f5a70f38c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="a8324-102">Практическое руководство. Использование автоматической разметки для создания кнопки</span><span class="sxs-lookup"><span data-stu-id="a8324-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="a8324-103">В этом примере описывается, как использовать автоматическую разметку для создания кнопки в локализуемом приложении.</span><span class="sxs-lookup"><span data-stu-id="a8324-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="a8324-104">Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может быть много времени.</span><span class="sxs-lookup"><span data-stu-id="a8324-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="a8324-105">Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов.</span><span class="sxs-lookup"><span data-stu-id="a8324-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="a8324-106">В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился необходимые корректировки.</span><span class="sxs-lookup"><span data-stu-id="a8324-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="a8324-107">Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разработать элементы, которые снижают потребность в коррекции.</span><span class="sxs-lookup"><span data-stu-id="a8324-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="a8324-108">Подход к написанию приложений, которые могут быть легко изменять размер и положение называется `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="a8324-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
 <span data-ttu-id="a8324-109">Ниже приведены два [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры создания приложений, позволяющих создать экземпляр кнопки; с англоязычным текстом и полноразмерных испанский текст.</span><span class="sxs-lookup"><span data-stu-id="a8324-109">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="a8324-110">Обратите внимание на то, что код является одинаковым, за исключением текста. Размер кнопки изменяется в соответствии с размером текста.</span><span class="sxs-lookup"><span data-stu-id="a8324-110">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8324-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a8324-111">Example</span></span>  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="a8324-112">На приведенном ниже рисунке показан результат выполнения примеров кода.</span><span class="sxs-lookup"><span data-stu-id="a8324-112">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="a8324-113">![Та же кнопка с текстовой подписью на различных языках](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="a8324-113">![The same button with text in different languages](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="a8324-114">Кнопка с автоматически изменяемым размером</span><span class="sxs-lookup"><span data-stu-id="a8324-114">Auto Resizable Button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8324-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a8324-115">See Also</span></span>  
 [<span data-ttu-id="a8324-116">Обзор использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="a8324-116">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="a8324-117">Использование сетки для автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="a8324-117">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
