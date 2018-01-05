---
title: "Элемент управления RichTextBox (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4325fd3eb2e3d7179ddb5270d073c7ba5f0f383f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="c9be4-102">Элемент управления RichTextBox (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c9be4-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="c9be4-103">Windows Forms `RichTextBox` элемент управления используется для отображения, ввода и изменения текста с форматированием.</span><span class="sxs-lookup"><span data-stu-id="c9be4-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="c9be4-104">`RichTextBox` Элемент управления выполняет все, что <xref:System.Windows.Forms.TextBox> делает элемент управления, но можно также отображать шрифты, цвета и ссылки; загрузить из файла; действия отмены и повтора операций; изменения текста и внедренные изображения и поиск определенных символов.</span><span class="sxs-lookup"><span data-stu-id="c9be4-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="c9be4-105">`RichTextBox` Элемент управления обычно используется для работы с текстом и отображения функций, как для текстовых редакторов, таких как Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="c9be4-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="c9be4-106">Как <xref:System.Windows.Forms.TextBox> управления `RichTextBox` элемент управления может отображать полосы прокрутки; но в отличие от <xref:System.Windows.Forms.TextBox> элемента управления, он отображает горизонтальные и вертикальные полосы прокрутки по умолчанию и параметры дополнительной полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="c9be4-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9be4-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c9be4-107">In This Section</span></span>  
 [<span data-ttu-id="c9be4-108">Общие сведения об элементе управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="c9be4-108">RichTextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="c9be4-109">Основные понятия `RichTextBox` управления, который позволяет пользователям вводить, отображать и изменять текст с помощью операций форматирования.</span><span class="sxs-lookup"><span data-stu-id="c9be4-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="c9be4-110">Практическое руководство. Отслеживание изменения атрибутов форматирования текста в элементе управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="c9be4-111">Объясняется, как отслеживать изменения шрифта и форматирование абзацев в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9be4-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c9be4-112">Практическое руководство. Отображение полос прокрутки в элементе управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c9be4-113">Описаны варианты полос прокрутки в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9be4-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c9be4-114">Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c9be4-115">Объясняется, как создавать ссылки на веб-сайты из `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9be4-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c9be4-116">Практическое руководство. Разрешение операций перетаскивания для элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="c9be4-117">Инструкции по перетаскиванию данных в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9be4-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c9be4-118">Практическое руководство. Загрузка файлов в элемент управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c9be4-119">Приводятся инструкции по загрузке существующего файла в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9be4-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c9be4-120">Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c9be4-121">Приводятся инструкции по записи содержимого `RichTextBox` элемента управления в файл.</span><span class="sxs-lookup"><span data-stu-id="c9be4-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="c9be4-122">Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c9be4-123">Описывает, как установить семейство шрифтов, размер, стиль и цвет текста в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9be4-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c9be4-124">Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="c9be4-125">Описывает форматирование абзацев в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9be4-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c9be4-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="c9be4-126">Reference</span></span>  
 <span data-ttu-id="c9be4-127">Класс <xref:System.Windows.Forms.RichTextBox></span><span class="sxs-lookup"><span data-stu-id="c9be4-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="c9be4-128">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="c9be4-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c9be4-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c9be4-129">Related Sections</span></span>  
 [<span data-ttu-id="c9be4-130">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9be4-130">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="c9be4-131">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="c9be4-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="c9be4-132">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="c9be4-132">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)  
 <span data-ttu-id="c9be4-133">Основные понятия <xref:System.Windows.Forms.TextBox> управления, который позволяет вводить изменяемый текст от пользователя.</span><span class="sxs-lookup"><span data-stu-id="c9be4-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
