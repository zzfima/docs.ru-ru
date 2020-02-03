---
title: Назначение кнопки "принять" с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746063"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="d10a5-102">Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d10a5-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="d10a5-103">В любой форме Windows Forms можно назначить элемент управления <xref:System.Windows.Forms.Button>, который будет кнопкой принять, также известный как кнопка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d10a5-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="d10a5-104">Когда пользователь нажимает клавишу ВВОД, нажата кнопка по умолчанию независимо от того, какой элемент управления формы имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d10a5-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="d10a5-105">Исключением является то, что элемент управления с фокусом — это еще одна кнопка — в этом случае будет нажата кнопка с фокусом или многострочное текстовое поле или пользовательский элемент управления, который захватывает клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="d10a5-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>

## <a name="to-designate-the-accept-button"></a><span data-ttu-id="d10a5-106">Назначение кнопки «принять»</span><span class="sxs-lookup"><span data-stu-id="d10a5-106">To designate the accept button</span></span>

1. <span data-ttu-id="d10a5-107">Выберите форму, в которой находится кнопка.</span><span class="sxs-lookup"><span data-stu-id="d10a5-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="d10a5-108">В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.Form.AcceptButton%2A> формы имя элемента управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="d10a5-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="d10a5-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d10a5-109">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="d10a5-110">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="d10a5-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="d10a5-111">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d10a5-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="d10a5-112">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d10a5-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="d10a5-113">Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d10a5-113">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="d10a5-114">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="d10a5-114">Button Control</span></span>](button-control-windows-forms.md)
