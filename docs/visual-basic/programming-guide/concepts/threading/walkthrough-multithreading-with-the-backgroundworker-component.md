---
title: "Многопоточность с помощью компонента BackgroundWorker (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb0734b4bbf3f8bf5b27305754829f1a9f29f42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="b1881-102">Пошаговое руководство: Многопоточность с помощью компонента BackgroundWorker (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1881-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="b1881-103">В этом пошаговом руководстве описывается создание многопоточного приложения Windows Forms, которое выполняет поиск заданного слова в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="b1881-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="b1881-104">В нем демонстрируются:</span><span class="sxs-lookup"><span data-stu-id="b1881-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="b1881-105">Определение класса с методом, который может вызываться компонентом <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="b1881-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="b1881-106">Обработка событий, вызываемых компонентом <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="b1881-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="b1881-107">Запуск компонента <xref:System.ComponentModel.BackgroundWorker> для выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="b1881-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="b1881-108">Реализация кнопки `Cancel`, которая останавливает компонент <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="b1881-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="b1881-109">Создание пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="b1881-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="b1881-110">Откройте новый проект приложения Windows Forms Visual Basic и создайте форму с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="b1881-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="b1881-111">Добавьте две кнопки и четыре текстовых поля в `Form1`.</span><span class="sxs-lookup"><span data-stu-id="b1881-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="b1881-112">Присвойте им имена, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b1881-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="b1881-113">Объект</span><span class="sxs-lookup"><span data-stu-id="b1881-113">Object</span></span>|<span data-ttu-id="b1881-114">Свойство</span><span class="sxs-lookup"><span data-stu-id="b1881-114">Property</span></span>|<span data-ttu-id="b1881-115">Параметр</span><span class="sxs-lookup"><span data-stu-id="b1881-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="b1881-116">Первая кнопка</span><span class="sxs-lookup"><span data-stu-id="b1881-116">First button</span></span>|<span data-ttu-id="b1881-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b1881-117">`Name`, `Text`</span></span>|<span data-ttu-id="b1881-118">Пуск, Пуск</span><span class="sxs-lookup"><span data-stu-id="b1881-118">Start, Start</span></span>|  
    |<span data-ttu-id="b1881-119">Вторая кнопка</span><span class="sxs-lookup"><span data-stu-id="b1881-119">Second button</span></span>|<span data-ttu-id="b1881-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b1881-120">`Name`, `Text`</span></span>|<span data-ttu-id="b1881-121">Отмена, Отмена</span><span class="sxs-lookup"><span data-stu-id="b1881-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="b1881-122">Первое текстовое поле</span><span class="sxs-lookup"><span data-stu-id="b1881-122">First text box</span></span>|<span data-ttu-id="b1881-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b1881-123">`Name`, `Text`</span></span>|<span data-ttu-id="b1881-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="b1881-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="b1881-125">Второе текстовое поле</span><span class="sxs-lookup"><span data-stu-id="b1881-125">Second text box</span></span>|<span data-ttu-id="b1881-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b1881-126">`Name`, `Text`</span></span>|<span data-ttu-id="b1881-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="b1881-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="b1881-128">Третье текстовое поле</span><span class="sxs-lookup"><span data-stu-id="b1881-128">Third text box</span></span>|<span data-ttu-id="b1881-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b1881-129">`Name`, `Text`</span></span>|<span data-ttu-id="b1881-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="b1881-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="b1881-131">Четвертое текстовое поле</span><span class="sxs-lookup"><span data-stu-id="b1881-131">Fourth text box</span></span>|<span data-ttu-id="b1881-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b1881-132">`Name`, `Text`</span></span>|<span data-ttu-id="b1881-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="b1881-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="b1881-134">Добавьте метку рядом с каждым текстовым полем.</span><span class="sxs-lookup"><span data-stu-id="b1881-134">Add a label next to each text box.</span></span> <span data-ttu-id="b1881-135">Задайте свойство `Text` для каждой метки, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b1881-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="b1881-136">Объект</span><span class="sxs-lookup"><span data-stu-id="b1881-136">Object</span></span>|<span data-ttu-id="b1881-137">Свойство</span><span class="sxs-lookup"><span data-stu-id="b1881-137">Property</span></span>|<span data-ttu-id="b1881-138">Параметр</span><span class="sxs-lookup"><span data-stu-id="b1881-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="b1881-139">Первая метка</span><span class="sxs-lookup"><span data-stu-id="b1881-139">First label</span></span>|`Text`|<span data-ttu-id="b1881-140">Исходный файл</span><span class="sxs-lookup"><span data-stu-id="b1881-140">Source File</span></span>|  
    |<span data-ttu-id="b1881-141">Вторая метка</span><span class="sxs-lookup"><span data-stu-id="b1881-141">Second label</span></span>|`Text`|<span data-ttu-id="b1881-142">Сравнение строк</span><span class="sxs-lookup"><span data-stu-id="b1881-142">Compare String</span></span>|  
    |<span data-ttu-id="b1881-143">Третья метка</span><span class="sxs-lookup"><span data-stu-id="b1881-143">Third label</span></span>|`Text`|<span data-ttu-id="b1881-144">Совпадающие слова</span><span class="sxs-lookup"><span data-stu-id="b1881-144">Matching Words</span></span>|  
    |<span data-ttu-id="b1881-145">Четвертая метка</span><span class="sxs-lookup"><span data-stu-id="b1881-145">Fourth label</span></span>|`Text`|<span data-ttu-id="b1881-146">Число строк</span><span class="sxs-lookup"><span data-stu-id="b1881-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="b1881-147">Создание компонента BackgroundWorker и подписка на его события</span><span class="sxs-lookup"><span data-stu-id="b1881-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="b1881-148">Добавьте в форму компонент <xref:System.ComponentModel.BackgroundWorker> из раздела **Компоненты** в **панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="b1881-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="b1881-149">Он будет отображаться в области компонентов формы.</span><span class="sxs-lookup"><span data-stu-id="b1881-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="b1881-150">Задайте следующие свойства для объекта BackgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="b1881-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="b1881-151">Свойство</span><span class="sxs-lookup"><span data-stu-id="b1881-151">Property</span></span>|<span data-ttu-id="b1881-152">Параметр</span><span class="sxs-lookup"><span data-stu-id="b1881-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="b1881-153">Да</span><span class="sxs-lookup"><span data-stu-id="b1881-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="b1881-154">True</span><span class="sxs-lookup"><span data-stu-id="b1881-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="b1881-155">Определение метода, который будет выполняться в отдельном потоке</span><span class="sxs-lookup"><span data-stu-id="b1881-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="b1881-156">В меню **Проект** меню выберите пункт **Добавить класс**, чтобы добавить класс в проект.</span><span class="sxs-lookup"><span data-stu-id="b1881-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="b1881-157">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="b1881-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="b1881-158">Выберите **Класс** в окне "Шаблоны" и введите `Words.vb` в поле имени.</span><span class="sxs-lookup"><span data-stu-id="b1881-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="b1881-159">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b1881-159">Click **Add**.</span></span> <span data-ttu-id="b1881-160">Отобразится класс `Words`.</span><span class="sxs-lookup"><span data-stu-id="b1881-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="b1881-161">Добавьте следующий код в класс `Words` :</span><span class="sxs-lookup"><span data-stu-id="b1881-161">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="b1881-162">Обработка событий из потока</span><span class="sxs-lookup"><span data-stu-id="b1881-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="b1881-163">Добавьте в основную форму следующие обработчики событий:</span><span class="sxs-lookup"><span data-stu-id="b1881-163">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="b1881-164">Запуск и вызов нового потока, выполняющего метод WordCount</span><span class="sxs-lookup"><span data-stu-id="b1881-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="b1881-165">Добавьте в программу следующие процедуры:</span><span class="sxs-lookup"><span data-stu-id="b1881-165">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="b1881-166">Вызовите метод `StartThread` из кнопки `Start` в вашей форме:</span><span class="sxs-lookup"><span data-stu-id="b1881-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="b1881-167">Реализация кнопки "Отмена", останавливающей поток</span><span class="sxs-lookup"><span data-stu-id="b1881-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="b1881-168">Вызовите процедуру `StopThread` из обработчика событий `Click` для кнопки `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="b1881-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="b1881-169">Тестирование</span><span class="sxs-lookup"><span data-stu-id="b1881-169">Testing</span></span>  
 <span data-ttu-id="b1881-170">Теперь вы можете протестировать приложение и убедиться в том, что оно работает правильно.</span><span class="sxs-lookup"><span data-stu-id="b1881-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="b1881-171">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="b1881-171">To test the application</span></span>  
  
1.  <span data-ttu-id="b1881-172">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="b1881-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="b1881-173">В открывшейся форме введите путь к файлу, который нужно протестировать, в поле `sourceFile`.</span><span class="sxs-lookup"><span data-stu-id="b1881-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="b1881-174">Например, если тестовый файл называется Test.txt, введите C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="b1881-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="b1881-175">Во втором текстовом поле введите слово или фразу для поиска приложения в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="b1881-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="b1881-176">Нажмите кнопку `Start`.</span><span class="sxs-lookup"><span data-stu-id="b1881-176">Click the `Start` button.</span></span> <span data-ttu-id="b1881-177">Значение на кнопке `LinesCounted` начнет увеличиваться незамедлительно.</span><span class="sxs-lookup"><span data-stu-id="b1881-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="b1881-178">По завершении в приложении отобразится сообщение "Подсчет завершен".</span><span class="sxs-lookup"><span data-stu-id="b1881-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="b1881-179">Тестирование кнопки "Отмена"</span><span class="sxs-lookup"><span data-stu-id="b1881-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="b1881-180">Нажмите клавишу F5 для запуска приложения, а затем введите имя файла и слово для поиска, как описано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="b1881-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="b1881-181">Убедитесь, что выбранный файл достаточно большой для того, чтобы процедуру можно было отменить до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="b1881-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="b1881-182">Нажмите кнопку `Start`, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="b1881-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="b1881-183">Нажмите кнопку `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="b1881-183">Click the `Cancel` button.</span></span> <span data-ttu-id="b1881-184">Приложение должно незамедлительно прекратить подсчет.</span><span class="sxs-lookup"><span data-stu-id="b1881-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b1881-185">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="b1881-185">Next Steps</span></span>  
 <span data-ttu-id="b1881-186">Это приложение включает обработку некоторых основных ошибок.</span><span class="sxs-lookup"><span data-stu-id="b1881-186">This application contains some basic error handling.</span></span> <span data-ttu-id="b1881-187">Оно выявляет пустые строки поиска.</span><span class="sxs-lookup"><span data-stu-id="b1881-187">It detects blank search strings.</span></span> <span data-ttu-id="b1881-188">Программу можно сделать более надежной за счет обработки других ошибок, например, превышения максимального числа слов или строк, которые могут быть подсчитаны.</span><span class="sxs-lookup"><span data-stu-id="b1881-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1881-189">См. также</span><span class="sxs-lookup"><span data-stu-id="b1881-189">See Also</span></span>  
 <span data-ttu-id="b1881-190">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) (Работа с потоками (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="b1881-190">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)</span></span>  
 [<span data-ttu-id="b1881-191">Пошаговое руководство: Разработка простого многопоточного компонента с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1881-191">Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic</span></span>](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [<span data-ttu-id="b1881-192">Практическое руководство. Подписка и отмена подписки на события</span><span class="sxs-lookup"><span data-stu-id="b1881-192">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
