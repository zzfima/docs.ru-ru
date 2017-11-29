---
title: "Пример. Фоновое выполнение операции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de485eb0b9c67ee9c3c897b6521971f50aaf751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>Пример. Фоновое выполнение операции
Если какая-либо операция будет выполняться в течение долгого времени и при этом требуется не допустить задержек в работе пользовательского интерфейса, можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.  
  
 Полный код, используемый в этом примере, в разделе [как: выполнение операции в фоновом режиме](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-run-an-operation-in-the-background"></a>Для запуска операции в фоновом режиме  
  
1.  Форма будет открыта в конструкторе Windows Forms, перетащите два <xref:System.Windows.Forms.Button> управляет из **элементов** форму, а затем присвойте `Name` и <xref:System.Windows.Forms.Control.Text%2A> свойства кнопок согласно следующей таблице.  
  
    |Кнопка|Имя|Text|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|**Start**|  
    |`button2`|`cancelBtn`|**Отмена**|  
  
2.  Откройте **элементов**, нажмите кнопку **компоненты** , а затем перетащите <xref:System.ComponentModel.BackgroundWorker> в форму компонент.  
  
     `backgroundWorker1` Компонент появится в **область компонентов**.  
  
3.  В **свойства** задайте <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> свойства `true`.  
  
4.  В **свойства** щелкните на **событий** кнопку, а затем дважды щелкните <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> событий для создания обработчиков событий.  
  
5.  Вставка кода требует много времени в <xref:System.ComponentModel.BackgroundWorker.DoWork> обработчика событий.  
  
6.  Параметры, необходимые для операции с <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> свойство <xref:System.ComponentModel.DoWorkEventArgs> параметр.  
  
7.  Присвойте результат вычисления <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> свойство <xref:System.ComponentModel.DoWorkEventArgs>.  
  
     Это будет доступен для <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчика событий.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  Вставьте код для получения результата операции в <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчика событий.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. Выполните метод `TimeConsumingOperation`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. В конструкторе Windows Forms дважды щелкните `startButton` для создания <xref:System.Windows.Forms.Control.Click> обработчика событий.  
  
11. Вызовите <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> метод в <xref:System.Windows.Forms.Control.Click> обработчик событий для `startButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. В конструкторе Windows Forms дважды щелкните `cancelButton` для создания <xref:System.Windows.Forms.Control.Click> обработчика событий.  
  
13. Вызовите <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> метод в <xref:System.Windows.Forms.Control.Click> обработчик событий для `cancelButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. В верхней части файла импортируйте пространства имен System.ComponentModel и System.Threading.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. Нажмите клавишу F6 для построения решения и нажмите клавиши CTRL-F5 для запуска приложения вне отладчика.  
  
> [!NOTE]
>  Если нажать клавишу F5 для запуска приложения в отладчике, то исключение, возникающее в `TimeConsumingOperation` метод перехватывается и отображается отладчиком. При запуске приложения вне отладчика, <xref:System.ComponentModel.BackgroundWorker> обрабатывает исключение и кэширует его в <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> свойство <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.  
  
1.  Нажмите кнопку **запустить** для запуска асинхронной операции, а затем нажмите **отменить** кнопку для остановки асинхронной операции.  
  
     Результат каждой операции выводится в элементе <xref:System.Windows.Forms.MessageBox>.  
  
## <a name="next-steps"></a>Дальнейшие действия  
  
-   Реализация формы, в которой отображается ход выполнения асинхронной операции. Дополнительные сведения см. в разделе [как: реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
-   Реализуйте класс, поддерживающий асинхронную модель для компонентов. Дополнительные сведения см. в разделе [реализации асинхронной модели, основанной на событиях](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Компонент BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
