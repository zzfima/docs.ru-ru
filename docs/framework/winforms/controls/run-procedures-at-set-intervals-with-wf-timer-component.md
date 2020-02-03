---
title: Выполнение процедур через заданные интервалы с помощью компонента Timer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
ms.openlocfilehash: dcc88beee947e2a83b426dcd2f3fd9d70c20fb67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743112"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a><span data-ttu-id="3652d-102">Выполнение операций с заданной периодичностью с помощью компонента Timer в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3652d-102">How to: Run Procedures at Set Intervals with the Windows Forms Timer Component</span></span>
<span data-ttu-id="3652d-103">Иногда может потребоваться создать процедуру, которая выполняется через определенные интервалы времени до окончания цикла или запускается по истечении установленного интервала.</span><span class="sxs-lookup"><span data-stu-id="3652d-103">You might sometimes want to create a procedure that runs at specific time intervals until a loop has finished or that runs when a set time interval has elapsed.</span></span> <span data-ttu-id="3652d-104">Создание такой процедуры возможно благодаря компоненту <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="3652d-104">The <xref:System.Windows.Forms.Timer> component makes such a procedure possible.</span></span>  
  
 <span data-ttu-id="3652d-105">Этот компонент предназначен для работы в среде Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3652d-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="3652d-106">Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="3652d-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3652d-107">Существуют некоторые ограничения при использовании компонента <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="3652d-107">There are some limitations when using the <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="3652d-108">Дополнительные сведения см. [в разделе ограничения свойства Interval компонента таймера Windows Forms](limitations-of-the-timer-component-interval-property.md).</span><span class="sxs-lookup"><span data-stu-id="3652d-108">For more information, see [Limitations of the Windows Forms Timer Component's Interval Property](limitations-of-the-timer-component-interval-property.md).</span></span>  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a><span data-ttu-id="3652d-109">Выполнение процедуры через заданные интервалы времени с помощью компонента Timer</span><span class="sxs-lookup"><span data-stu-id="3652d-109">To run a procedure at set intervals with the Timer component</span></span>  
  
1. <span data-ttu-id="3652d-110">Добавьте элемент <xref:System.Windows.Forms.Timer> в форму.</span><span class="sxs-lookup"><span data-stu-id="3652d-110">Add a <xref:System.Windows.Forms.Timer> to your form.</span></span> <span data-ttu-id="3652d-111">В следующем разделе "Пример" показано, как сделать это программным путем.</span><span class="sxs-lookup"><span data-stu-id="3652d-111">See the following Example section for an illustration of how to do this programmatically.</span></span> <span data-ttu-id="3652d-112">Visual Studio также поддерживает добавление компонентов в форму.</span><span class="sxs-lookup"><span data-stu-id="3652d-112">Visual Studio also has support for adding components to a form.</span></span> <span data-ttu-id="3652d-113">См. также [руководство. Добавление элементов управления без пользовательского интерфейса в Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3652d-113">Also see [How to: Add Controls Without a User Interface to Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="3652d-114">Задайте значение свойства <xref:System.Windows.Forms.Timer.Interval%2A> (в миллисекундах) для таймера.</span><span class="sxs-lookup"><span data-stu-id="3652d-114">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property (in milliseconds) for the timer.</span></span> <span data-ttu-id="3652d-115">Это свойство определяет, сколько времени пройдет до момента повторного запуска процедуры.</span><span class="sxs-lookup"><span data-stu-id="3652d-115">This property determines how much time will pass before the procedure is run again.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3652d-116">Чем чаще происходит событие таймера, тем выше загрузка процессора при ответе на событие.</span><span class="sxs-lookup"><span data-stu-id="3652d-116">The more often a timer event occurs, the more processor time is used in responding to the event.</span></span> <span data-ttu-id="3652d-117">Это может снизить общую производительность.</span><span class="sxs-lookup"><span data-stu-id="3652d-117">This can slow down overall performance.</span></span> <span data-ttu-id="3652d-118">Не устанавливайте значение интервала меньше, чем необходимо.</span><span class="sxs-lookup"><span data-stu-id="3652d-118">Do not set a smaller interval than you need.</span></span>  
  
3. <span data-ttu-id="3652d-119">Напишите соответствующий код в обработчике событий <xref:System.Windows.Forms.Timer.Tick>.</span><span class="sxs-lookup"><span data-stu-id="3652d-119">Write appropriate code in the <xref:System.Windows.Forms.Timer.Tick> event handler.</span></span> <span data-ttu-id="3652d-120">Код, написанный в этом событии, будет выполняться с интервалом, указанным в свойстве <xref:System.Windows.Forms.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="3652d-120">The code you write in this event will run at the interval specified in the <xref:System.Windows.Forms.Timer.Interval%2A> property.</span></span>  
  
4. <span data-ttu-id="3652d-121">Задайте для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `true`, чтобы запустить таймер.</span><span class="sxs-lookup"><span data-stu-id="3652d-121">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true` to start the timer.</span></span> <span data-ttu-id="3652d-122">Событие <xref:System.Windows.Forms.Timer.Tick> начнет возникать, запуская процедуру с заданным интервалом.</span><span class="sxs-lookup"><span data-stu-id="3652d-122">The <xref:System.Windows.Forms.Timer.Tick> event will begin to occur, running your procedure at the set interval.</span></span>  
  
5. <span data-ttu-id="3652d-123">В соответствующее время задайте для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `false`, чтобы остановить повторный запуск процедуры.</span><span class="sxs-lookup"><span data-stu-id="3652d-123">At the appropriate time, set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `false` to stop the procedure from running again.</span></span> <span data-ttu-id="3652d-124">Установка интервала, в `0`, не приведет к сбою таймера.</span><span class="sxs-lookup"><span data-stu-id="3652d-124">Setting the interval to `0` does not cause the timer to stop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3652d-125">Пример</span><span class="sxs-lookup"><span data-stu-id="3652d-125">Example</span></span>  
 <span data-ttu-id="3652d-126">В первом примере кода отслеживается время дня с шагом в одну секунду.</span><span class="sxs-lookup"><span data-stu-id="3652d-126">This first code example tracks the time of day in one-second increments.</span></span> <span data-ttu-id="3652d-127">В нем используются <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Label> и компонент <xref:System.Windows.Forms.Timer> в форме.</span><span class="sxs-lookup"><span data-stu-id="3652d-127">It uses a <xref:System.Windows.Forms.Button>, a <xref:System.Windows.Forms.Label>, and a <xref:System.Windows.Forms.Timer> component on a form.</span></span> <span data-ttu-id="3652d-128">Свойству <xref:System.Windows.Forms.Timer.Interval%2A> присваивается значение 1000 (эквивалентно одной секунде).</span><span class="sxs-lookup"><span data-stu-id="3652d-128">The <xref:System.Windows.Forms.Timer.Interval%2A> property is set to 1000 (equal to one second).</span></span> <span data-ttu-id="3652d-129">В событии <xref:System.Windows.Forms.Timer.Tick> для подписи метки задается текущее время.</span><span class="sxs-lookup"><span data-stu-id="3652d-129">In the <xref:System.Windows.Forms.Timer.Tick> event, the label's caption is set to the current time.</span></span> <span data-ttu-id="3652d-130">При нажатии кнопки свойству <xref:System.Windows.Forms.Timer.Enabled%2A> присваивается значение `false`, после чего таймер перестает обновлять подпись метки.</span><span class="sxs-lookup"><span data-stu-id="3652d-130">When the button is clicked, the <xref:System.Windows.Forms.Timer.Enabled%2A> property is set to `false`, stopping the timer from updating the label's caption.</span></span> <span data-ttu-id="3652d-131">В следующем примере кода требуется форма с элементом управления <xref:System.Windows.Forms.Button> с именем `Button1`, <xref:System.Windows.Forms.Timer>ным элементом управления с именем `Timer1`и элементом управления <xref:System.Windows.Forms.Label> с именем `Label1`.</span><span class="sxs-lookup"><span data-stu-id="3652d-131">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)     
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,    
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,   
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a><span data-ttu-id="3652d-132">Пример</span><span class="sxs-lookup"><span data-stu-id="3652d-132">Example</span></span>  
 <span data-ttu-id="3652d-133">Во втором примере кода процедура выполняется каждые 600 миллисекунд до завершения цикла.</span><span class="sxs-lookup"><span data-stu-id="3652d-133">This second code example runs a procedure every 600 milliseconds until a loop has finished.</span></span> <span data-ttu-id="3652d-134">В следующем примере кода требуется форма с элементом управления <xref:System.Windows.Forms.Button> с именем `Button1`, <xref:System.Windows.Forms.Timer>ным элементом управления с именем `Timer1`и элементом управления <xref:System.Windows.Forms.Label> с именем `Label1`.</span><span class="sxs-lookup"><span data-stu-id="3652d-134">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)     
{  
   if (counter >= 10)   
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)   
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="3652d-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3652d-135">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="3652d-136">Компонент Timer</span><span class="sxs-lookup"><span data-stu-id="3652d-136">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="3652d-137">Общие сведения о компоненте Timer</span><span class="sxs-lookup"><span data-stu-id="3652d-137">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
