---
title: Запуск процедур в набор интервалов с компонентом таймер
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
ms.openlocfilehash: 52d68a8136551384f67ff6232799600af09f8b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182047"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a>Выполнение операций с заданной периодичностью с помощью компонента Timer в Windows Forms
Иногда может потребоваться создать процедуру, которая выполняется через определенные интервалы времени до окончания цикла или запускается по истечении установленного интервала. Создание такой процедуры возможно благодаря компоненту <xref:System.Windows.Forms.Timer>.  
  
 Этот компонент предназначен для работы в среде Windows Forms. Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
> [!NOTE]
> Существуют некоторые ограничения при использовании компонента <xref:System.Windows.Forms.Timer>. Для получения дополнительной [информации см.](limitations-of-the-timer-component-interval-property.md)  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a>Выполнение процедуры через заданные интервалы времени с помощью компонента Timer  
  
1. Добавьте элемент <xref:System.Windows.Forms.Timer> в форму. В следующем разделе "Пример" показано, как сделать это программным путем. Visual Studio также имеет поддержку для добавления компонентов в форму. Также [см. Как: Добавить элементы управления без пользовательского интерфейса в windows Forms.](how-to-add-controls-without-a-user-interface-to-windows-forms.md)  
  
2. Задайте значение свойства <xref:System.Windows.Forms.Timer.Interval%2A> (в миллисекундах) для таймера. Это свойство определяет, сколько времени пройдет до момента повторного запуска процедуры.  
  
    > [!NOTE]
    > Чем чаще происходит событие таймера, тем выше загрузка процессора при ответе на событие. Это может снизить общую производительность. Не устанавливайте значение интервала меньше, чем необходимо.  
  
3. Напишите соответствующий код в обработчике событий <xref:System.Windows.Forms.Timer.Tick>. Код, написанный в этом событии, будет выполняться с интервалом, указанным в свойстве <xref:System.Windows.Forms.Timer.Interval%2A>.  
  
4. Задайте для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `true`, чтобы запустить таймер. Событие <xref:System.Windows.Forms.Timer.Tick> начнет возникать, запуская процедуру с заданным интервалом.  
  
5. В соответствующее время задайте для свойства <xref:System.Windows.Forms.Timer.Enabled%2A> значение `false`, чтобы остановить повторный запуск процедуры. Установка интервала `0` не приводит к остановке таймера.  
  
## <a name="example"></a>Пример  
 В первом примере кода отслеживается время дня с шагом в одну секунду. В нем используются <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Label> и компонент <xref:System.Windows.Forms.Timer> в форме. Свойству <xref:System.Windows.Forms.Timer.Interval%2A> присваивается значение 1000 (эквивалентно одной секунде). В событии <xref:System.Windows.Forms.Timer.Tick> для подписи метки задается текущее время. При нажатии кнопки свойству <xref:System.Windows.Forms.Timer.Enabled%2A> присваивается значение `false`, после чего таймер перестает обновлять подпись метки. Следующий пример кода требует, чтобы <xref:System.Windows.Forms.Button> у `Button1`вас <xref:System.Windows.Forms.Timer> была `Timer1`форма с <xref:System.Windows.Forms.Label> именем элемента управления, названием элементом управления и названной системой `Label1`управления.  
  
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
  
## <a name="example"></a>Пример  
 Во втором примере кода процедура выполняется каждые 600 миллисекунд до завершения цикла. Следующий пример кода требует, чтобы <xref:System.Windows.Forms.Button> у `Button1`вас <xref:System.Windows.Forms.Timer> была `Timer1`форма с <xref:System.Windows.Forms.Label> именем элемента управления, названием элементом управления и названной системой `Label1`управления.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Timer>
- [Компонент Timer](timer-component-windows-forms.md)
- [Общие сведения о компоненте Timer](timer-component-overview-windows-forms.md)
