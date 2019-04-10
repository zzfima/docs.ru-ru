---
title: Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms, с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: a0f567befb1e0c323dd16fffedec279ff836cbf8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337959"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="f3953-102">Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms, с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="f3953-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="f3953-103">Элементы управления Windows Forms обычно отображается текст, связанный с их основной функцией элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f3953-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="f3953-104">Например <xref:System.Windows.Forms.Button> управления обычно отображается заголовок, указывающее, какое действие выполняется при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="f3953-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="f3953-105">С помощью свойства <xref:System.Windows.Forms.Control.Text%2A> можно задавать или получать текст для всех элементов управления.</span><span class="sxs-lookup"><span data-stu-id="f3953-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="f3953-106">Шрифт можно менять с помощью свойства <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3953-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="f3953-107">Для задания текста и шрифта с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="f3953-107">To set the text and font with the designer</span></span>  
  
1. <span data-ttu-id="f3953-108">В окне «Свойства» задайте <xref:System.Windows.Forms.Control.Text%2A> свойство элемента управления соответствующую строку.</span><span class="sxs-lookup"><span data-stu-id="f3953-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="f3953-109">Чтобы создать сочетание клавиш, поставьте амперсанд (&) перед буквой, которая будет использоваться сочетание клавиш.</span><span class="sxs-lookup"><span data-stu-id="f3953-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2. <span data-ttu-id="f3953-110">В окне «Свойства» нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.Control.Font%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f3953-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="f3953-111">В диалоговом окне стандартного шрифта выберите шрифт, стиль шрифта, размер, эффекты (например, зачеркивание или подчеркивание) и сценарий, которые должны.</span><span class="sxs-lookup"><span data-stu-id="f3953-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3953-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f3953-112">See also</span></span>

- [<span data-ttu-id="f3953-113">Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3953-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="f3953-114">Шрифты и текст</span><span class="sxs-lookup"><span data-stu-id="f3953-114">Using Fonts and Text</span></span>](../advanced/using-fonts-and-text.md)
- [<span data-ttu-id="f3953-115">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3953-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
