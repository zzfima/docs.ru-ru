---
title: Пошаговое руководство. Обновление строки состояния во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: 49722d5dadf694e8ee3037646652b921ddda3e91
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44135657"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="d469f-102">Пошаговое руководство. Обновление строки состояния во время выполнения</span><span class="sxs-lookup"><span data-stu-id="d469f-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="d469f-103"><xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и расширяют функциональные возможности для <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления сохраняются для обеспечения обратной совместимости и использования в будущем, если вы Выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="d469f-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="d469f-104">Часто программа требует динамического обновления содержимого панелей строки состояния в среде выполнения с учетом изменений в состоянии приложения или других взаимодействий с пользователем.</span><span class="sxs-lookup"><span data-stu-id="d469f-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="d469f-105">Это обычный способ сообщить пользователям о том, что CAPS LOCK, NUM LOCK или SCROLL LOCK включен, или сообщить ему дату или время в удобном формате.</span><span class="sxs-lookup"><span data-stu-id="d469f-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="d469f-106">В следующем примере используется экземпляр <xref:System.Windows.Forms.StatusBarPanel> класса для размещения часов.</span><span class="sxs-lookup"><span data-stu-id="d469f-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="d469f-107">Получение строки состояния, готовой для обновления</span><span class="sxs-lookup"><span data-stu-id="d469f-107">To get the status bar ready for updating</span></span>  
  
1.  <span data-ttu-id="d469f-108">Создание новой формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d469f-108">Create a new Windows form.</span></span>  
  
2.  <span data-ttu-id="d469f-109">Добавьте элемент управления <xref:System.Windows.Forms.StatusBar> в форму.</span><span class="sxs-lookup"><span data-stu-id="d469f-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="d469f-110">Дополнительные сведения см. в разделе [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d469f-110">For details, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="d469f-111">Добавьте панель строки состояния для вашей <xref:System.Windows.Forms.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d469f-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="d469f-112">Дополнительные сведения см. в разделе [Практическое руководство. Добавление панелей в элемент управления StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="d469f-112">For details, see [How to: Add Panels to a StatusBar Control](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4.  <span data-ttu-id="d469f-113">Для <xref:System.Windows.Forms.StatusBar> вы добавили в форму элемента управления значение <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="d469f-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="d469f-114">Добавление форм Windows <xref:System.Windows.Forms.Timer> в форму компонент.</span><span class="sxs-lookup"><span data-stu-id="d469f-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d469f-115">Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> компонент разработан для среды Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d469f-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="d469f-116">Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="d469f-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
6.  <span data-ttu-id="d469f-117">Задайте для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d469f-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7.  <span data-ttu-id="d469f-118">Задайте <xref:System.Windows.Forms.Timer.Interval%2A> свойство <xref:System.Windows.Forms.Timer> значение 30000.</span><span class="sxs-lookup"><span data-stu-id="d469f-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d469f-119"><xref:System.Windows.Forms.Timer.Interval%2A> Свойство <xref:System.Windows.Forms.Timer> компонент устанавливается равным 30 секундам (30 000 миллисекунд), чтобы гарантировать, отражали точного времени для отображения.</span><span class="sxs-lookup"><span data-stu-id="d469f-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="d469f-120">Реализация таймера для обновления строки состояния</span><span class="sxs-lookup"><span data-stu-id="d469f-120">To implement the timer to update the status bar</span></span>  
  
1.  <span data-ttu-id="d469f-121">Вставьте следующий код в обработчик событий <xref:System.Windows.Forms.Timer> компонент для обновления панели <xref:System.Windows.Forms.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d469f-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="d469f-122">Теперь вы готовы запустить приложение и увидеть, как работают часы в панели строки состояния.</span><span class="sxs-lookup"><span data-stu-id="d469f-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="d469f-123">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="d469f-123">To test the application</span></span>  
  
1.  <span data-ttu-id="d469f-124">Выполните отладку приложения и нажмите клавишу F5, чтобы его запустить.</span><span class="sxs-lookup"><span data-stu-id="d469f-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="d469f-125">Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d469f-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d469f-126">Часы появятся в строке состояния примерно через 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="d469f-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="d469f-127">Это необходимо для того, чтобы время отображалось максимально точно.</span><span class="sxs-lookup"><span data-stu-id="d469f-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="d469f-128">И наоборот, чтобы часы появились быстрее, можно уменьшить значение <xref:System.Windows.Forms.Timer.Interval%2A> заданному на шаге 7 в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="d469f-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d469f-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d469f-129">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="d469f-130">Практическое руководство. Добавление панелей в элемент управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="d469f-130">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [<span data-ttu-id="d469f-131">Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d469f-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [<span data-ttu-id="d469f-132">Общие сведения об элементе управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="d469f-132">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
