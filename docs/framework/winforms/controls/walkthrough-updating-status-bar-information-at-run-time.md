---
title: "Пошаговое руководство. Обновление строки состояния во время выполнения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96b9c0caeecd4ae381ff2d163e9bf9ff0a89538f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="58543-102">Пошаговое руководство. Обновление строки состояния во время выполнения</span><span class="sxs-lookup"><span data-stu-id="58543-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="58543-103"><xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> заменить элементы управления и добавить функциональные возможности в <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления можно сохранить для обратной совместимости и использования в будущем, если вы Выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="58543-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="58543-104">Часто программа требует динамического обновления содержимого панелей строки состояния в среде выполнения с учетом изменений в состоянии приложения или других взаимодействий с пользователем.</span><span class="sxs-lookup"><span data-stu-id="58543-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="58543-105">Это обычный способ сообщить пользователям о том, что CAPS LOCK, NUM LOCK или SCROLL LOCK включен, или сообщить ему дату или время в удобном формате.</span><span class="sxs-lookup"><span data-stu-id="58543-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="58543-106">В следующем примере используется экземпляр <xref:System.Windows.Forms.StatusBarPanel> класса для размещения часов.</span><span class="sxs-lookup"><span data-stu-id="58543-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="58543-107">Получение строки состояния, готовой для обновления</span><span class="sxs-lookup"><span data-stu-id="58543-107">To get the status bar ready for updating</span></span>  
  
1.  <span data-ttu-id="58543-108">Создание новой формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="58543-108">Create a new Windows form.</span></span>  
  
2.  <span data-ttu-id="58543-109">Добавьте элемент управления <xref:System.Windows.Forms.StatusBar> в форму.</span><span class="sxs-lookup"><span data-stu-id="58543-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="58543-110">Дополнительные сведения см. в разделе [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="58543-110">For details, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="58543-111">Добавьте панель строки состояния для вашей <xref:System.Windows.Forms.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="58543-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="58543-112">Дополнительные сведения см. в разделе [Практическое руководство. Добавление панелей в элемент управления StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="58543-112">For details, see [How to: Add Panels to a StatusBar Control](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4.  <span data-ttu-id="58543-113">Для <xref:System.Windows.Forms.StatusBar> вы добавили в форму элемент управления устанавливать <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="58543-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="58543-114">Добавить форму Windows Forms <xref:System.Windows.Forms.Timer> в форму компонент.</span><span class="sxs-lookup"><span data-stu-id="58543-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58543-115">Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> компонент предназначен для работы в среде Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="58543-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="58543-116">Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="58543-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
6.  <span data-ttu-id="58543-117">Задайте для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="58543-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7.  <span data-ttu-id="58543-118">Задать <xref:System.Windows.Forms.Timer.Interval%2A> свойство <xref:System.Windows.Forms.Timer> 30 000.</span><span class="sxs-lookup"><span data-stu-id="58543-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58543-119"><xref:System.Windows.Forms.Timer.Interval%2A> Свойство <xref:System.Windows.Forms.Timer> набор компонентов до 30 секунд (30 000 миллисекунд), чтобы отражались точное время отображение.</span><span class="sxs-lookup"><span data-stu-id="58543-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="58543-120">Реализация таймера для обновления строки состояния</span><span class="sxs-lookup"><span data-stu-id="58543-120">To implement the timer to update the status bar</span></span>  
  
1.  <span data-ttu-id="58543-121">Вставьте следующий код в обработчик событий <xref:System.Windows.Forms.Timer> компонента для обновления панели <xref:System.Windows.Forms.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="58543-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
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
  
     <span data-ttu-id="58543-122">Теперь вы готовы запустить приложение и увидеть, как работают часы в панели строки состояния.</span><span class="sxs-lookup"><span data-stu-id="58543-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="58543-123">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="58543-123">To test the application</span></span>  
  
1.  <span data-ttu-id="58543-124">Выполните отладку приложения и нажмите клавишу F5, чтобы его запустить.</span><span class="sxs-lookup"><span data-stu-id="58543-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="58543-125">Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="58543-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58543-126">Часы появятся в строке состояния примерно через 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="58543-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="58543-127">Это необходимо для того, чтобы время отображалось максимально точно.</span><span class="sxs-lookup"><span data-stu-id="58543-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="58543-128">С другой стороны, чтобы часы появились раньше, можно уменьшить значение <xref:System.Windows.Forms.Timer.Interval%2A> свойство, заданное в шаге 7 в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="58543-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58543-129">См. также</span><span class="sxs-lookup"><span data-stu-id="58543-129">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="58543-130">Практическое руководство. Добавление панелей в элемент управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="58543-130">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [<span data-ttu-id="58543-131">Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58543-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [<span data-ttu-id="58543-132">Общие сведения об элементе управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="58543-132">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
