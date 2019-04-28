---
title: Элемент управления RichTextBox (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 2b1a6604df3979e83e4a815cdb4a9397ab4e67ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012468"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="a44d3-102">Элемент управления RichTextBox (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a44d3-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="a44d3-103">Windows Forms `RichTextBox` элемент управления используется для отображения, ввода и обработки текста с форматированием.</span><span class="sxs-lookup"><span data-stu-id="a44d3-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="a44d3-104">`RichTextBox` Управления следит за недопущением <xref:System.Windows.Forms.TextBox> делает элемент управления, но можно также отображать шрифты, цвета и ссылки; загрузить текст и встроенные изображения из файла; действия отмены и повтора операций; изменения и находить указанные символы.</span><span class="sxs-lookup"><span data-stu-id="a44d3-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="a44d3-105">`RichTextBox` Управления обычно используется для работы с текстом и отображения функций, как для текстовых редакторов, таких как Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="a44d3-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="a44d3-106">Как <xref:System.Windows.Forms.TextBox> элемента управления, `RichTextBox` элемент управления может отображать полосы прокрутки; но в отличие от <xref:System.Windows.Forms.TextBox> элемента управления, он по умолчанию отображаются горизонтальные и вертикальные полосы прокрутки и имеет дополнительные параметры полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="a44d3-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a44d3-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a44d3-107">In This Section</span></span>  
 [<span data-ttu-id="a44d3-108">Общие сведения об элементе управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a44d3-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="a44d3-109">Основные понятия `RichTextBox` управления, который позволяет пользователям вводить, отображать и изменять текст с форматированием параметров.</span><span class="sxs-lookup"><span data-stu-id="a44d3-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="a44d3-110">Практическое руководство. Определить, при форматировании изменение атрибутов элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a44d3-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="a44d3-111">Объясняет, как для отслеживания изменения шрифта и форматирование абзацев в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a44d3-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="a44d3-112">Практическое руководство. Отображение полос прокрутки в Windows Forms элемента управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a44d3-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="a44d3-113">Описывает варианты полос прокрутки в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a44d3-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="a44d3-114">Практическое руководство. Отображать веб-ссылки с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a44d3-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="a44d3-115">Объясняет создание ссылок на веб-сайтов из `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a44d3-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="a44d3-116">Практическое руководство. Включение операций перетаскивания и вставки с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a44d3-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="a44d3-117">Инструкции для перетаскивания данных в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a44d3-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="a44d3-118">Практическое руководство. Загрузка файлов в элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a44d3-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="a44d3-119">Содержит инструкции по загрузке существующего файла в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a44d3-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="a44d3-120">Практическое руководство. Сохранение файлов с использованием элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a44d3-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="a44d3-121">Инструкции по сохранению содержимого `RichTextBox` элемента управления в файл.</span><span class="sxs-lookup"><span data-stu-id="a44d3-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="a44d3-122">Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a44d3-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="a44d3-123">Описывает способ задания семейство шрифтов, размер, стиль и цвет текста в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a44d3-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="a44d3-124">Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a44d3-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="a44d3-125">Описывает форматирование абзацев в `RichTextBox` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a44d3-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a44d3-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="a44d3-126">Reference</span></span>  
 <span data-ttu-id="a44d3-127">Класс <xref:System.Windows.Forms.RichTextBox></span><span class="sxs-lookup"><span data-stu-id="a44d3-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="a44d3-128">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="a44d3-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a44d3-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a44d3-129">Related Sections</span></span>  
 [<span data-ttu-id="a44d3-130">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a44d3-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="a44d3-131">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="a44d3-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="a44d3-132">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="a44d3-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="a44d3-133">Основные понятия <xref:System.Windows.Forms.TextBox> управления, который позволяет вводить изменяемый текст от пользователя.</span><span class="sxs-lookup"><span data-stu-id="a44d3-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
