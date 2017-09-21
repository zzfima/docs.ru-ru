---
title: "Пошаговое руководство. Многопоточность с помощью компонента BackgroundWorker (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 541a1ec788c337eea9965b8a46155e5c6606ea2f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a>Пошаговое руководство. Многопоточность с помощью компонента BackgroundWorker (C#)
В этом пошаговом руководстве описывается создание многопоточного приложения Windows Forms, которое выполняет поиск заданного слова в текстовом файле. В нем демонстрируются:  
  
-   Определение класса с методом, который может вызываться компонентом <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Обработка событий, вызываемых компонентом <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Запуск компонента <xref:System.ComponentModel.BackgroundWorker> для выполнения метода.  
  
-   Реализация кнопки `Cancel`, которая останавливает компонент <xref:System.ComponentModel.BackgroundWorker>.  
  
### <a name="to-create-the-user-interface"></a>Создание пользовательского интерфейса  
  
1.  Откройте новый проект приложения Windows Forms C# и создайте форму с именем `Form1`.  
  
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
  
    |Объект|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |Первая метка|`Text`|Исходный файл|  
    |Вторая метка|`Text`|Сравнение строк|  
    |Третья метка|`Text`|Совпадающие слова|  
    |Четвертая метка|`Text`|Число строк|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>Создание компонента BackgroundWorker и подписка на его события  
  
1.  Добавьте в форму компонент <xref:System.ComponentModel.BackgroundWorker> из раздела **Компоненты** в **панели элементов**. Он будет отображаться в области компонентов формы.  
  
2.  Задайте для объекта backgroundWorker1 следующие свойства.  
  
    |Свойство|Параметр|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|Да|  
    |`WorkerSupportsCancellation`|Да|  
  
3.  Подпишитесь на события объекта backgroundWorker1. В верхней части окна **Свойства** нажмите на значок **События**. Дважды щелкните событие `RunWorkerCompleted`, чтобы создать метод обработчика событий. Сделайте то же самое для событий `ProgressChanged` и `DoWork`.  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>Определение метода, который будет выполняться в отдельном потоке  
  
1.  В меню **Проект** меню выберите пункт **Добавить класс**, чтобы добавить класс в проект. Откроется диалоговое окно **Добавление нового элемента**.  
  
2.  Выберите **Класс** в окне "Шаблоны" и введите `Words.cs` в поле имени.  
  
3.  Нажмите кнопку **Добавить**. Отобразится класс `Words`.  
  
