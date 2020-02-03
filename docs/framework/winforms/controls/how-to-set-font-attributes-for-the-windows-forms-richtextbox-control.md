---
title: Установка атрибутов шрифта для элемента управления RichTextBox
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
ms.openlocfilehash: f27256c155223df576ee3c42e6bf65270c870b0f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744862"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="bda1c-102">Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bda1c-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="bda1c-103">Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> имеет множество параметров для форматирования отображаемого текста.</span><span class="sxs-lookup"><span data-stu-id="bda1c-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="bda1c-104">Можно сделать выбранные символы полужирным, подчеркнутым или курсивом с помощью свойства <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>.</span><span class="sxs-lookup"><span data-stu-id="bda1c-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="bda1c-105">Это свойство также может использоваться для изменения размера и начертания выбранных символов.</span><span class="sxs-lookup"><span data-stu-id="bda1c-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="bda1c-106">Свойство <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> позволяет изменить цвет выбранных символов.</span><span class="sxs-lookup"><span data-stu-id="bda1c-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="bda1c-107">Изменение внешнего вида символов</span><span class="sxs-lookup"><span data-stu-id="bda1c-107">To change the appearance of characters</span></span>  
  
1. <span data-ttu-id="bda1c-108">Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> соответствующий шрифт.</span><span class="sxs-lookup"><span data-stu-id="bda1c-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="bda1c-109">Чтобы разрешить пользователям задавать семейство шрифтов, размер и гарнитуру в приложении, обычно используется компонент <xref:System.Windows.Forms.FontDialog>.</span><span class="sxs-lookup"><span data-stu-id="bda1c-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="bda1c-110">Его обзор приведен в разделе [Общие сведения о компоненте FontDialog](fontdialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bda1c-110">For an overview, see [FontDialog Component Overview](fontdialog-component-overview-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="bda1c-111">Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> соответствующий цвет.</span><span class="sxs-lookup"><span data-stu-id="bda1c-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="bda1c-112">Чтобы разрешить пользователям задавать цвет в приложении, обычно используется компонент <xref:System.Windows.Forms.ColorDialog>.</span><span class="sxs-lookup"><span data-stu-id="bda1c-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="bda1c-113">Его обзор приведен в разделе [Общие сведения о компоненте ColorDialog](colordialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bda1c-113">For an overview, see [ColorDialog Component Overview](colordialog-component-overview-windows-forms.md).</span></span>  
  
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
    > <span data-ttu-id="bda1c-114">Эти свойства влияют лишь на выделенный текст или, если никакой текст не выбран, текст, вводимый в текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="bda1c-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="bda1c-115">Сведения о программном выборе текста см. в разделе <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="bda1c-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda1c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bda1c-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="bda1c-117">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="bda1c-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="bda1c-118">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bda1c-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
