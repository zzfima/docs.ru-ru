---
title: "Многопоточность с помощью компонента BackgroundWorker (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3686eb230349876f6cfffd2ad94ed1f547779ab1
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>Пошаговое руководство: Многопоточность с помощью компонента BackgroundWorker (Visual Basic)
В этом пошаговом руководстве демонстрируется создание многопоточного приложения Windows Forms, которое выполняет поиск вхождений слова в текстовом файле. Демонстрируется следующее:  
  
-   Определение класса с методом, который может быть вызван <xref:System.ComponentModel.BackgroundWorker>компонента.</xref:System.ComponentModel.BackgroundWorker>  
  
-   Обработка событий, вызванных <xref:System.ComponentModel.BackgroundWorker>компонента.</xref:System.ComponentModel.BackgroundWorker>  
  
-   Запуск <xref:System.ComponentModel.BackgroundWorker>компонент для выполнения метода.</xref:System.ComponentModel.BackgroundWorker>  
  
-   Реализация `Cancel` кнопку, которая останавливает <xref:System.ComponentModel.BackgroundWorker>компонента.</xref:System.ComponentModel.BackgroundWorker>  
  
### <a name="to-create-the-user-interface"></a>Создание пользовательского интерфейса  
  
1.  Откройте новый проект приложения Windows Forms Visual Basic и создайте форму с именем `Form1`.  
  
2.  Добавьте две кнопки и четыре текстовых поля для `Form1`.  
  
3.  Присвойте имена объектам, как показано в следующей таблице.  
  
    |Объект|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |Первая кнопка|`Name`, `Text`|Запуск, запуск|  
    |Вторая кнопка|`Name`, `Text`|"Отмена", "Отмена"|  
    |Первое текстовое поле|`Name`, `Text`|SourceFile,»»|  
    |Второе текстовое поле|`Name`, `Text`|CompareString,»»|  
    |Третье текстовое поле|`Name`, `Text`|WordsCounted, «0»|  
    |Четвертое текстовое поле|`Name`, `Text`|LinesCounted, «0»|  
  
4.  Добавьте метку рядом с каждым текстовым полем. Задать `Text` свойства для каждой метки, как показано в следующей таблице.  
  
    |Объект|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |Первая метка|`Text`|Исходный файл|  
    |Второй метки|`Text`|Строка для сравнения|  
    |Третья надпись|`Text`|Совпадающих слов|  
    |Четвертая надпись|`Text`|Строки инвентаризации|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>Чтобы создать компонент BackgroundWorker и подписаться на его события  
  
1.  Добавление <xref:System.ComponentModel.BackgroundWorker>из **компоненты** раздел **элементов** к форме.</xref:System.ComponentModel.BackgroundWorker> Он будет отображаться в области компонентов формы.  
  
2.  Задайте следующие свойства для объекта BackgroundWorker1.  
  
    |Свойство|Параметр|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|Да|  
    |`WorkerSupportsCancellation`|Да|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>Чтобы определить метод, который будет выполняться в отдельном потоке  
  
1.  От **проекта** меню, выберите **добавить класс** Чтобы добавить класс в проект. **Add New Item** диалоговое окно.  
  
2.  Выберите **класса** из окна «Шаблоны» и введите `Words.vb` в поле имя.  
  
3.  Нажмите кнопку **Добавить**. `Words` Отображаться класса.  
  
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
  
-   Добавьте следующие обработчики событий главную форму:  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>Чтобы запустить и вызвать новый поток, который выполняется метод WordCount  
  
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
  
2.  Вызов `StartThread` метод `Start` кнопки на форме:  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>Чтобы реализовать кнопку Cancel, которая останавливает поток.  
  
-   Вызов `StopThread` процедуру `Click` обработчик событий для `Cancel` кнопки.  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>Тестирование  
 Теперь можно протестировать приложение, чтобы убедиться в том, что он работает правильно.  
  
#### <a name="to-test-the-application"></a>Тестирование приложения  
  
1.  Нажмите клавишу F5 для запуска приложения.  
  
2.  При отображении формы, введите путь к файлу для файла, необходимо протестировать в `sourceFile` поле. Например предположим, что файл теста именем Test.txt, введите C:\Test.txt.  
  
3.  В втором текстовом поле введите слово или фразу для поиска в текстовом файле приложения.  
  
4.  Нажмите кнопку `Start`. `LinesCounted` Кнопка должна немедленно начать увеличение счета. Приложение отображает сообщение «Завершения подсчета» после ее завершения.  
  
#### <a name="to-test-the-cancel-button"></a>Чтобы проверить работу кнопки Cancel  
  
1.  Нажмите клавишу F5 для запуска приложения и введите файла и имя слово, как описано в предыдущей процедуре. Убедитесь, что выбранный файл достаточно велик, чтобы можно было отменить процедуру до ее завершения.  
  
2.  Щелкните `Start` кнопку, чтобы запустить приложение.  
  
3.  Нажмите кнопку `Cancel`. Приложение должно немедленно прекратить подсчет.  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Это приложение содержит обработка некоторых основных ошибок. Он обнаруживает пустые строки поиска. Эту программу можно сделать более надежным, обработку других ошибок, например превышения максимального числа слов или строк, которые могут быть подсчитаны.  
  
## <a name="see-also"></a>См. также  
 [Работа с потоками (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)   
 [Пошаговое руководство: Разработка простого многопоточного компонента с помощью Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)   
 [Практическое руководство. Подписка и отмена подписки на события](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
