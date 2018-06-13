---
title: Многопоточность с помощью компонента BackgroundWorker (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
ms.openlocfilehash: 07700aa526866729f1ba1a8d846f22ce333c356d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654295"
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>Пошаговое руководство: Многопоточность с помощью компонента BackgroundWorker (Visual Basic)
В этом пошаговом руководстве описывается создание многопоточного приложения Windows Forms, которое выполняет поиск заданного слова в текстовом файле. В нем демонстрируются:  
  
-   Определение класса с методом, который может вызываться компонентом <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Обработка событий, вызываемых компонентом <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Запуск компонента <xref:System.ComponentModel.BackgroundWorker> для выполнения метода.  
  
-   Реализация кнопки `Cancel`, которая останавливает компонент <xref:System.ComponentModel.BackgroundWorker>.  
  
### <a name="to-create-the-user-interface"></a>Создание пользовательского интерфейса  
  
1.  Откройте новый проект приложения Windows Forms Visual Basic и создайте форму с именем `Form1`.  
  
2.  Добавьте две кнопки и четыре текстовых поля в `Form1`.  
  
3.  Присвойте им имена, как показано в следующей таблице.  
  
    |Объект|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |Первая кнопка|`Name`, `Text`|Пуск, Пуск|  
    |Вторая кнопка|`Name`, `Text`|Отмена, Отмена|  
    |Первое текстовое поле|`Name`, `Text`|SourceFile, ""|  
    |Второе текстовое поле|`Name`, `Text`|CompareString, ""|  
    |Третье текстовое поле|`Name`, `Text`|WordsCounted, "0"|  
    |Четвертое текстовое поле|`Name`, `Text`|LinesCounted, "0"|  
  
4.  Добавьте метку рядом с каждым текстовым полем. Задайте свойство `Text` для каждой метки, как показано в следующей таблице.  
  
    |Object|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |Первая метка|`Text`|Исходный файл|  
    |Вторая метка|`Text`|Сравнение строк|  
    |Третья метка|`Text`|Совпадающие слова|  
    |Четвертая метка|`Text`|Число строк|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>Создание компонента BackgroundWorker и подписка на его события  
  
1.  Добавьте в форму компонент <xref:System.ComponentModel.BackgroundWorker> из раздела **Компоненты** в **панели элементов**. Он будет отображаться в области компонентов формы.  
  
2.  Задайте следующие свойства для объекта BackgroundWorker1.  
  
    |Свойство.|Параметр|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|Да|  
    |`WorkerSupportsCancellation`|Да|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>Определение метода, который будет выполняться в отдельном потоке  
  
1.  В меню **Проект** меню выберите пункт **Добавить класс**, чтобы добавить класс в проект. Откроется диалоговое окно **Добавление нового элемента**.  
  
2.  Выберите **Класс** в окне "Шаблоны" и введите `Words.vb` в поле имени.  
  
3.  Нажмите кнопку **Добавить**. Отобразится класс `Words`.  
  
4.  Добавьте следующий код в класс `Words` :  
  
    ```vb  
    Public Class Words  
        ' Object to store the current state, for passing to the caller.  
        Public Class CurrentState  
            Public LinesCounted As Integer  
            Public WordsMatched As Integer  
        End Class  
  
        Public SourceFile As String  
        Public CompareString As String  
        Private WordCount As Integer = 0  
        Private LinesCounted As Integer = 0  
  
        Public Sub CountWords(  
            ByVal worker As System.ComponentModel.BackgroundWorker,  
            ByVal e As System.ComponentModel.DoWorkEventArgs  
        )  
            ' Initialize the variables.  
            Dim state As New CurrentState  
            Dim line = ""  
            Dim elapsedTime = 20  
            Dim lastReportDateTime = Now  
  
            If CompareString Is Nothing OrElse  
               CompareString = System.String.Empty Then  
  
               Throw New Exception("CompareString not specified.")  
            End If  
  
            Using myStream As New System.IO.StreamReader(SourceFile)  
  
                ' Process lines while there are lines remaining in the file.  
                Do While Not myStream.EndOfStream  
                    If worker.CancellationPending Then  
                        e.Cancel = True  
                        Exit Do  
                    Else  
                        line = myStream.ReadLine  
                        WordCount += CountInString(line, CompareString)  
                        LinesCounted += 1  
  
                        ' Raise an event so the form can monitor progress.  
                        If Now > lastReportDateTime.AddMilliseconds(elapsedTime) Then  
                            state.LinesCounted = LinesCounted  
                            state.WordsMatched = WordCount  
                            worker.ReportProgress(0, state)  
                            lastReportDateTime = Now  
                        End If  
  
                        ' Uncomment for testing.  
                        'System.Threading.Thread.Sleep(5)  
                    End If  
                Loop  
  
                ' Report the final count values.  
                state.LinesCounted = LinesCounted  
                state.WordsMatched = WordCount  
                worker.ReportProgress(0, state)  
            End Using  
        End Sub  
  
        Private Function CountInString(  
            ByVal SourceString As String,  
            ByVal CompareString As String  
        ) As Integer  
            ' This function counts the number of times  
            ' a word is found in a line.  
            If SourceString Is Nothing Then  
                Return 0  
            End If  
  
            Dim EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString)  
  
            ' To count all occurrences of the string, even within words, remove  
            ' both instances of "\b".  
            Dim regex As New System.Text.RegularExpressions.Regex(  
                "\b" + EscapedCompareString + "\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase)  
  
            Dim matches As System.Text.RegularExpressions.MatchCollection  
            matches = regex.Matches(SourceString)  
            Return matches.Count  
        End Function  
    End Class  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a>Обработка событий из потока  
  
-   Добавьте в основную форму следующие обработчики событий:  
  
    ```vb  
    Private Sub BackgroundWorker1_RunWorkerCompleted(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
      ) Handles BackgroundWorker1.RunWorkerCompleted  
  
        ' This event handler is called when the background thread finishes.  
        ' This method runs on the main thread.  
        If e.Error IsNot Nothing Then  
            MessageBox.Show("Error: " & e.Error.Message)  
        ElseIf e.Cancelled Then  
            MessageBox.Show("Word counting canceled.")  
        Else  
            MessageBox.Show("Finished counting words.")  
        End If  
    End Sub  
  
    Private Sub BackgroundWorker1_ProgressChanged(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.ProgressChangedEventArgs  
      ) Handles BackgroundWorker1.ProgressChanged  
  
        ' This method runs on the main thread.  
        Dim state As Words.CurrentState =   
            CType(e.UserState, Words.CurrentState)  
        Me.LinesCounted.Text = state.LinesCounted.ToString  
        Me.WordsCounted.Text = state.WordsMatched.ToString  
    End Sub  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>Запуск и вызов нового потока, выполняющего метод WordCount  
  
1.  Добавьте в программу следующие процедуры:  
  
    ```vb  
    Private Sub BackgroundWorker1_DoWork(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.DoWorkEventArgs  
      ) Handles BackgroundWorker1.DoWork  
  
        ' This event handler is where the actual work is done.  
        ' This method runs on the background thread.  
  
        ' Get the BackgroundWorker object that raised this event.  
        Dim worker As System.ComponentModel.BackgroundWorker  
        worker = CType(sender, System.ComponentModel.BackgroundWorker)  
  
        ' Get the Words object and call the main method.  
        Dim WC As Words = CType(e.Argument, Words)  
        WC.CountWords(worker, e)  
    End Sub  
  
    Sub StartThread()  
        ' This method runs on the main thread.  
        Me.WordsCounted.Text = "0"  
  
        ' Initialize the object that the background worker calls.  
        Dim WC As New Words  
        WC.CompareString = Me.CompareString.Text  
        WC.SourceFile = Me.SourceFile.Text  
  
        ' Start the asynchronous operation.  
        BackgroundWorker1.RunWorkerAsync(WC)  
    End Sub  
    ```  
  
2.  Вызовите метод `StartThread` из кнопки `Start` в вашей форме:  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>Реализация кнопки "Отмена", останавливающей поток  
  
-   Вызовите процедуру `StopThread` из обработчика событий `Click` для кнопки `Cancel`.  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>Тестирование  
 Теперь вы можете протестировать приложение и убедиться в том, что оно работает правильно.  
  
#### <a name="to-test-the-application"></a>Тестирование приложения  
  
1.  Нажмите клавишу F5 для запуска приложения.  
  
2.  В открывшейся форме введите путь к файлу, который нужно протестировать, в поле `sourceFile`. Например, если тестовый файл называется Test.txt, введите C:\Test.txt.  
  
3.  Во втором текстовом поле введите слово или фразу для поиска приложения в текстовом файле.  
  
4.  Нажмите кнопку `Start`. Значение на кнопке `LinesCounted` начнет увеличиваться незамедлительно. По завершении в приложении отобразится сообщение "Подсчет завершен".  
  
#### <a name="to-test-the-cancel-button"></a>Тестирование кнопки "Отмена"  
  
1.  Нажмите клавишу F5 для запуска приложения, а затем введите имя файла и слово для поиска, как описано в предыдущей процедуре. Убедитесь, что выбранный файл достаточно большой для того, чтобы процедуру можно было отменить до ее завершения.  
  
2.  Нажмите кнопку `Start`, чтобы запустить приложение.  
  
3.  Нажмите кнопку `Cancel`. Приложение должно незамедлительно прекратить подсчет.  
  
## <a name="next-steps"></a>Следующие шаги  
 Это приложение включает обработку некоторых основных ошибок. Оно выявляет пустые строки поиска. Программу можно сделать более надежной за счет обработки других ошибок, например, превышения максимального числа слов или строк, которые могут быть подсчитаны.  
  
## <a name="see-also"></a>См. также  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) (Работа с потоками (Visual Basic))  
 [Пошаговое руководство: Разработка простого многопоточного компонента с помощью Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [Практическое руководство. Подписка и отмена подписки на события](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
