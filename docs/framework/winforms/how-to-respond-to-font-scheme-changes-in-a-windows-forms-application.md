---
title: Реагирование на изменения шрифтовой схемы в приложении Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739226"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="af0f3-102">Практическое руководство. Реагирование на изменения схемы шрифтов в приложениях Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af0f3-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="af0f3-103">В операционных системах Windows пользователь может изменить параметры шрифта в масштабе всей системы, сделав шрифт по умолчанию больше или меньше.</span><span class="sxs-lookup"><span data-stu-id="af0f3-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="af0f3-104">Изменение этих параметров шрифта является критически важным для пользователей, имеющих визуальное нарушение, и требует большего размера для чтения текста на своих экранах.</span><span class="sxs-lookup"><span data-stu-id="af0f3-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="af0f3-105">Можно настроить приложение Windows Forms для реагирования на эти изменения, увеличивая или уменьшая размер формы и весь содержащийся в ней текст при изменении шрифтовой схемы.</span><span class="sxs-lookup"><span data-stu-id="af0f3-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="af0f3-106">Если требуется, чтобы форма автоматически соответствовала изменениям размеров шрифтов, можно добавить код в форму.</span><span class="sxs-lookup"><span data-stu-id="af0f3-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="af0f3-107">Как правило, шрифтом по умолчанию, используемым Windows Forms, является шрифт, возвращаемый вызовом пространства имен <xref:Microsoft.Win32> в `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="af0f3-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="af0f3-108">Шрифт, возвращаемый этим вызовом, изменяется только при изменении разрешения экрана.</span><span class="sxs-lookup"><span data-stu-id="af0f3-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="af0f3-109">Как показано в следующей процедуре, код должен изменить шрифт по умолчанию на <xref:System.Drawing.SystemFonts.IconTitleFont%2A>, чтобы реагировать на изменения размера шрифта.</span><span class="sxs-lookup"><span data-stu-id="af0f3-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="af0f3-110">Использование шрифта рабочего стола и реагирование на изменения схемы шрифтов</span><span class="sxs-lookup"><span data-stu-id="af0f3-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1. <span data-ttu-id="af0f3-111">Создайте форму и добавьте в нее нужные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="af0f3-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="af0f3-112">Дополнительные сведения см. в разделе [инструкции. создание Windows Forms приложения из командной строки](how-to-create-a-windows-forms-application-from-the-command-line.md) и [элементов управления для использования в Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="af0f3-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="af0f3-113">Добавьте ссылку на пространство имен <xref:Microsoft.Win32> в код.</span><span class="sxs-lookup"><span data-stu-id="af0f3-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="af0f3-114">Добавьте следующий код в конструктор формы, чтобы подключить необходимые обработчики событий и изменить используемый по умолчанию шрифт для формы.</span><span class="sxs-lookup"><span data-stu-id="af0f3-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="af0f3-115">Реализуйте обработчик для события <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>, которое приводит к автоматическому масштабированию формы при изменении категории <xref:Microsoft.Win32.UserPreferenceCategory.Window>.</span><span class="sxs-lookup"><span data-stu-id="af0f3-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. <span data-ttu-id="af0f3-116">Наконец, реализуйте обработчик для события <xref:System.Windows.Forms.Form.FormClosing>, которое отсоединяет обработчик событий <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="af0f3-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="af0f3-117">Сбой включения этого кода приведет к утечке памяти в приложении.</span><span class="sxs-lookup"><span data-stu-id="af0f3-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. <span data-ttu-id="af0f3-118">Скомпилируйте и запустите код.</span><span class="sxs-lookup"><span data-stu-id="af0f3-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="af0f3-119">Изменение схемы шрифтов в Windows XP вручную</span><span class="sxs-lookup"><span data-stu-id="af0f3-119">To manually change the font scheme in Windows XP</span></span>  
  
1. <span data-ttu-id="af0f3-120">Пока приложение Windows Forms работает, щелкните правой кнопкой мыши рабочий стол Windows и выберите в контекстном меню пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="af0f3-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="af0f3-121">В диалоговом окне **Свойства экрана** перейдите на вкладку **вид** .</span><span class="sxs-lookup"><span data-stu-id="af0f3-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3. <span data-ttu-id="af0f3-122">В раскрывающемся списке **Размер шрифта** выберите новый размер шрифта.</span><span class="sxs-lookup"><span data-stu-id="af0f3-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="af0f3-123">Обратите внимание, что форма теперь реагирует на изменения, внесенные во время выполнения в шрифтовую схему рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="af0f3-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="af0f3-124">При изменении пользователем между **обычными**, **крупными шрифтами**и **очень крупными шрифтами**форма изменяет шрифт и масштабируется правильно.</span><span class="sxs-lookup"><span data-stu-id="af0f3-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af0f3-125">Пример</span><span class="sxs-lookup"><span data-stu-id="af0f3-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="af0f3-126">Конструктор в этом примере кода содержит вызов `InitializeComponent`, который определяется при создании нового проекта Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="af0f3-126">The constructor in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="af0f3-127">Удалите эту строку кода, если вы создаете приложение в командной строке.</span><span class="sxs-lookup"><span data-stu-id="af0f3-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0f3-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="af0f3-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="af0f3-129">Автоматическое масштабирование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af0f3-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
