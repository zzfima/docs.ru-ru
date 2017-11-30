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
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="0e7a6-102">Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="0e7a6-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="0e7a6-103">Многие компоненты предоставляют возможность асинхронного выполнения работы.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="0e7a6-104"><xref:System.Media.SoundPlayer> И <xref:System.Windows.Forms.PictureBox> компоненты, например, включить возможность загрузить звуки и изображений «в фоновом режиме», а основной поток продолжает работу без прерывания.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="0e7a6-105">Использование асинхронных методов в классе, который поддерживает [Обзор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) может быть простым, как и присоединение обработчика событий в компонент *имя_метода* `Completed` события так же, как для любого другого события.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's *MethodName*`Completed` event, just as you would for any other event.</span></span> <span data-ttu-id="0e7a6-106">При вызове *имя_метода* `Async` метод, ваше приложение продолжит работу без перерыва, пока *имя_метода* `Completed` события.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-106">When you call the *MethodName*`Async` method, your application will continue running without interruption until the *MethodName*`Completed` event is raised.</span></span> <span data-ttu-id="0e7a6-107">В обработчике событий можно просматривать <xref:System.ComponentModel.AsyncCompletedEventArgs> параметра, чтобы определить, если асинхронная операция выполнена успешно, или была отменена.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="0e7a6-108">Дополнительные сведения об использовании обработчиков событий см. в разделе [Обзор обработчиков событий](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0e7a6-108">For more information about using event handlers, see [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="0e7a6-109">Ниже показано, как использовать асинхронную возможность загрузки изображения <xref:System.Windows.Forms.PictureBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="0e7a6-110">Чтобы включить элемент управления PictureBox асинхронно загружать изображения</span><span class="sxs-lookup"><span data-stu-id="0e7a6-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1.  <span data-ttu-id="0e7a6-111">Создайте экземпляр класса <xref:System.Windows.Forms.PictureBox> компонент в форме.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2.  <span data-ttu-id="0e7a6-112">Создайте обработчик события для <xref:System.Windows.Forms.PictureBox.LoadCompleted> события.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="0e7a6-113">Проверьте наличие ошибок, произошедших во время асинхронной загрузки.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="0e7a6-114">Кроме того, это место, где искать отмены.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  <span data-ttu-id="0e7a6-115">Добавьте две кнопки, вызывается `loadButton` и `cancelLoadButton`, в форму.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="0e7a6-116">Добавить <xref:System.Windows.Forms.Control.Click> обработчики событий запуска и отмены загрузки.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="0e7a6-117">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-117">Run your application.</span></span>  
  
     <span data-ttu-id="0e7a6-118">Как загрузки изображения можно свободно перемещаться по форме, свернуть и развернуть его.</span><span class="sxs-lookup"><span data-stu-id="0e7a6-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7a6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0e7a6-119">See Also</span></span>  
 [<span data-ttu-id="0e7a6-120">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="0e7a6-120">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="0e7a6-121">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="0e7a6-121">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="0e7a6-122">НЕ в СБОРКЕ: Многопоточность в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e7a6-122">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
