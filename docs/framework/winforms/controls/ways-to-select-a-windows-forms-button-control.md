---
title: Способы выбора элемента управления Button
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740006"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="55553-102">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55553-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="55553-103">Кнопку Windows Forms можно выбрать следующими способами.</span><span class="sxs-lookup"><span data-stu-id="55553-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
- <span data-ttu-id="55553-104">Используйте мышь для нажатия кнопки.</span><span class="sxs-lookup"><span data-stu-id="55553-104">Use a mouse to click the button.</span></span>  
  
- <span data-ttu-id="55553-105">Вызов события <xref:System.Windows.Forms.Control.Click> кнопки в коде.</span><span class="sxs-lookup"><span data-stu-id="55553-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
- <span data-ttu-id="55553-106">Переместите фокус на кнопку, нажав клавишу TAB, а затем нажмите клавишу пробел или ввод.</span><span class="sxs-lookup"><span data-stu-id="55553-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
- <span data-ttu-id="55553-107">Нажмите клавишу доступа (ALT + подчеркнутая буква) для кнопки.</span><span class="sxs-lookup"><span data-stu-id="55553-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="55553-108">Дополнительные сведения о ключах доступа см. [в разделе как создать ключи доступа для элементов управления Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="55553-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
- <span data-ttu-id="55553-109">Если кнопка «Accept» («принять») является кнопкой формы, нажатие клавиши Ввод нажимает кнопку, даже если фокус находится на другом элементе управления, за исключением того, что другой элемент управления является другой кнопкой, многострочным текстовым полем или пользовательским элементом управления, который захватывает клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="55553-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
- <span data-ttu-id="55553-110">Если кнопка в форме отменена, нажатие клавиши ESC нажимает кнопку, даже если фокус находится на другом элементе управления.</span><span class="sxs-lookup"><span data-stu-id="55553-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
- <span data-ttu-id="55553-111">Вызовите метод <xref:System.Windows.Forms.Button.PerformClick%2A>, чтобы программно нажать кнопку.</span><span class="sxs-lookup"><span data-stu-id="55553-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55553-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="55553-112">See also</span></span>

- [<span data-ttu-id="55553-113">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="55553-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="55553-114">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55553-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="55553-115">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="55553-115">Button Control</span></span>](button-control-windows-forms.md)
