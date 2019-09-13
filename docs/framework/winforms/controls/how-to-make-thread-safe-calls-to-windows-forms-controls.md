---
title: Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms
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
ms.openlocfilehash: 78ad7b16d5220972a61848c0c80cd884afa842d9
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928618"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms

Многопоточность может повысить производительность Windows Forms приложений, но доступ к элементам управления Windows Forms не является потокобезопасным. Многопоточность может представлять код для очень серьезных и сложных ошибок. Два или более потока, управляющих элементом управления, могут привести к нестабильному состоянию и вызвать условия гонки, взаимоблокировки, зависания или фиксации. При реализации многопоточности в приложении следует обязательно вызывать элементы управления между потоками потокобезопасным образом. Дополнительные сведения см. в разделе рекомендации по [управляемому потоку](../../../standard/threading/managed-threading-best-practices.md). 

Существует два способа безопасного вызова элемента управления Windows Forms из потока, который не был создан этим элементом управления. <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> Метод можно использовать для вызова делегата, созданного в основном потоке, который, в свою очередь, вызывает элемент управления. Или можно реализовать <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, который использует модель, управляемую событиями, для разделения работы, выполненной в фоновом потоке, от создания отчетов о результатах. 

## <a name="unsafe-cross-thread-calls"></a>Ненадежные вызовы между потоками

Вызвать элемент управления напрямую из потока, который не создал его, неважно. В следующем фрагменте кода показан незащищенный вызов <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> элемента управления. Обработчик событий создает новый `WriteTextUnsafe` поток, который <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> устанавливает свойство основного потока напрямую. `Button1_Click` 

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

Отладчик Visual Studio обнаруживает эти ненадежные вызовы потоков путем вызова <xref:System.InvalidOperationException> исключения с сообщением, **недопустимой операцией между потоками. Доступ к элементу управления "" осуществляется из потока, отличного от потока, в котором он был создан.** <xref:System.InvalidOperationException> Всегда происходит для ненадежных межпотоковых вызовов во время отладки Visual Studio и может возникнуть во время выполнения приложения. Проблему следует устранить, но можно отключить исключение, задав <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> для `false`свойства значение.

## <a name="safe-cross-thread-calls"></a>Надежные вызовы между потоками 

В следующих примерах кода демонстрируются два способа безопасного вызова элемента управления Windows Forms из потока, который не создал его. 

1. <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> Метод, который вызывает делегат из основного потока для вызова элемента управления. 
2. <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> Компонент, который предоставляет модель, управляемую событиями. 

В обоих примерах фоновый поток заждет одну секунду для имитации работы, выполняемой в этом потоке. 

Вы можете собрать и запустить эти примеры как .NET Framework приложения из командной C# строки или Visual Basic. Дополнительные сведения см. в разделе [Построение из командной строки с помощью csc. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Сборка из командной строки (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

Начиная с .NET Core 3,0, можно также создавать и запускать примеры как приложения Windows .NET Core из папки, в которой имеется .NET Core Windows Forms  *\<имя папки >. csproj* -файл проекта. 

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Пример Использование метода Invoke с делегатом

В следующем примере показан шаблон для обеспечения потокобезопасных вызовов элемента управления Windows Forms. Он запрашивает <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> свойство, которое сравнивает идентификатор потока создаваемого элемента управления с идентификатором вызывающего потока. Если идентификаторы потоков совпадают, он вызывает элемент управления напрямую. Если идентификаторы потоков отличаются, он вызывает <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> метод с делегатом из основного потока, который выполняет фактический вызов элемента управления.

Позволяет задать свойство<xref:System.Windows.Forms.TextBox.Text%2A>элементауправления. <xref:System.Windows.Forms.TextBox> `SafeCallDelegate` `WriteTextSafe` Метод запрашивает <xref:System.Windows.Forms.Control.InvokeRequired%2A>. Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает `true` ,`WriteTextSafe` передает вметод,чтобывыполнитьфактическийвызовэлементауправления.`SafeCallDelegate` <xref:System.Windows.Forms.Control.Invoke%2A> Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает `false`, `WriteTextSafe` задает непосредственно.<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> Обработчик событий создает новый поток и `WriteTextSafe` выполняет метод. `Button1_Click` 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Пример Использование обработчика событий BackgroundWorker

Простой способ реализации многопоточности заключается в <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> использовании компонента, использующего модель, управляемую событиями. Фоновый поток запускает <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> событие, которое не взаимодействует с основным потоком. Главный поток запускает <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> обработчики событий <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> и, которые могут вызывать элементы управления основного потока.

Чтобы сделать потокобезопасный вызов с помощью <xref:System.ComponentModel.BackgroundWorker>, создайте метод в фоновом потоке, чтобы выполнить работу, и привяжите его <xref:System.ComponentModel.BackgroundWorker.DoWork> к событию. Создайте другой метод в основном потоке, чтобы сообщить результаты фоновой работы и привязать его к <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> событию или. <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Чтобы запустить фоновый поток, вызовите <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>. 

В примере <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> с помощью обработчика событий <xref:System.Windows.Forms.TextBox> задается <xref:System.Windows.Forms.TextBox.Text%2A> свойство элемента управления. Пример использования события см. <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> в разделе. <xref:System.ComponentModel.BackgroundWorker> 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>См. также

- <xref:System.ComponentModel.BackgroundWorker>
- [Практическое руководство. Выполнение операции в фоновом режиме](how-to-run-an-operation-in-the-background.md)
- [Практическое руководство. Реализация формы, использующей фоновую операцию](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Разработка пользовательских элементов управления Windows Forms с помощью .NET Framework](developing-custom-windows-forms-controls.md)
