---
title: Практическое руководство. Многострочные элементы управления TextBox в Windows Forms
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
ms.openlocfilehash: f7a0e3a14d14f0629bd9995dbecd3f0b98bea1d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190916"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="cae81-102">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cae81-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="cae81-103">По умолчанию в Windows Forms <xref:System.Windows.Forms.TextBox> элемент управления выводит одну строку текста и не отображает полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="cae81-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="cae81-104">Если текст длиннее, чем свободное пространство, отображается только часть текста.</span><span class="sxs-lookup"><span data-stu-id="cae81-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="cae81-105">Это поведение по умолчанию можно изменить, задав <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, и <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующие значения свойств.</span><span class="sxs-lookup"><span data-stu-id="cae81-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="cae81-106">Для отображения возврата каретки в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="cae81-106">To display a carriage return in the TextBox control</span></span>  
  
-   <span data-ttu-id="cae81-107">Для отображения возврата каретки в многострочном <xref:System.Windows.Forms.TextBox>, используйте <xref:System.Environment.NewLine%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="cae81-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="cae81-108">Имейте в виду, что интерпретация escape-символы (\\) зависит от конкретного языка.</span><span class="sxs-lookup"><span data-stu-id="cae81-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="cae81-109">Visual Basic использует `Chr$(13) & Chr$(10)` для сочетания символов возврата и перевода строки каретки.</span><span class="sxs-lookup"><span data-stu-id="cae81-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="cae81-110">Чтобы просмотреть несколько строк в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="cae81-110">To view multiple lines in the TextBox control</span></span>  
  
1.  <span data-ttu-id="cae81-111">Задайте для свойства <xref:System.Windows.Forms.TextBox.Multiline%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="cae81-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="cae81-112">Если <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> является `true` (по умолчанию), затем будет отображаться как один или несколько абзацев текст в элементе управления; в противном случае он будет отображаться в виде списка, в которой некоторые строки могут быть обрезаны на границе элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cae81-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2.  <span data-ttu-id="cae81-113">Присвойте свойству <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="cae81-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="cae81-114">Значение</span><span class="sxs-lookup"><span data-stu-id="cae81-114">Value</span></span>|<span data-ttu-id="cae81-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cae81-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="cae81-116">Используйте это значение, если текст будет выровнен по абзаца, вмещаться элементе управления.</span><span class="sxs-lookup"><span data-stu-id="cae81-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="cae81-117">Пользователь может использовать указатель мыши для перемещения внутри элемента управления, если текст слишком велика, чтобы отобразить все сразу.</span><span class="sxs-lookup"><span data-stu-id="cae81-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="cae81-118">Используйте это значение, если вы хотите отобразить список строк, некоторые из которых может превышать ширину <xref:System.Windows.Forms.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cae81-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="cae81-119">Это значение используется в том случае, если список может быть больше времени, чем высота элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cae81-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3.  <span data-ttu-id="cae81-120">Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="cae81-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="cae81-121">Значение</span><span class="sxs-lookup"><span data-stu-id="cae81-121">Value</span></span>|<span data-ttu-id="cae81-122">Описание</span><span class="sxs-lookup"><span data-stu-id="cae81-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="cae81-123">Текст в элементе управления будет не переносится автоматически, поэтому он будет прокручивать экран вправо до достижения конца строки.</span><span class="sxs-lookup"><span data-stu-id="cae81-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="cae81-124">Используйте это значение, если вы выбрали <xref:System.Windows.Forms.ScrollBars.Horizontal> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.Both>выше.</span><span class="sxs-lookup"><span data-stu-id="cae81-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |`true` <span data-ttu-id="cae81-125">(по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cae81-125">(default)</span></span>|<span data-ttu-id="cae81-126">Горизонтальная полоса прокрутки не появится.</span><span class="sxs-lookup"><span data-stu-id="cae81-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="cae81-127">Используйте это значение, если вы выбрали <xref:System.Windows.Forms.ScrollBars.Vertical> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.None>выше, чтобы отобразить один или несколько абзацев.</span><span class="sxs-lookup"><span data-stu-id="cae81-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cae81-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cae81-128">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="cae81-129">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="cae81-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="cae81-130">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cae81-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="cae81-131">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cae81-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="cae81-132">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="cae81-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="cae81-133">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="cae81-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="cae81-134">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cae81-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="cae81-135">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="cae81-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
