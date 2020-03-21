---
title: Сделать поток-безопасные вызовы для элементов управления
ms.date: 02/19/2019
dev_langs:
- csharp
- vb
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: 365b1acb693b9ff2be603a3e659ed8d846a7696a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142008"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Как: Делать вызовы для безопасности потоков на элементы управления Windows Forms

Многопоточность может повысить производительность приложений Windows Forms, но доступ к элементам управления Windows Forms по своей сути не является безопасным для потоков. Многопоточность может подвергнуть код очень серьезным и сложным ошибкам. Два или более потоков, манипулирующих управлением, могут привести управление к несогласованному состоянию и привести к расовым условиям, взаимоблокировкам и замораживаниям или зависаниям. Если вы реализуете многопоточность в приложении, обязательно вызовите элементы управления поперечным потоком безопасным способом. Для получения дополнительной информации [см.](../../../standard/threading/managed-threading-best-practices.md)

Существует два способа безопасного вызова управления формами Windows из потока, который не создал этот элемент управления. Метод можно <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> использовать для вызова делегата, созданного в основном потоке, который, в свою очередь, вызывает элемент управления. Или можно реализовать <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>модель, управляемую событиями, чтобы отделить работу, проделанную в фоновом потоке, от отчетности о результатах.

## <a name="unsafe-cross-thread-calls"></a>Небезопасные перекрестные вызовы

Небезопасно вызывать элемент управления непосредственно из потока, который его не создал. Следующий фрагмент кода иллюстрирует небезопасный вызов <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> в элемент управления. Обработчик `Button1_Click` событий `WriteTextUnsafe` создает новый поток, который <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> устанавливает свойство основного потока напрямую.

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

Отладка Visual Studio обнаруживает эти небезопасные <xref:System.InvalidOperationException> вызовы потока, повышая с сообщением, **Кросс-поток операции не действительны. Элемент управления "" доступ из потока, кроме потока, на** который он был создан. Всегда <xref:System.InvalidOperationException> происходит для небезопасных перекрестных потоков вызовов во время отладки Visual Studio, и может произойти во время выполнения приложения. Вы должны исправить проблему, но вы можете отключить <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> исключение, `false`установив свойство.

## <a name="safe-cross-thread-calls"></a>Безопасные перекрестные вызовы

Следующие примеры кода демонстрируют два способа безопасного вызова управления формами Windows из потока, который не создал его:

1. Метод, <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> который вызывает делегата из основного потока для вызова элемента управления.
2. Компонент, <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> который предлагает модель, управляемую событиями.

В обоих примерах фоновый поток спит в течение одной секунды, чтобы имитировать работу, проделанную в этом потоке.

Вы можете создавать и запускать эти примеры в виде приложений .NET Framework из командной строки C- или Visual Basic. Для получения дополнительной информации см. [здание Командной строки с csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Build из командной строки (Visual Basic).](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)

Начиная с .NET Core 3.0, вы также можете создавать и запускать примеры приложений Windows .NET Core из папки с названием папки .NET Core Windows Forms * \<>.csproj* project file.

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Пример: Используйте метод Invoke с делегатом

В следующем примере показан шаблон для обеспечения безопасных вызовов потоков для управления формами Windows. Он запрашивает <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> свойство, которое сравнивает идентификатор потока элемента управления с идентификатором вызывающего потока. Если иикты потока одинаковы, он вызывает элемент управления напрямую. Если иикты потока отличаются, <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> он вызывает метод с делегатом из основного потока, что делает фактический вызов к управлению.

Позволяет `SafeCallDelegate` установить <xref:System.Windows.Forms.TextBox> свойство <xref:System.Windows.Forms.TextBox.Text%2A> элемента управления. Запросы `WriteTextSafe` метода <xref:System.Windows.Forms.Control.InvokeRequired%2A>. При <xref:System.Windows.Forms.Control.InvokeRequired%2A> `true` `WriteTextSafe` возврате, `SafeCallDelegate` передает <xref:System.Windows.Forms.Control.Invoke%2A> метод, чтобы сделать фактический вызов к элементу управления. Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> `false` `WriteTextSafe` возвращается, <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> устанавливает непосредственно. Обработчик `Button1_Click` событий создает новый `WriteTextSafe` поток и запускает метод.

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Пример: Используйте обработчик событий BackgroundWorker

Простой способ реализации многопоточности — это <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> компонент, в котором используется модель, управляемая событиями. Фоновый поток <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> запускает событие, которое не взаимодействует с основным потоком. Основной поток <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> запускает <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> обработчики событий, которые могут вызывать элементы управления основного потока.

Чтобы сделать вызов с <xref:System.ComponentModel.BackgroundWorker>безопасностью потока с помощью, создайте метод в <xref:System.ComponentModel.BackgroundWorker.DoWork> фоновом потоке для сработки и свяжите его с событием. Создайте другой метод в основном потоке, чтобы сообщить о <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> результатах фоновой работы и связать его с событием или событием. Чтобы запустить фоновый <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>поток, позвоните .

В примере <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> используется обработчик событий для установки <xref:System.Windows.Forms.TextBox> свойства элемента <xref:System.Windows.Forms.TextBox.Text%2A> управления. Например, с <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> помощью <xref:System.ComponentModel.BackgroundWorker>события см.

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>См. также раздел

- <xref:System.ComponentModel.BackgroundWorker>
- [Как: Выполнить операцию в фоновом режиме](how-to-run-an-operation-in-the-background.md)
- [Как: Реализация формы, используюейейейую фоновая операция](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Разработка пользовательских элементов управления формами Windows с помощью рамочной программы .NET](developing-custom-windows-forms-controls.md)
