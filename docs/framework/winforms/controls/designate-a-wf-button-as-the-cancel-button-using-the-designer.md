---
title: Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: cc352f15fb1e8b531cd0f9b298b2db4ce649d3cf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039650"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="d4876-102">Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d4876-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="d4876-103">В любой форме Windows Forms можно назначить <xref:System.Windows.Forms.Button> элемент управления кнопкой Отмена.</span><span class="sxs-lookup"><span data-stu-id="d4876-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="d4876-104">Нажатие кнопки «отмена» происходит каждый раз, когда пользователь нажимает клавишу ESC, независимо от того, какой элемент управления формы имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d4876-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="d4876-105">Такая кнопка обычно запрограммирована, позволяя пользователю быстро выйти из операции без фиксации каких-либо действий.</span><span class="sxs-lookup"><span data-stu-id="d4876-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>

## <a name="to-designate-the-cancel-button"></a><span data-ttu-id="d4876-106">Назначение кнопки «Отмена»</span><span class="sxs-lookup"><span data-stu-id="d4876-106">To designate the cancel button</span></span>

1. <span data-ttu-id="d4876-107">Выберите форму, в которой находится кнопка.</span><span class="sxs-lookup"><span data-stu-id="d4876-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="d4876-108">В окне **Свойства** задайте для <xref:System.Windows.Forms.Form.CancelButton%2A> <xref:System.Windows.Forms.Button> свойства формы имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d4876-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4876-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d4876-109">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="d4876-110">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="d4876-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="d4876-111">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4876-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="d4876-112">Практическое руководство. Реакция на нажатие кнопки Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4876-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="d4876-113">Практическое руководство. Назначение кнопки Windows Forms в качестве кнопки Accept с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d4876-113">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="d4876-114">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="d4876-114">Button Control</span></span>](button-control-windows-forms.md)
