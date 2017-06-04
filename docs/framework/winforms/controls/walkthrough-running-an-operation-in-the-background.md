---
title: "Пример. Фоновое выполнение операции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "фоновые операции"
  - "фоновые задачи"
  - "фоновые потоки"
  - "BackgroundWorker - класс, примеры"
  - "формы, фоновые операции"
  - "формы, многопоточность"
  - "работа с потоками [Windows Forms], фоновые операции"
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Пример. Фоновое выполнение операции
Если какая\-либо операция будет выполняться в течение долгого времени, и при этом требуется не допустить, чтобы пользовательский интерфейс перестал отвечать на запросы пользователя или "завис", можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.  
  
 Полный текст кода для текущего примера см. в разделе [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Для запуска операции в фоновом режиме выполните следующие действия.  
  
1.  Когда форма будет открыта в конструкторе Windows Forms, перетащите два элемента управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму, затем установите значения свойств `Name` и <xref:System.Windows.Forms.Control.Text%2A> для кнопок согласно следующей таблицы.  
  
    |Кнопка|Имя|Текст|  
    |------------|---------|-----------|  
    |`button1`|`startBtn`|Start|  
    |`button2`|`cancelBtn`|Отмена|  
  
2.  Откройте **панель элементов**, перейдите на вкладку **Компоненты** и перетащите в форму компонент <xref:System.ComponentModel.BackgroundWorker>.  
  
     Компонент `backgroundWorker1` появится в **области компонентов**.  
  
3.  В окне **Свойства** установите для свойства <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> значение `true`.  
  
4.  В окне **Свойства** нажмите кнопку **События**, и затем дважды щелкните события <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>, чтобы создать обработчики событий.  
  
5.  Вставьте код, требующий длительного выполнения, в обработчик события <xref:System.ComponentModel.BackgroundWorker.DoWork>.  
  
6.  Параметры, необходимые для операции, можно получить из свойства <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> параметра <xref:System.ComponentModel.DoWorkEventArgs>.  
  
7.  Присвойте результат вычисления свойству <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> <xref:System.ComponentModel.DoWorkEventArgs>.  
  
     Результат будет доступен для обработчика событий <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  Вставьте код для получения результата операции в обработчик события <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. Реализуйте метод `TimeConsumingOperation`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. В конструкторе Windows Forms дважды щелкните `startButton`, чтобы создать обработчик события <xref:System.Windows.Forms.Control.Click>.  
  
11. Вызовите метод <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> в обработчике событий <xref:System.Windows.Forms.Control.Click> для `startButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. В конструкторе Windows Forms дважды щелкните `cancelButton`, чтобы создать обработчик события <xref:System.Windows.Forms.Control.Click>.  
  
13. Вызовите метод <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> в обработчике событий <xref:System.Windows.Forms.Control.Click> для `cancelButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. В начале файла импортируйте пространства имен System.ComponentModel и System.Threading.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. Нажмите клавишу F6 Press для построения решения, затем нажмите клавиши CTRL\-F5 для запуска приложения вне отладчика.  
  
> [!NOTE]
>  Если нажать клавишу F5 и запустить приложение в отладчике, то исключение, возникающее в методе `TimeConsumingOperation`, перехватывается и отображается отладчиком.  При запуске приложения вне отладчика <xref:System.ComponentModel.BackgroundWorker> обрабатывает исключение и кэширует его в свойстве <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.  
  
1.  Нажмите кнопку **Пуск** для запуска асинхронной операции, затем нажмите кнопку **Отмена** для ее остановки.  
  
     Результат каждой операции отображается в <xref:System.Windows.Forms.MessageBox>.  
  
## Следующие действия  
  
-   Примените форму, в которой отображается ход выполнения асинхронной операции.  Дополнительные сведения см. в разделе [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
-   Реализуйте класс, поддерживающий асинхронную модель для компонентов.  Дополнительные сведения см. в разделе [Implementing the Event\-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## См. также  
 <xref:System.ComponentModel.BackgroundWorker>   
 <xref:System.ComponentModel.DoWorkEventArgs>   
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Компонент BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md)