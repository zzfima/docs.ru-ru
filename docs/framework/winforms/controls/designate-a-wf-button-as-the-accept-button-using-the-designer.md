---
title: Как выполнить Создание кнопки принятия в конструкторе Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 477094b88c99bbe9193a6eaedb5c16d0c0e679d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709550"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="4cac0-102">Как выполнить Создание кнопки принятия в конструкторе Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cac0-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="4cac0-103">В любой форме Windows, можно назначить <xref:System.Windows.Forms.Button> отображения элемента управления "Принять", также известный как кнопка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4cac0-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="4cac0-104">Каждый раз, когда пользователь нажимает клавишу ВВОД, нажатии кнопки по умолчанию, независимо от того, что другой элемент управления в форме имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="4cac0-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="4cac0-105">Исключение составляют случаи, когда элемент управления с фокусом является еще одну кнопку — в этом случае будет нажата кнопка с фокусом, или многострочного текстового окна, или пользовательский элемент управления, который перехватывает клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="4cac0-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cac0-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="4cac0-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4cac0-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="4cac0-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4cac0-108">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="4cac0-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="4cac0-109">Чтобы создать кнопку «принять»</span><span class="sxs-lookup"><span data-stu-id="4cac0-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="4cac0-110">Выберите форму, в которой находится кнопка.</span><span class="sxs-lookup"><span data-stu-id="4cac0-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="4cac0-111">В **свойства** формы задайте окне <xref:System.Windows.Forms.Form.AcceptButton%2A> свойства <xref:System.Windows.Forms.Button> имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4cac0-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cac0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4cac0-112">See also</span></span>
- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="4cac0-113">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="4cac0-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [<span data-ttu-id="4cac0-114">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cac0-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="4cac0-115">Практическое руководство. Ответ на нажатие кнопки Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cac0-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="4cac0-116">Практическое руководство. Создание кнопки отмены, с помощью конструктора Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cac0-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="4cac0-117">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="4cac0-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
