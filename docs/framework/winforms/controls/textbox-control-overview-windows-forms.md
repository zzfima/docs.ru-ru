---
title: Общие сведения об элементе управления TextBox (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: a91b67df1071c79707bb20a68efb4d5e6f083ae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932552"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="0283f-102">Общие сведения об элементе управления TextBox (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0283f-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="0283f-103">Текстовые поля форм Windows Forms используются для получения входных данных от пользователя или для отображения текста.</span><span class="sxs-lookup"><span data-stu-id="0283f-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="0283f-104"><xref:System.Windows.Forms.TextBox> Управления обычно используется для ввода и редактирования текста, несмотря на то, что его можно также сделать доступным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0283f-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="0283f-105">Текстовые поля можно отобразить несколько строк, переноса текста по размеру элемента управления и добавлять основные элементы форматирования.</span><span class="sxs-lookup"><span data-stu-id="0283f-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="0283f-106"><xref:System.Windows.Forms.TextBox> Элемент управления предоставляет в одном формате, введенные в элементе управления или отображать текст.</span><span class="sxs-lookup"><span data-stu-id="0283f-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="0283f-107">Чтобы отобразить несколько типов форматированного текста, используйте <xref:System.Windows.Forms.RichTextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0283f-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="0283f-108">Дополнительные сведения см. в разделе [Обзор элемента управления RichTextBox](richtextbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0283f-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="0283f-109">Работа с элементом управления TextBox</span><span class="sxs-lookup"><span data-stu-id="0283f-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="0283f-110">Текст, отображаемый элементом управления, содержащийся в <xref:System.Windows.Forms.TextBox.Text%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0283f-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="0283f-111">По умолчанию можно ввести не более 2048 символов в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="0283f-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="0283f-112">Если задать <xref:System.Windows.Forms.TextBox.Multiline%2A> свойства `true`, можно ввести текст до 32 КБ.</span><span class="sxs-lookup"><span data-stu-id="0283f-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="0283f-113"><xref:System.Windows.Forms.TextBox.Text%2A> Свойство можно задать во время разработки в окне свойств во время выполнения в коде, или вводимыми пользователем во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0283f-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="0283f-114">Текущее содержимое текстового поля могут быть получены во время выполнения путем чтения <xref:System.Windows.Forms.TextBox.Text%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0283f-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="0283f-115">В следующем примере кода задает текст в элементе управления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0283f-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="0283f-116">`InitializeMyControl` Процедуры не выполняется автоматически; его необходимо вызывать.</span><span class="sxs-lookup"><span data-stu-id="0283f-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="0283f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0283f-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="0283f-118">Практическое руководство. Управление положением курсора в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="0283f-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="0283f-119">Практическое руководство. Создание текстового поля пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0283f-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0283f-120">Практическое руководство. Создать только для чтения текстовое поле</span><span class="sxs-lookup"><span data-stu-id="0283f-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="0283f-121">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="0283f-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="0283f-122">Практическое руководство. Выделите текст в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="0283f-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0283f-123">Практическое руководство. Просмотр нескольких строк в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="0283f-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0283f-124">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="0283f-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
