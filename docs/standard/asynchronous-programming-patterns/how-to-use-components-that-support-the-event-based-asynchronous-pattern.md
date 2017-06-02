---
title: "How to: Use Components That Support the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Use Components That Support the Event-based Asynchronous Pattern
Многие компоненты предоставляют возможность асинхронного выполнения работы.  Компоненты <xref:System.Media.SoundPlayer> и <xref:System.Windows.Forms.PictureBox>, к примеру, позволяют загружать звуки и изображения "в фоновом режиме", тогда как основной поток продолжает работать без прерывания.  
  
 Использование асинхронных методов для класса, поддерживающего [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md), может быть таким же простым, как и присоединение обработчика события к событию компонента *MethodName*`Completed`, так же, как и к любому другому событию.  При вызове метода *MethodName*`Async` приложение будет продолжать работать без прерывания до возникновения события *MethodName*`Completed`.  В обработчике события можно просмотреть параметр <xref:System.ComponentModel.AsyncCompletedEventArgs> для определения, была ли асинхронная операция завершена успешно или же отменена.  
  
 Дополнительные сведения об использовании обработчиков событий см. в разделе [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 В следующей процедуре показано, как использовать асинхронную возможность загрузки изображения, предоставляемую элементом управления <xref:System.Windows.Forms.PictureBox>.  
  
### Чтобы разрешить элементу управления PictureBox асинхронно загружать изображение  
  
1.  Создайте экземпляр компонента <xref:System.Windows.Forms.PictureBox> в пользовательской форме.  
  
2.  Создайте обработчик события для события <xref:System.Windows.Forms.PictureBox.LoadCompleted>.  
  
     Проверьте на наличие ошибок, которые могут произойти во время асинхронной загрузки.  Также здесь следует проверить на возможность отмены.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Добавьте в форму две кнопки `loadButton` и `cancelLoadButton`.  Добавьте обработчики события <xref:System.Windows.Forms.Control.Click> для запуска и отмены загрузки.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Запустите приложение.  
  
     При выполнении загрузки изображения можно свободно перемещаться по форме, уменьшая и увеличивая ее.  
  
## См. также  
 [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/ru-ru/c731a50c-09c1-4468-9646-54c86b75d269)