---
title: Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms
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
ms.openlocfilehash: 9d095e3561cd346e6dbd99d1be7468f6ad5725a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960458"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="68ab7-102">Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68ab7-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="68ab7-103">Элемент управления <xref:System.Windows.Forms.RichTextBox> Windows Forms имеет множество параметров для форматирования отображаемого текста.</span><span class="sxs-lookup"><span data-stu-id="68ab7-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="68ab7-104">Вы можете отформатировать выбранные абзацы как маркированные списки <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> , задав свойство.</span><span class="sxs-lookup"><span data-stu-id="68ab7-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="68ab7-105">Можно также использовать <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>свойства, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>и <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> для установки отступов абзацев относительно левого и правого краев элемента управления и левого края других строк текста.</span><span class="sxs-lookup"><span data-stu-id="68ab7-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="68ab7-106">Форматирование абзаца в виде маркированного списка</span><span class="sxs-lookup"><span data-stu-id="68ab7-106">To format a paragraph as a bulleted list</span></span>  
  
1. <span data-ttu-id="68ab7-107">Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="68ab7-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="68ab7-108">Чтобы задать отступ абзаца</span><span class="sxs-lookup"><span data-stu-id="68ab7-108">To indent a paragraph</span></span>  
  
1. <span data-ttu-id="68ab7-109">Задайте для <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> свойства целое число, представляющее расстояние в пикселях между левым краями элемента управления и левой границей текста.</span><span class="sxs-lookup"><span data-stu-id="68ab7-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2. <span data-ttu-id="68ab7-110">Задайте для <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> свойства целое число, представляющее расстояние в пикселях между левым краями первой строки текста в абзаце и левым краями последующих строк в одном абзаце.</span><span class="sxs-lookup"><span data-stu-id="68ab7-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="68ab7-111">Значение <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> свойства применяется только к строкам в абзаце, которые были заключены под первой строкой.</span><span class="sxs-lookup"><span data-stu-id="68ab7-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3. <span data-ttu-id="68ab7-112">Задайте для <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> свойства целое число, представляющее расстояние в пикселях между правым ребром элемента управления и правым краю текста.</span><span class="sxs-lookup"><span data-stu-id="68ab7-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
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
    > <span data-ttu-id="68ab7-113">Все эти свойства влияют на все абзацы, содержащие выделенный текст, а также на текст, который будет вводиться после текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="68ab7-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="68ab7-114">Например, когда пользователь выделяет слово в абзаце и затем изменяет параметры отступа, новые параметры будут применяться ко всему абзацу, который содержит это слово, а также ко всем абзацам, которые будут введены после выделенного абзаца.</span><span class="sxs-lookup"><span data-stu-id="68ab7-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="68ab7-115">Дополнительные сведения о выборе текста программным способом <xref:System.Windows.Forms.TextBoxBase.Select%2A>см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="68ab7-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ab7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="68ab7-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="68ab7-117">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="68ab7-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="68ab7-118">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68ab7-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
