---
title: Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
ms.openlocfilehash: 7c4c9362bb5a32bd8d5afc2b1edeb935d505fd19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="63b98-102">Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="63b98-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="63b98-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления поддерживает разнообразные варианты форматирования текста, он отображает.</span><span class="sxs-lookup"><span data-stu-id="63b98-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="63b98-104">Внесения выделенных символов полужирным, подчеркнутым или курсивом, с помощью <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="63b98-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="63b98-105">Это свойство также может использоваться для изменения размера и начертания выбранных символов.</span><span class="sxs-lookup"><span data-stu-id="63b98-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="63b98-106"><xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Свойства можно изменить цвет выделенных символов.</span><span class="sxs-lookup"><span data-stu-id="63b98-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="63b98-107">Изменение внешнего вида символов</span><span class="sxs-lookup"><span data-stu-id="63b98-107">To change the appearance of characters</span></span>  
  
1.  <span data-ttu-id="63b98-108">Задать <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> свойства в соответствующий шрифт.</span><span class="sxs-lookup"><span data-stu-id="63b98-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="63b98-109">Чтобы пользователи могли установить семейство шрифтов, размер и начертание шрифта в приложение, обычно используется <xref:System.Windows.Forms.FontDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="63b98-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="63b98-110">Его обзор приведен в разделе [Общие сведения о компоненте FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="63b98-110">For an overview, see [FontDialog Component Overview](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="63b98-111">Задать <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> свойства неподходящим.</span><span class="sxs-lookup"><span data-stu-id="63b98-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="63b98-112">Чтобы пользователи могли установить цвет в приложении, обычно используется <xref:System.Windows.Forms.ColorDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="63b98-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="63b98-113">Его обзор приведен в разделе [Общие сведения о компоненте ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="63b98-113">For an overview, see [ColorDialog Component Overview](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).</span></span>  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="63b98-114">Эти свойства влияют лишь на выделенный текст или, если никакой текст не выбран, текст, вводимый в текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="63b98-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="63b98-115">Сведения о выделение текста программными средствами см. в разделе <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="63b98-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b98-116">См. также</span><span class="sxs-lookup"><span data-stu-id="63b98-116">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="63b98-117">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="63b98-117">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="63b98-118">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="63b98-118">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
