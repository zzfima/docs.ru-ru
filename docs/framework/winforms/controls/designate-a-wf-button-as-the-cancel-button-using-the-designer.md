---
title: "Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28e1667d086f26759e0129fc62d94ea79c68d880
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="a27c2-102">Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="a27c2-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="a27c2-103">В любой форме Windows Forms можно назначить <xref:System.Windows.Forms.Button> элемента управления "Отмена".</span><span class="sxs-lookup"><span data-stu-id="a27c2-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="a27c2-104">Каждый раз, когда пользователь нажимает клавишу ESC, независимо от других элементов управления в форме имеет фокус по нажатию кнопки "Отмена".</span><span class="sxs-lookup"><span data-stu-id="a27c2-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="a27c2-105">Такая кнопка обычно создается, чтобы пользователь мог быстро прервать операцию, не выполняя никаких действий.</span><span class="sxs-lookup"><span data-stu-id="a27c2-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a27c2-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="a27c2-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a27c2-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="a27c2-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a27c2-108">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a27c2-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="a27c2-109">Чтобы создать кнопку «Отмена»</span><span class="sxs-lookup"><span data-stu-id="a27c2-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="a27c2-110">Выберите форму, в которой находится кнопка.</span><span class="sxs-lookup"><span data-stu-id="a27c2-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="a27c2-111">В **свойства** задайте формы <xref:System.Windows.Forms.Form.CancelButton%2A> свойства <xref:System.Windows.Forms.Button> имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a27c2-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a27c2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a27c2-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="a27c2-113">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="a27c2-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="a27c2-114">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a27c2-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="a27c2-115">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a27c2-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="a27c2-116">Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="a27c2-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="a27c2-117">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="a27c2-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
