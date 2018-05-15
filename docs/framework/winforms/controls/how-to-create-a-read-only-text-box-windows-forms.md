---
title: Практическое руководство. Создание текстового поля, доступного только для чтения (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 06e03f67bd1f084b30bce85c3d81ad7b8c97a1b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="aed54-102">Практическое руководство. Создание текстового поля, доступного только для чтения (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="aed54-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="aed54-103">Для редактирования текстовое поле Windows Forms можно преобразовать в элемент управления только для чтения.</span><span class="sxs-lookup"><span data-stu-id="aed54-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="aed54-104">Например текстовое поле может отображать значение, которое обычно изменяется, но в настоящее время не может быть из-за состояния приложения.</span><span class="sxs-lookup"><span data-stu-id="aed54-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="aed54-105">Чтобы создать поле текст только для чтения</span><span class="sxs-lookup"><span data-stu-id="aed54-105">To create a read-only text box</span></span>  
  
1.  <span data-ttu-id="aed54-106">Задать <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="aed54-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="aed54-107">Со свойством, имеющим значение `true`, пользователи могут прокручивать и выделять текст в текстовом поле не изменять.</span><span class="sxs-lookup"><span data-stu-id="aed54-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="aed54-108">Объект **копирования** команда работает в текстовом поле, но **Вырезать** и **вставить** команды не.</span><span class="sxs-lookup"><span data-stu-id="aed54-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aed54-109"><xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Свойство влияет только на взаимодействие с пользователем во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="aed54-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="aed54-110">Можно по-прежнему изменить содержимое текстового поля программными средствами во время выполнения, изменив <xref:System.Windows.Forms.TextBox.Text%2A> свойства текстового поля.</span><span class="sxs-lookup"><span data-stu-id="aed54-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed54-111">См. также</span><span class="sxs-lookup"><span data-stu-id="aed54-111">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="aed54-112">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="aed54-112">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="aed54-113">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aed54-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="aed54-114">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aed54-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="aed54-115">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="aed54-115">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="aed54-116">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aed54-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="aed54-117">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aed54-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="aed54-118">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="aed54-118">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
