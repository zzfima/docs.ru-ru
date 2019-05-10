---
title: Практическое руководство. Отображение всплывающей справки
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: bf3bcbff0cd6f3bbf71e96e748cb170d5ce68dfc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211402"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="f2a8c-102">Практическое руководство. Отображение всплывающей справки</span><span class="sxs-lookup"><span data-stu-id="f2a8c-102">How to: Display pop-up Help</span></span>

<span data-ttu-id="f2a8c-103">Один из способов отображения справки в Windows Forms — через **помочь** кнопки, расположенной в правой части строки заголовка, доступной через <xref:System.Windows.Forms.Form.HelpButton%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="f2a8c-104">Этот способ вывода справки хорошо подходит при работе с диалоговыми окнами.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="f2a8c-105">Модальные диалоговые окна (с методом <xref:System.Windows.Forms.Form.ShowDialog%2A>) затрудняют работу внешних справочных систем, так как их нужно закрывать, чтобы перенести фокус на другое окно.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="f2a8c-106">Кроме того, с помощью **помочь** кнопку требует отсутствия не **свернуть** кнопку или **развернуть** кнопки в строке заголовка.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="f2a8c-107">Это стандартное соглашение стандартным диалоговым окном, формах обычно есть **свернуть** и **развернуть** кнопки.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>

<span data-ttu-id="f2a8c-108">Можно также использовать <xref:System.Windows.Forms.HelpProvider> компонента, чтобы связать элементы управления с файлами справочной системы, даже если применяется всплывающая справка.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-108">You can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="f2a8c-109">Дополнительные сведения см. в разделе [предоставление справки в приложении Windows](how-to-provide-help-in-a-windows-application.md).</span><span class="sxs-lookup"><span data-stu-id="f2a8c-109">For more information, see [Providing Help in a Windows Application](how-to-provide-help-in-a-windows-application.md).</span></span>

## <a name="display-pop-up-help"></a><span data-ttu-id="f2a8c-110">Отображение всплывающей справки</span><span class="sxs-lookup"><span data-stu-id="f2a8c-110">Display pop-up Help</span></span>

1. <span data-ttu-id="f2a8c-111">В Visual Studio перетащите [HelpProvider](../controls/helpprovider-component-windows-forms.md) компонент из области элементов в форму.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-111">In Visual Studio, drag a [HelpProvider](../controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>

   <span data-ttu-id="f2a8c-112">Он разместится в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-112">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="f2a8c-113">В окне "Свойства" присвойте свойству <xref:System.Windows.Forms.Form.HelpButton%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-113">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="f2a8c-114">При этом в правой части строки заголовка формы появится кнопка с вопросительным знаком.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-114">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>

3. <span data-ttu-id="f2a8c-115">Для отображения <xref:System.Windows.Forms.Form.HelpButton%2A> свойствам <xref:System.Windows.Forms.Form.MinimizeBox%2A> и <xref:System.Windows.Forms.Form.MaximizeBox%2A> формы нужно присвоить значение `false`, свойству <xref:System.Windows.Forms.Form.ControlBox%2A> — значение `true`, а свойству <xref:System.Windows.Forms.Form.FormBorderStyle%2A> — одно из следующих значений: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> или <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-115">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>

4. <span data-ttu-id="f2a8c-116">Выберите элемент управления, для которого нужно отображать справку в форме, и укажите строку справки в окне "Свойства".</span><span class="sxs-lookup"><span data-stu-id="f2a8c-116">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="f2a8c-117">Это строка текста, который будет отображаться в окне, аналогичном окну [подсказки](../controls/tooltip-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f2a8c-117">This is the string of text that will be displayed in a window similar to a [ToolTip](../controls/tooltip-component-windows-forms.md).</span></span>

5. <span data-ttu-id="f2a8c-118">Нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-118">Press **F5**.</span></span>

6. <span data-ttu-id="f2a8c-119">Нажмите клавишу **помочь** в строке заголовка кнопку и щелкните элемент управления, для которого была задана строка справки.</span><span class="sxs-lookup"><span data-stu-id="f2a8c-119">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2a8c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f2a8c-120">See also</span></span>

- [<span data-ttu-id="f2a8c-121">Отображение справки по элементам управления с помощью подсказок</span><span class="sxs-lookup"><span data-stu-id="f2a8c-121">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="f2a8c-122">Интеграция справки пользователя в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2a8c-122">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="f2a8c-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2a8c-123">Windows Forms</span></span>](../index.md)