4.  Добавьте следующий код в класс `Words` :  
  
    ```csharp  
    public class Words  
    {  
        // Object to store the current state, for passing to the caller.  
        public class CurrentState  
        {  
            public int LinesCounted;  
            public int WordsMatched;  
        }  
  
        public string SourceFile;  
        public string CompareString;  
        private int WordCount;  
        private int LinesCounted;  
  
        public void CountWords(  
            System.ComponentModel.BackgroundWorker worker,  
            System.ComponentModel.DoWorkEventArgs e)  
        {  
            // Initialize the variables.  
            CurrentState state = new CurrentState();  
            string line = "";  
            int elapsedTime = 20;  
            DateTime lastReportDateTime = DateTime.Now;  
  
            if (CompareString == null ||  
                CompareString == System.String.Empty)  
            {  
                throw new Exception("CompareString not specified.");  
            }  
  
            // Open a new stream.  
            using (System.IO.StreamReader myStream = new System.IO.StreamReader(SourceFile))  
            {  
                // Process lines while there are lines remaining in the file.  
                while (!myStream.EndOfStream)  
                {  
                    if (worker.CancellationPending)  
                    {  
                        e.Cancel = true;  
                        break;  
                    }  
                    else  
                    {  
                        line = myStream.ReadLine();  
                        WordCount += CountInString(line, CompareString);  
                        LinesCounted += 1;  
  
                        // Raise an event so the form can monitor progress.  
                        int compare = DateTime.Compare(  
                            DateTime.Now, lastReportDateTime.AddMilliseconds(elapsedTime));  
                        if (compare > 0)  
                        {  
                            state.LinesCounted = LinesCounted;  
                            state.WordsMatched = WordCount;  
                            worker.ReportProgress(0, state);  
                            lastReportDateTime = DateTime.Now;  
                        }  
                    }  
                    // Uncomment for testing.  
                    //System.Threading.Thread.Sleep(5);  
                }  
  
                // Report the final count values.  
                state.LinesCounted = LinesCounted;  
                state.WordsMatched = WordCount;  
                worker.ReportProgress(0, state);  
            }  
        }  
  
        private int CountInString(  
            string SourceString,  
            string CompareString)  
        {  
            // This function counts the number of times  
            // a word is found in a line.  
            if (SourceString == null)  
            {  
                return 0;  
            }  
  
            string EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString);  
  
            System.Text.RegularExpressions.Regex regex;  
            regex = new System.Text.RegularExpressions.Regex(   
                // To count all occurrences of the string, even within words, remove  
                // both instances of @"\b" from the following line.  
                @"\b" + EscapedCompareString + @"\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase);  
  
            System.Text.RegularExpressions.MatchCollection matches;  
            matches = regex.Matches(SourceString);  
            return matches.Count;  
        }  
  
    }  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a>Обработка событий из потока  
  
-   Добавьте в основную форму следующие обработчики событий:  
  
    ```csharp  
    private void backgroundWorker1_RunWorkerCompleted(object sender, RunWorkerCompletedEventArgs e)  
    {  
    // This event handler is called when the background thread finishes.  
    // This method runs on the main thread.  
    if (e.Error != null)  
        MessageBox.Show("Error: " + e.Error.Message);  
    else if (e.Cancelled)  
        MessageBox.Show("Word counting canceled.");  
    else  
        MessageBox.Show("Finished counting words.");  
    }  
  
    private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)  
    {  
        // This method runs on the main thread.  
        Words.CurrentState state =  
            (Words.CurrentState)e.UserState;  
        this.LinesCounted.Text = state.LinesCounted.ToString();  
        this.WordsCounted.Text = state.WordsMatched.ToString();  
    }  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>Запуск и вызов нового потока, выполняющего метод WordCount  
  
1.  Добавьте в программу следующие процедуры:  
  
    ```csharp  
    private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)  
    {  
        // This event handler is where the actual work is done.  
        // This method runs on the background thread.  
  
        // Get the BackgroundWorker object that raised this event.  
        System.ComponentModel.BackgroundWorker worker;  
        worker = (System.ComponentModel.BackgroundWorker)sender;  
  
        // Get the Words object and call the main method.  
        Words WC = (Words)e.Argument;  
        WC.CountWords(worker, e);  
    }  
  
    private void StartThread()  
    {  
        // This method runs on the main thread.  
        this.WordsCounted.Text = "0";  
  
        // Initialize the object that the background worker calls.  
        Words WC = new Words();  
        WC.CompareString = this.CompareString.Text;  
        WC.SourceFile = this.SourceFile.Text;  
  
        // Start the asynchronous operation.  
        backgroundWorker1.RunWorkerAsync(WC);  
    }  
    ```  
  
2.  Вызовите метод `StartThread` из кнопки `Start` в вашей форме:  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>Реализация кнопки "Отмена", останавливающей поток  
  
    -   Вызовите процедуру `StopThread` из обработчика событий `Click` для кнопки `Cancel`.  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
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
  
## <a name="next-steps"></a>Дальнейшие действия  
 Это приложение включает обработку некоторых основных ошибок. Оно выявляет пустые строки поиска. Программу можно сделать более надежной за счет обработки других ошибок, например, превышения максимального числа слов или строк, которые могут быть подсчитаны.  
  
## <a name="see-also"></a>См. также  
 [Работа с потоками (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)   
 [Практическое руководство. Подписка и отмена подписки на события](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)

