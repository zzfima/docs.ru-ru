---
title: "Обзор модели приложения Visual Basic | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Application object, Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0925bb102c148480d82128b91cbf1762de24e7ec
ms.lasthandoff: 03/13/2017

---
# <a name="overview-of-the-visual-basic-application-model"></a>Обзор модели приложения в Visual Basic
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет четко определенную модель для управления поведением приложений Windows Forms: [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] модели приложения. Эта модель включает события для обработки приложения запуска и завершения работы, а также события для перехвата необработанных исключений. Он также обеспечивает поддержку для разработки приложений с одним экземпляром. Модель приложения является расширяемой, поэтому разработчики, которые необходим больший контроль могут настраивать переопределяемые методы.  
  
## <a name="uses-for-the-application-model"></a>Использование модели приложения  
 Типичный приложению для выполнения задач при запуске и завершении работы. Например при запуске, приложение может отображать экран-заставку, подключаться к базе данных, загружает сохраненное состояние и т.д. При завершении работы приложения, его закрытия подключений к базе данных, сохранять текущее состояние и т.д. Кроме того, приложение может выполнить определенный код при завершении приложения вниз непредвиденно, например во время необработанное исключение.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Модель приложения позволяет легко создавать *экземпляра* приложения. Приложения с одним экземпляром отличается от обычных приложений тем, что только один экземпляр приложения может выполняться одновременно. Попытка запуска другого экземпляра такого приложения приводит к первоначальный экземпляр уведомляется — с помощью параметра `StartupNextInstance` событий — что была выполнена следующая попытка запуска. Уведомление содержит аргументы командной строки последующего экземпляра. Последующий экземпляр приложения затем закрывается до любой инициализации.  
  
 Приложения с одним экземпляром запускается и проверяет, является ли первый экземпляр или последующим экземпляром приложения:  
  
-   Если это первый экземпляр, оно запускается обычным образом.  
  
-   Каждая следующая попытка запустить приложение, пока первый экземпляр, приведет к очень по-разному. Последующие попытки уведомляет об аргументах командной строки первого экземпляра и немедленно завершает работу. Первый экземпляр обрабатывает `StartupNextInstance` событие, чтобы определить аргументы командной строки последующих экземпляров, а затем продолжает работать.  
  
     На этой диаграмме показано, как последующий экземпляр уведомляет первый экземпляр.  
  
     ![Единый образ экземпляра приложения](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 При обработке `StartupNextInstance` события, можно управлять поведением приложения одного экземпляра. Например Microsoft Outlook обычно запускается как приложение одного экземпляра; Когда Outlook работает и при попытке запустить Outlook снова, фокус перемещается к первому экземпляру, но другой экземпляр не открывается.  
  
## <a name="events-in-the-application-model"></a>События в модели приложения  
 В модели приложения предусмотрены следующие события:  
  
-   **Запуск приложения**. Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>при запуске.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> При обработке этого события, можно добавить код, который инициализирует приложение до загрузки главной формы. `Startup` Событий также предоставляет возможность отменить выполнение приложения во время этого этапа процесса загрузки, при необходимости.  
  
     Можно настроить приложение для отображения заставки при выполнении кода запуска приложения. По умолчанию модель приложения отключает заставку экрана, когда либо `/nosplash` или `-nosplash` используется аргумент командной строки.  
  
-   **Приложения с одним процессом**. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>Событие возникает при запуске последующего экземпляра приложения с одним экземпляром.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Событие передает аргументы командной строки последующего экземпляра.  
  
-   **Необработанные исключения**. Если в приложении возникает необработанное исключение, он выдает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>событий.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> Обработчик этого события может проверить исключение и определить, следует ли продолжить выполнение.  
  
     `UnhandledException` Событие не вызывается в некоторых случаях. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
  
-   **Изменения сетевого подключения**. При изменении доступности сети компьютера приложение вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>событий.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
  
     `NetworkAvailabilityChanged` Событие не вызывается в некоторых случаях. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
  
-   **Завершить работу приложения**. Приложение предоставляет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>событие для оповещения при закрытии.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> В этом случае обработчик, можно гарантировать, что операции в приложении необходимо выполнить, закрытие и сохранение, например — завершены. Можно настроить приложение на завершение работы при закрытии главной формы или завершать работу только закрытие всех форм.  
  
## <a name="availability"></a>Доступность  
 По умолчанию [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] модель приложения доступно для проектов Windows Forms. Если настроить приложение на использование другого автоматически запускаемого объекта или запуск кода приложения с пользовательским `Sub Main`, затем, объекта или класса может понадобиться предоставить реализацию <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>класс для использования в модели приложения.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Сведения об изменении автоматически запускаемого объекта см. в разделе [страница "приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
