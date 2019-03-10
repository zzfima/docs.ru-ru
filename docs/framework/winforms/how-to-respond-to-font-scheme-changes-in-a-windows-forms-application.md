---
title: Практическое руководство. Реагирование на изменения схемы шрифтов в приложении Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 4c34a65ed8ddabfb99451e055048502cb7617e4f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715975"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="4b275-102">Практическое руководство. Реагирование на изменения схемы шрифтов в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b275-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="4b275-103">В операционных системах Windows пользователь может изменить параметры шрифта во всей системе, чтобы проверить шрифт по умолчанию отображаются, больше или меньше.</span><span class="sxs-lookup"><span data-stu-id="4b275-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="4b275-104">Изменение этих параметров шрифта важно для пользователей с нарушениями зрения и требуют более длинный тип для чтения текста на экране компьютера.</span><span class="sxs-lookup"><span data-stu-id="4b275-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="4b275-105">Вы можете настроить приложение Windows Forms реагировать на эти изменения путем увеличения или уменьшения размера формы и все содержащиеся в нем текст при каждом изменении шрифтовой схемы.</span><span class="sxs-lookup"><span data-stu-id="4b275-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="4b275-106">Если требуется, чтобы формы в соответствии с изменениями в размерах шрифта динамически, можно добавить код в форму.</span><span class="sxs-lookup"><span data-stu-id="4b275-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="4b275-107">Как правило, шрифт по умолчанию, используемые в Windows Forms используется шрифт, возвращенный <xref:Microsoft.Win32> вызов пространства имен `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="4b275-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="4b275-108">Шрифт, возвращаемый при вызове этого метода изменяется только при изменении разрешения экрана.</span><span class="sxs-lookup"><span data-stu-id="4b275-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="4b275-109">Как показано в следующей процедуре, ваш код должен изменить шрифт по умолчанию для <xref:System.Drawing.SystemFonts.IconTitleFont%2A> реагировать на изменения размера шрифта.</span><span class="sxs-lookup"><span data-stu-id="4b275-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="4b275-110">Чтобы использовать шрифт рабочего стола и реагировать на изменения схемы шрифтов</span><span class="sxs-lookup"><span data-stu-id="4b275-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="4b275-111">Создайте форму и добавьте элементы управления к нему.</span><span class="sxs-lookup"><span data-stu-id="4b275-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="4b275-112">Дополнительные сведения см. в разделе [Как Создание приложения Windows Forms из командной строки](how-to-create-a-windows-forms-application-from-the-command-line.md) и [элементы управления для использования в формах Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4b275-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="4b275-113">Добавьте ссылку на <xref:Microsoft.Win32> пространства имен в код.</span><span class="sxs-lookup"><span data-stu-id="4b275-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="4b275-114">Добавьте следующий код в конструктор формы для привязки обработчиков событий, а также изменять шрифт по умолчанию используется для формы.</span><span class="sxs-lookup"><span data-stu-id="4b275-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="4b275-115">Реализовать обработчик для <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> событие, которое приводит к автоматическому масштабированию формы при <xref:Microsoft.Win32.UserPreferenceCategory.Window> категории изменения.</span><span class="sxs-lookup"><span data-stu-id="4b275-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="4b275-116">Наконец, Реализуйте обработчик для <xref:System.Windows.Forms.Form.FormClosing> событие, которое отсоединяет <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="4b275-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="4b275-117">Если не добавить этот код вызовет утечка памяти.</span><span class="sxs-lookup"><span data-stu-id="4b275-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  <span data-ttu-id="4b275-118">Скомпилируйте и запустите код.</span><span class="sxs-lookup"><span data-stu-id="4b275-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="4b275-119">Для ручного изменения схемы шрифтов в Windows XP</span><span class="sxs-lookup"><span data-stu-id="4b275-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="4b275-120">Пока выполняется приложение Windows Forms, щелкните правой кнопкой мыши рабочий стол Windows и выберите **свойства** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="4b275-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="4b275-121">В **свойства отображения** диалоговом окне щелкните **внешний вид** вкладки.</span><span class="sxs-lookup"><span data-stu-id="4b275-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="4b275-122">Из **размер шрифта** раскрывающемся списке выберите новый размер шрифта.</span><span class="sxs-lookup"><span data-stu-id="4b275-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="4b275-123">Вы заметите, что форма теперь реагирует на изменения схемы шрифтов рабочего стола во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b275-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="4b275-124">Когда пользователь изменяет между **обычный**, **крупного шрифта**, и **Огромный шрифт**, форма изменяет шрифт и корректно масштабируется.</span><span class="sxs-lookup"><span data-stu-id="4b275-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b275-125">Пример</span><span class="sxs-lookup"><span data-stu-id="4b275-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="4b275-126">Конструктор в этом примере код содержит вызов `InitializeComponent`, который определяется при создании нового проекта Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4b275-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="4b275-127">Удалите эту строку кода, при создании приложения в командной строке.</span><span class="sxs-lookup"><span data-stu-id="4b275-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b275-128">См. также</span><span class="sxs-lookup"><span data-stu-id="4b275-128">See also</span></span>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="4b275-129">Автоматическое масштабирование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b275-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
