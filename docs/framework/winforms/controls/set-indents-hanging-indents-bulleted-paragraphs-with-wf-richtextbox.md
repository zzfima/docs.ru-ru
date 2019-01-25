---
title: Как выполнить Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: ad5dd1cc3839fbe29d39f6ab38b0e865e7b0a335
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492431"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="360ae-102">Как выполнить Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="360ae-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="360ae-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления имеет разнообразные варианты форматирования отображаемого в нем текста.</span><span class="sxs-lookup"><span data-stu-id="360ae-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="360ae-104">Можно форматировать выделенные абзацы в виде маркированных списков, задав <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="360ae-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="360ae-105">Можно также использовать <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, и <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> свойства, чтобы задать отступ абзацев относительно левой и правой границ элемента управления и левого края остальных строк текста.</span><span class="sxs-lookup"><span data-stu-id="360ae-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="360ae-106">Форматирование абзаца в виде маркированного списка</span><span class="sxs-lookup"><span data-stu-id="360ae-106">To format a paragraph as a bulleted list</span></span>  
  
1.  <span data-ttu-id="360ae-107">Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="360ae-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="360ae-108">Чтобы задать отступ абзаца</span><span class="sxs-lookup"><span data-stu-id="360ae-108">To indent a paragraph</span></span>  
  
1.  <span data-ttu-id="360ae-109">Задайте <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> свойство в целое число, представляющее расстояние в пикселях между левым краем элемента управления и левой границей текста.</span><span class="sxs-lookup"><span data-stu-id="360ae-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2.  <span data-ttu-id="360ae-110">Задайте <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> свойство в целое число, представляющее расстояние в пикселях между левым краем первой строки текста в абзаце и левой границей последующих строк того же абзаца.</span><span class="sxs-lookup"><span data-stu-id="360ae-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="360ae-111">Значение <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> свойство применяется только к строкам абзаца, следующим первой строки.</span><span class="sxs-lookup"><span data-stu-id="360ae-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3.  <span data-ttu-id="360ae-112">Задайте <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> свойство в целое число, представляющее расстояние в пикселях между правым краем элемента управления и правым краем текста.</span><span class="sxs-lookup"><span data-stu-id="360ae-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="360ae-113">Все эти свойства влияют на все абзацы, содержащие выделенный текст, а также на текст, который будет вводиться после текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="360ae-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="360ae-114">Например, когда пользователь выделяет слово в абзаце и затем изменяет параметры отступа, новые параметры будут применяться ко всему абзацу, который содержит это слово, а также ко всем абзацам, которые будут введены после выделенного абзаца.</span><span class="sxs-lookup"><span data-stu-id="360ae-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="360ae-115">Сведения о программном выборе текста см. в разделе <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="360ae-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="360ae-116">См. также</span><span class="sxs-lookup"><span data-stu-id="360ae-116">See also</span></span>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="360ae-117">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="360ae-117">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [<span data-ttu-id="360ae-118">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="360ae-118">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
