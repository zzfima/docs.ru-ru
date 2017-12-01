---
title: "Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49e03a8d886ccd4ed6e4b2a19692c1874f5928ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях
Многие компоненты предоставляют возможность асинхронного выполнения работы. <xref:System.Media.SoundPlayer> И <xref:System.Windows.Forms.PictureBox> компоненты, например, включить возможность загрузить звуки и изображений «в фоновом режиме», а основной поток продолжает работу без прерывания.  
  
 Использование асинхронных методов в классе, который поддерживает [Обзор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) может быть простым, как и присоединение обработчика событий в компонент *имя_метода* `Completed` события так же, как для любого другого события. При вызове *имя_метода* `Async` метод, ваше приложение продолжит работу без перерыва, пока *имя_метода* `Completed` события. В обработчике событий можно просматривать <xref:System.ComponentModel.AsyncCompletedEventArgs> параметра, чтобы определить, если асинхронная операция выполнена успешно, или была отменена.  
  
 Дополнительные сведения об использовании обработчиков событий см. в разделе [Обзор обработчиков событий](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Ниже показано, как использовать асинхронную возможность загрузки изображения <xref:System.Windows.Forms.PictureBox> элемента управления.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Чтобы включить элемент управления PictureBox асинхронно загружать изображения  
  
1.  Создайте экземпляр класса <xref:System.Windows.Forms.PictureBox> компонент в форме.  
  
2.  Создайте обработчик события для <xref:System.Windows.Forms.PictureBox.LoadCompleted> события.  
  
     Проверьте наличие ошибок, произошедших во время асинхронной загрузки. Кроме того, это место, где искать отмены.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Добавьте две кнопки, вызывается `loadButton` и `cancelLoadButton`, в форму. Добавить <xref:System.Windows.Forms.Control.Click> обработчики событий запуска и отмены загрузки.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Запустите приложение.  
  
     Как загрузки изображения можно свободно перемещаться по форме, свернуть и развернуть его.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [НЕ в СБОРКЕ: Многопоточность в Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
