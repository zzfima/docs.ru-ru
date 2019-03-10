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
ms.openlocfilehash: 92578bd267230f5878bda9533bd117e8f98d8f13
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714688"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a026d-102">Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a026d-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a026d-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления имеет разнообразные варианты форматирования отображаемого в нем текста.</span><span class="sxs-lookup"><span data-stu-id="a026d-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="a026d-104">Вы можете выделить выбранные символы полужирным, подчеркнутым шрифтом или курсивом, с помощью <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a026d-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="a026d-105">Это свойство также может использоваться для изменения размера и начертания выбранных символов.</span><span class="sxs-lookup"><span data-stu-id="a026d-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="a026d-106"><xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Свойства можно изменить цвет выбранных символов.</span><span class="sxs-lookup"><span data-stu-id="a026d-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="a026d-107">Изменение внешнего вида символов</span><span class="sxs-lookup"><span data-stu-id="a026d-107">To change the appearance of characters</span></span>  
  
1.  <span data-ttu-id="a026d-108">Задайте <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> свойство соответствующий шрифт.</span><span class="sxs-lookup"><span data-stu-id="a026d-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="a026d-109">Чтобы обеспечить пользователям возможность выбора семейства шрифтов, размера и начертания в приложении, обычно используется <xref:System.Windows.Forms.FontDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="a026d-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="a026d-110">Его обзор приведен в разделе [Общие сведения о компоненте FontDialog](fontdialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a026d-110">For an overview, see [FontDialog Component Overview](fontdialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="a026d-111">Задайте <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> свойство соответствующий цвет.</span><span class="sxs-lookup"><span data-stu-id="a026d-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="a026d-112">Чтобы пользователи могли установить цвет в приложении, обычно используется <xref:System.Windows.Forms.ColorDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="a026d-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="a026d-113">Его обзор приведен в разделе [Общие сведения о компоненте ColorDialog](colordialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a026d-113">For an overview, see [ColorDialog Component Overview](colordialog-component-overview-windows-forms.md).</span></span>  
  
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
    >  <span data-ttu-id="a026d-114">Эти свойства влияют лишь на выделенный текст или, если никакой текст не выбран, текст, вводимый в текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="a026d-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="a026d-115">Сведения о программном выборе текста см. в разделе <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="a026d-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a026d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a026d-116">See also</span></span>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="a026d-117">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a026d-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="a026d-118">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a026d-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
