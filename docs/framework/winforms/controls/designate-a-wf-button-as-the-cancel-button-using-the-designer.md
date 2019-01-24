---
title: Как выполнить Создание кнопки отмены, с помощью конструктора Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 9d11528d7d7fed13f531faeb09f38c4564f970be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520481"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="c8b03-102">Как выполнить Создание кнопки отмены, с помощью конструктора Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8b03-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="c8b03-103">В любой форме Windows, можно назначить <xref:System.Windows.Forms.Button> отображения элемента управления кнопки "Отмена".</span><span class="sxs-lookup"><span data-stu-id="c8b03-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="c8b03-104">Каждый раз, когда пользователь нажимает клавишу ESC, независимо от того, что другой элемент управления в форме имеет фокус, нажатии кнопки "Отмена".</span><span class="sxs-lookup"><span data-stu-id="c8b03-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="c8b03-105">Такая кнопка обычно создается, чтобы пользователи могли быстро прервать операцию, не выполняя никаких действий.</span><span class="sxs-lookup"><span data-stu-id="c8b03-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8b03-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="c8b03-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c8b03-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="c8b03-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c8b03-108">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c8b03-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="c8b03-109">Чтобы создать кнопку «Отмена»</span><span class="sxs-lookup"><span data-stu-id="c8b03-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="c8b03-110">Выберите форму, в которой находится кнопка.</span><span class="sxs-lookup"><span data-stu-id="c8b03-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="c8b03-111">В **свойства** формы задайте окне <xref:System.Windows.Forms.Form.CancelButton%2A> свойства <xref:System.Windows.Forms.Button> имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c8b03-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b03-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c8b03-112">See also</span></span>
- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="c8b03-113">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="c8b03-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [<span data-ttu-id="c8b03-114">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8b03-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="c8b03-115">Практическое руководство. Ответ на нажатие кнопки Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8b03-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="c8b03-116">Практическое руководство. Создание кнопки принятия в конструкторе Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8b03-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="c8b03-117">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="c8b03-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
