---
title: Сделать потокобезопасные вызовы элементов управления
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
ms.openlocfilehash: 101457ab2a02b8de49d06c354ca307e07b690ba2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736160"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Пошаговое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms

Многопоточность может повысить производительность Windows Forms приложений, но доступ к элементам управления Windows Forms не является потокобезопасным. Многопоточность может представлять код для очень серьезных и сложных ошибок. Два или более потока, управляющих элементом управления, могут привести к нестабильному состоянию и вызвать условия гонки, взаимоблокировки, зависания или фиксации. При реализации многопоточности в приложении следует обязательно вызывать элементы управления между потоками потокобезопасным образом. Дополнительные сведения см. в разделе рекомендации по [управляемому потоку](../../../standard/threading/managed-threading-best-practices.md). 

Существует два способа безопасного вызова элемента управления Windows Forms из потока, который не был создан этим элементом управления. Можно использовать метод <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> для вызова делегата, созданного в основном потоке, который, в свою очередь, вызывает элемент управления. Или можно реализовать <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, который использует модель, управляемую событиями, для разделения работы, выполненной в фоновом потоке, от создания отчетов по результатам. 

## <a name="unsafe-cross-thread-calls"></a>Ненадежные вызовы между потоками

Вызвать элемент управления напрямую из потока, который не создал его, неважно. В следующем фрагменте кода показан незащищенный вызов элемента управления <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>. Обработчик событий `Button1_Click` создает новый поток `WriteTextUnsafe`, который непосредственно задает свойство <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> основного потока. 

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

Отладчик Visual Studio обнаруживает эти ненадежные вызовы потоков, вызывая <xref:System.InvalidOperationException> с сообщением, **операция между потоками недопустима. Доступ к элементу управления "" осуществляется из потока, отличного от потока, в котором он был создан.** <xref:System.InvalidOperationException> всегда происходит для ненадежных межпотоковых вызовов во время отладки Visual Studio и может произойти во время выполнения приложения. Проблему следует устранить, но можно отключить исключение, задав для свойства <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> значение `false`.

## <a name="safe-cross-thread-calls"></a>Надежные вызовы между потоками 

В следующих примерах кода демонстрируются два способа безопасного вызова элемента управления Windows Forms из потока, который не создал его. 

1. Метод <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>, который вызывает делегат из основного потока для вызова элемента управления. 
2. Компонент <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, который предоставляет модель, управляемую событиями. 

В обоих примерах фоновый поток заждет одну секунду для имитации работы, выполняемой в этом потоке. 

Вы можете собрать и запустить эти примеры как .NET Framework приложения из командной C# строки или Visual Basic. Дополнительные сведения см. в разделе [Построение из командной строки с помощью csc. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Сборка из командной строки (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

Начиная с .NET Core 3,0, можно также создавать и запускать примеры как приложения Windows .NET Core из папки, в которой имеется .NET Core Windows Forms *\<имя папки >. csproj* . 

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Пример. использование метода Invoke с делегатом

В следующем примере показан шаблон для обеспечения потокобезопасных вызовов элемента управления Windows Forms. Он запрашивает свойство <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName>, которое сравнивает идентификатор потока создаваемого элемента управления с ИДЕНТИФИКАТОРом вызывающего потока. Если идентификаторы потоков совпадают, он вызывает элемент управления напрямую. Если идентификаторы потоков отличаются, вызывается метод <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> с делегатом из основного потока, который выполняет фактический вызов элемента управления.

`SafeCallDelegate` позволяет задать свойство <xref:System.Windows.Forms.TextBox.Text%2A> элемента управления <xref:System.Windows.Forms.TextBox>. Метод `WriteTextSafe` запрашивает <xref:System.Windows.Forms.Control.InvokeRequired%2A>. Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает `true`, `WriteTextSafe` передает `SafeCallDelegate` методу <xref:System.Windows.Forms.Control.Invoke%2A> для выполнения фактического вызова элемента управления. Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает `false`, `WriteTextSafe` непосредственно задает <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>. Обработчик событий `Button1_Click` создает новый поток и выполняет метод `WriteTextSafe`. 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Пример. использование обработчика событий BackgroundWorker

Простой способ реализации многопоточности заключается в использовании компонента <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, который использует модель, управляемую событиями. Фоновый поток запускает событие <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>, которое не взаимодействует с основным потоком. Главный поток запускает <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> обработчики событий, которые могут вызывать элементы управления основного потока.

Чтобы сделать потокобезопасный вызов с помощью <xref:System.ComponentModel.BackgroundWorker>, создайте метод в фоновом потоке, чтобы выполнить работу, и привяжите его к событию <xref:System.ComponentModel.BackgroundWorker.DoWork>. Создайте другой метод в основном потоке, чтобы сообщить результаты фоновой работы и привязать его к событию <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> или <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>. Чтобы запустить фоновый поток, вызовите <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>. 

В примере используется обработчик событий <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> для установки свойства <xref:System.Windows.Forms.TextBox.Text%2A> элемента управления <xref:System.Windows.Forms.TextBox>. Пример использования события <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> см. в разделе <xref:System.ComponentModel.BackgroundWorker>. 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>См. также:

- <xref:System.ComponentModel.BackgroundWorker>
- [Как выполнить операцию в фоновом режиме](how-to-run-an-operation-in-the-background.md)
- [Как реализовать форму, использующую фоновую операцию](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Разработка пользовательских элементов управления Windows Forms с помощью .NET Framework](developing-custom-windows-forms-controls.md)
