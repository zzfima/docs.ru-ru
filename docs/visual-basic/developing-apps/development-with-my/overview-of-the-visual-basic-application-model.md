---
title: Обзор модели приложения в Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74a8fcfe3f49ab042b3bb4775f9f6e84374db0ae
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="overview-of-the-visual-basic-application-model"></a>Обзор модели приложения в Visual Basic
Visual Basic предоставляет четко определенную модель для управления поведением приложений Windows Forms: модель приложения Visual Basic. Эта модель включает события для обработки приложения при запуске и завершении работы, а также события для перехвата необработанных исключений. Он также обеспечивает поддержку для разработки приложений с одним экземпляром. Модель приложения является расширяемой, поэтому разработчики, которые требуется больший контроль над можно настраивать переопределяемые методы.  
  
## <a name="uses-for-the-application-model"></a>Использует для модели приложения  
 Типичное приложение требуется для выполнения задач при запуске и завершении работы. Например при запуске, приложение можно отображение экрана-заставки, подключаться к базе данных, загрузить сохраненное состояние и т. д. При завершении работы приложения, его можно закрыть подключения к базе данных, сохранить текущее состояние и так далее. Кроме того, приложение может выполнить определенный код при завершении приложения вниз непредвиденно, например во время необработанное исключение.  
  
 Модель приложения Visual Basic упрощает создание *единственных* приложения. Приложению экземпляра отличается от обычного приложения, в том, что только один экземпляр приложения может выполняться одновременно. Попытка запуска другого экземпляра приложения с одним экземпляром приводит к первоначальному уведомляется — с помощью параметра `StartupNextInstance` событий — вносилось еще одну попытку запуска. Уведомление содержит аргументы командной строки последующего экземпляра. Последующий экземпляр приложения затем закрывается до любой инициализации.  
  
 Приложения с одним экземпляром начинается и проверяет, является ли первый экземпляр или последующим экземпляром приложения.  
  
-   Если это первый экземпляр, оно запускается обычным образом.  
  
-   Каждый повторная попытка запуска приложения, пока первый экземпляр, приводит к очень по-разному. Последующие попытки уведомляет первый экземпляр об аргументах командной строки и немедленно завершает работу. Первый экземпляр обрабатывает `StartupNextInstance` событие, чтобы определить аргументы командной строки последующих экземпляров, а затем продолжает выполняться.  
  
     На этой диаграмме показано, как последующий экземпляр уведомляет первый экземпляр.  
  
     ![Один экземпляр приложения изображения](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 При обработке `StartupNextInstance` событий, можно управлять поведением приложения одного экземпляра. Например Microsoft Outlook обычно запускается как приложение одного экземпляра; Если Outlook работает и попытаться запустить Outlook еще раз, фокус перемещается к первому экземпляру, но другой экземпляр не открывается.  
  
## <a name="events-in-the-application-model"></a>События в модели приложения  
 В модели приложения находятся следующие события:  
  
-   **Запуск приложения**. Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> событий при запуске. С помощью обработки этого события, можно добавить код, который инициализирует приложение до загрузки главной формы. `Startup` Событий также предоставляет возможность отменить выполнение приложения во время этого этапа процесса загрузки, при необходимости.  
  
     Можно настроить приложение для отображения экрана-заставки при выполнении кода запуска приложения. По умолчанию модель приложения отключает заставку экрана, когда либо `/nosplash` или `-nosplash` используется аргумент командной строки.  
  
-   **Приложения с одним процессом**. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Событие возникает при запуске последующих экземпляр приложения с одним экземпляром. Событие передает аргументы командной строки последующего экземпляра.  
  
-   **Необработанные исключения**. При возникновении необработанного исключения в приложении, он выдает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> событий. Обработчик этого события можно проверить исключение и определить, следует ли продолжить выполнение.  
  
     `UnhandledException` Событие не происходит при некоторых обстоятельствах. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
-   **Изменения сетевого подключения**. При изменении доступности сети компьютера, приложение вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> событий.  
  
     `NetworkAvailabilityChanged` Событие не происходит при некоторых обстоятельствах. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
-   **Завершение работы приложения**. Приложение предоставляет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> событие для сигнализации при закрытии. В этом случае обработчик, можно гарантировать, что операции в приложении необходимо выполнить, закрытие и сохранение, например — завершены. Можно настроить приложение на завершение работы при закрытии главной формы или завершать работу только закрытие всех форм.  
  
## <a name="availability"></a>Доступность  
 По умолчанию модель приложения Visual Basic доступна в проектах Windows Forms. Если настроить приложение на использование другого автоматически запускаемого объекта или запуск кода приложения с пользовательским `Sub Main`, затем этого объекта или класса может понадобиться предоставить реализацию <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> класс для использования в модели приложения. Сведения об изменении автоматически запускаемого объекта см. в разделе [страница "приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
