---
title: "Способы активации элемента управления Button в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b6fa31b89b8fbe50077933cf04aa3c17db86438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="08dc9-102">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08dc9-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="08dc9-103">Кнопки Windows Forms можно выбрать следующими способами:</span><span class="sxs-lookup"><span data-stu-id="08dc9-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="08dc9-104">Нажмите кнопку мышью.</span><span class="sxs-lookup"><span data-stu-id="08dc9-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="08dc9-105">Кнопка вызова <xref:System.Windows.Forms.Control.Click> события в коде.</span><span class="sxs-lookup"><span data-stu-id="08dc9-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="08dc9-106">Перемещение фокуса к кнопке по нажатию клавиши TAB и затем нажмите кнопку, нажав клавишу ПРОБЕЛ или ВВОД.</span><span class="sxs-lookup"><span data-stu-id="08dc9-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="08dc9-107">Нажмите клавишу доступа (ALT + подчеркнутая буква) для кнопки.</span><span class="sxs-lookup"><span data-stu-id="08dc9-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="08dc9-108">Дополнительные сведения о ключах доступа см. в разделе [как: Создание сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="08dc9-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="08dc9-109">Если кнопка является кнопкой «принять», формы, нажатие клавиши ВВОД активирует кнопку, даже если фокус находится на другом элементе управления, только если этот элемент управления является кнопкой, многострочным текстовым полем или пользовательский элемент управления, который перехватывает клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="08dc9-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="08dc9-110">Если кнопка является кнопкой «Отмена» в форме, нажатие клавиши ESC активирует кнопку, даже если другой элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="08dc9-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="08dc9-111">Вызовите <xref:System.Windows.Forms.Button.PerformClick%2A> метод, чтобы активировать кнопку программными средствами.</span><span class="sxs-lookup"><span data-stu-id="08dc9-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08dc9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="08dc9-112">See Also</span></span>  
 [<span data-ttu-id="08dc9-113">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="08dc9-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="08dc9-114">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08dc9-114">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="08dc9-115">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="08dc9-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
