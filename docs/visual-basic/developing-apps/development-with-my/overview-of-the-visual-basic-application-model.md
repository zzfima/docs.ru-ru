---
title: Обзор модели приложения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: 16522424ecd3009cb905bacb39694189a9540318
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517387"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Обзор модели приложения в Visual Basic
Visual Basic предоставляет четко определенную модель для управления поведением приложений Windows Forms: модель приложения Visual Basic. Эта модель включает события для обработки приложения запуска и завершения работы, а также события для перехвата необработанных исключений. Он также обеспечивает поддержку для разработки приложения с одним процессом. Модель приложения является расширяемой, поэтому разработчики, которым требуется больший контроль можно настраивать переопределяемые методы.  
  
## <a name="uses-for-the-application-model"></a>Использование модели приложения  
 Типичное приложение необходимо для выполнения задач при запуске и завершении работы. Например при запуске, приложение можно отобразить экран-заставку, подключаться к базе данных, загрузить сохраненное состояние и так далее. При завершении работы приложения, его можно закрыть подключения к базе данных, сохранить текущее состояние и так далее. Кроме того, приложение может выполнить определенный код при завершении приложения вниз неожиданно, таких как во время необработанное исключение.  
  
 Модель приложения Visual Basic позволяет легко создавать *единственной* приложения. Приложение в одном экземпляре отличается от обычного приложения тем, что только один экземпляр приложения может выполняться одновременно. Попытка запуска другого экземпляра приложения одного экземпляра приводит к первоначальному уведомляется — с помощью параметра `StartupNextInstance` событий — еще одна попытка запуска была создана. Уведомление содержит аргументы командной строки последующего экземпляра. Последующий экземпляр приложения, которое затем разрывается, перед любой инициализации.  
  
 Приложение в одном экземпляре запускается и проверяет, является ли первый экземпляр или последующий экземпляр приложения:  
  
-   Если это первый экземпляр, оно запускается обычным образом.  
  
-   Каждой последующей попытки для запуска приложения, пока первый экземпляр, приводит к кардинально разное поведение. Последующие попытки уведомляет первый экземпляр об аргументах командной строки и немедленно завершает работу. Первый экземпляр обрабатывает `StartupNextInstance` событие, чтобы определить аргументы командной строки последующего экземпляра, а затем продолжает выполняться.  
  
     На этой схеме показано, как последующий экземпляр уведомляет первый экземпляр.  
  
     ![Единый образ экземпляра приложения](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 При обработке `StartupNextInstance` событий, можно управлять поведением одним экземпляром приложения. Например Microsoft Outlook обычно запускается как приложение одного экземпляра; Если Outlook работает, и попытке запустить Outlook снова, фокуса в исходном экземпляре, но другой экземпляр не открывается.  
  
## <a name="events-in-the-application-model"></a>События в модели приложения  
 В модели приложения находятся следующие события:  
  
-   **Запуск приложения**. Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> событий при запуске. Обрабатывая это событие, можно добавить код, который инициализирует приложение до загрузки главной формы. `Startup` Событий также предоставляет возможность отменить выполнение приложения во время этого этапа процесса загрузки, при необходимости.  
  
     Можно настроить приложение для отображения экрана-заставки, во время выполнения кода запуска приложения. По умолчанию модель приложения отключает заставку экрана, когда либо `/nosplash` или `-nosplash` используется аргумент командной строки.  
  
-   **Приложения с одним процессом**. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Событие возникает при запуске последующего экземпляра приложения одного экземпляра. Событие передает аргументы командной строки последующего экземпляра.  
  
-   **Необработанные исключения**. Если в приложении возникает необработанное исключение, он выдает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> событий. Обработчик этого события можно проверить исключение и определить, следует ли продолжить выполнение.  
  
     `UnhandledException` Событие не происходит в некоторых случаях. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
-   **Изменения сетевого подключения**. При изменении доступности сети компьютера, приложение создает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> событий.  
  
     `NetworkAvailabilityChanged` Событие не происходит в некоторых случаях. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
-   **Завершить работу приложения**. Приложение предоставляет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> событие, чтобы сообщить при закрытии. В этом событии обработчик, можно гарантировать, что операции в приложении необходимо выполнить, закрытие и сохранение, например, завершены. Чтобы завершить работу при закрытии главной формы, или завершать работу только закрытие всех форм приложения можно настроить.  
  
## <a name="availability"></a>Доступность  
 По умолчанию модель приложения Visual Basic доступен для проектов Windows Forms. Настройка приложения для использования разных автоматически запускаемый объект, или запустить код приложения с пользовательским `Sub Main`, затем, объект или класс может потребоваться предоставить реализацию <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> класс для использования в модели приложения. Сведения об изменении автоматически запускаемый объект, см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
