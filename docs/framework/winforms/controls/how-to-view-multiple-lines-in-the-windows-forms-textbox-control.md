---
title: Просмотр нескольких строк в элементе управления TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728284"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="0a8dd-102">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a8dd-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="0a8dd-103">По умолчанию элемент управления Windows Forms <xref:System.Windows.Forms.TextBox> отображает одну строку текста и не отображает полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="0a8dd-104">Если текст превышает доступное пространство, отображается только часть текста.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="0a8dd-105">Это поведение по умолчанию можно изменить, задав для свойств <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>и <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующие значения.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="0a8dd-106">Отображение возврата каретки в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="0a8dd-106">To display a carriage return in the TextBox control</span></span>  
  
- <span data-ttu-id="0a8dd-107">Чтобы отобразить возврат каретки в многострочном <xref:System.Windows.Forms.TextBox>, используйте свойство <xref:System.Environment.NewLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="0a8dd-108">Имейте в виду, что интерпретация escape-символов (\\) зависит от языка.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="0a8dd-109">Visual Basic использует `Chr$(13) & Chr$(10)` для сочетания символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="0a8dd-110">Просмотр нескольких строк в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="0a8dd-110">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="0a8dd-111">Установите свойство <xref:System.Windows.Forms.TextBox.Multiline%2A> в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="0a8dd-112">Если <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `true` (по умолчанию), то текст в элементе управления будет отображаться как один или несколько абзацев. в противном случае он будет отображаться в виде списка, в котором некоторые строки могут быть обрезаны по границе элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="0a8dd-113">Присвойте свойству <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="0a8dd-114">Значение</span><span class="sxs-lookup"><span data-stu-id="0a8dd-114">Value</span></span>|<span data-ttu-id="0a8dd-115">Description</span><span class="sxs-lookup"><span data-stu-id="0a8dd-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="0a8dd-116">Используйте это значение, если текст будет абзацем, который почти всегда соответствует элементу управления.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="0a8dd-117">Пользователь может использовать указатель мыши для перемещения внутри элемента управления, если текст слишком длинный, чтобы отобразить все одновременно.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="0a8dd-118">Используйте это значение, если требуется отобразить список строк, некоторые из которых могут быть длиннее ширины элемента управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="0a8dd-119">Используйте это значение, если список может быть длиннее, чем высота элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="0a8dd-120">Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="0a8dd-121">Значение</span><span class="sxs-lookup"><span data-stu-id="0a8dd-121">Value</span></span>|<span data-ttu-id="0a8dd-122">Description</span><span class="sxs-lookup"><span data-stu-id="0a8dd-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="0a8dd-123">Текст в элементе управления не будет автоматически заключаться в оболочку, поэтому он будет прокручиваться вправо до тех пор, пока не будет достигнут разрыв строки.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="0a8dd-124">Используйте это значение, если выбраны <xref:System.Windows.Forms.ScrollBars.Horizontal> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.Both>выше.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="0a8dd-125">`true` (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0a8dd-125">`true` (default)</span></span>|<span data-ttu-id="0a8dd-126">Горизонтальная полоса прокрутки не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="0a8dd-127">Используйте это значение, если для отображения одного или нескольких абзацев выбраны <xref:System.Windows.Forms.ScrollBars.Vertical> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.None>выше.</span><span class="sxs-lookup"><span data-stu-id="0a8dd-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a8dd-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0a8dd-128">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="0a8dd-129">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="0a8dd-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0a8dd-130">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a8dd-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="0a8dd-131">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a8dd-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0a8dd-132">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="0a8dd-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="0a8dd-133">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="0a8dd-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="0a8dd-134">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a8dd-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0a8dd-135">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="0a8dd-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
