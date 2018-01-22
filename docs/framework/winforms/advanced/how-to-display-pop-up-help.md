---
title: "Практическое руководство. Отображение всплывающей справки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ec4401bb3465f72e4ef732e7554dc64603d700c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="d04f2-102">Практическое руководство. Отображение всплывающей справки</span><span class="sxs-lookup"><span data-stu-id="d04f2-102">How to: Display Pop-up Help</span></span>
<span data-ttu-id="d04f2-103">Является одним из способов отображения справки в Windows Forms через **справки** кнопку, расположенную справа от строки заголовка, доступной через <xref:System.Windows.Forms.Form.HelpButton%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d04f2-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="d04f2-104">Этот способ вывода справки хорошо подходит при работе с диалоговыми окнами.</span><span class="sxs-lookup"><span data-stu-id="d04f2-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="d04f2-105">Модальные диалоговые окна (с методом <xref:System.Windows.Forms.Form.ShowDialog%2A>) затрудняют работу внешних справочных систем, так как их нужно закрывать, чтобы перенести фокус на другое окно.</span><span class="sxs-lookup"><span data-stu-id="d04f2-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="d04f2-106">Кроме того, с помощью **справки** кнопки необходимо наличие не **свернуть** кнопку или **развернуть** кнопка отображается в строке заголовка.</span><span class="sxs-lookup"><span data-stu-id="d04f2-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="d04f2-107">Это стандартное диалоговое традиции формах обычно есть **свернуть** и **развернуть** кнопки.</span><span class="sxs-lookup"><span data-stu-id="d04f2-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>  
  
 <span data-ttu-id="d04f2-108">Следует помнить, что компонент <xref:System.Windows.Forms.HelpProvider> можно также использовать, чтобы связать элементы управления с файлами справочной системы, даже если применяется всплывающая справка.</span><span class="sxs-lookup"><span data-stu-id="d04f2-108">Be aware that you can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="d04f2-109">Дополнительные сведения см. в разделе [предоставление справки в приложении Windows](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).</span><span class="sxs-lookup"><span data-stu-id="d04f2-109">For more information, see [Providing Help in a Windows Application](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d04f2-110">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="d04f2-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d04f2-111">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="d04f2-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d04f2-112">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="d04f2-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-pop-up-help"></a><span data-ttu-id="d04f2-113">Отображение всплывающей справки</span><span class="sxs-lookup"><span data-stu-id="d04f2-113">To display pop-up Help</span></span>  
  
1.  <span data-ttu-id="d04f2-114">Перетащите [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) компонента из области элементов в форму.</span><span class="sxs-lookup"><span data-stu-id="d04f2-114">Drag a [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>  
  
     <span data-ttu-id="d04f2-115">Он разместится в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d04f2-115">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="d04f2-116">В окне "Свойства" присвойте свойству <xref:System.Windows.Forms.Form.HelpButton%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d04f2-116">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="d04f2-117">При этом в правой части строки заголовка формы появится кнопка с вопросительным знаком.</span><span class="sxs-lookup"><span data-stu-id="d04f2-117">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>  
  
3.  <span data-ttu-id="d04f2-118">Для отображения <xref:System.Windows.Forms.Form.HelpButton%2A> свойствам <xref:System.Windows.Forms.Form.MinimizeBox%2A> и <xref:System.Windows.Forms.Form.MaximizeBox%2A> формы нужно присвоить значение `false`, свойству <xref:System.Windows.Forms.Form.ControlBox%2A> — значение `true`, а свойству <xref:System.Windows.Forms.Form.FormBorderStyle%2A> — одно из следующих значений: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> или <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span><span class="sxs-lookup"><span data-stu-id="d04f2-118">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>  
  
4.  <span data-ttu-id="d04f2-119">Выберите элемент управления, для которого нужно отображать справку в форме, и укажите строку справки в окне "Свойства".</span><span class="sxs-lookup"><span data-stu-id="d04f2-119">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="d04f2-120">Это строка текста, который будет отображаться в окне, аналогичном окну [подсказка](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d04f2-120">This is the string of text that will be displayed in a window similar to a [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).</span></span>  
  
5.  <span data-ttu-id="d04f2-121">Нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="d04f2-121">Press **F5**.</span></span>  
  
6.  <span data-ttu-id="d04f2-122">Нажмите клавишу **справки** кнопку в строке заголовка и щелкните элемент управления, для которого была задана строка справки.</span><span class="sxs-lookup"><span data-stu-id="d04f2-122">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d04f2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d04f2-123">See Also</span></span>  
 [<span data-ttu-id="d04f2-124">Отображение справки по элементам управления с помощью подсказок</span><span class="sxs-lookup"><span data-stu-id="d04f2-124">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [<span data-ttu-id="d04f2-125">Интеграция справки пользователя в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d04f2-125">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="d04f2-126">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d04f2-126">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
