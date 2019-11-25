---
title: Обзор модели приложения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: aa47304cf2bded93bdb95ffe7dfa35bb37d9a643
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976462"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Обзор модели приложения в Visual Basic

Visual Basic предоставляет четко определенную модель для управления поведением Windows Forms приложений: модель Visual Basic приложения. Эта модель включает события для обработки запуска и завершения работы приложения, а также события для перехвата необработанных исключений. Он также обеспечивает поддержку разработки приложений с одним экземпляром. Модель приложения является расширяемой, поэтому разработчики, которым требуется больший контроль, могут настраивать переопределяемые методы.  
  
## <a name="uses-for-the-application-model"></a>Использование для модели приложения  

 Типичное приложение должно выполнять задачи при запуске и завершении работы. Например, при запуске приложение может отобразить экран-заставку, сделать подключения к базе данных, загрузить сохраненное состояние и т. д. Когда приложение завершает работу, оно может закрыть подключения к базе данных, сохранить текущее состояние и т. д. Кроме того, приложение может выполнять конкретный код при неожиданном завершении работы приложения, например во время необработанного исключения.  
  
 Модель приложений Visual Basic позволяет легко создавать приложения с *одним экземпляром* . Приложение с одним экземпляром отличается от обычного приложения тем, что в каждый момент времени может выполняться только один экземпляр приложения. Попытка запуска другого экземпляра приложения с одним экземпляром приводит к уведомлению об исходном экземпляре (с помощью события `StartupNextInstance`), когда была выполнена другая попытка запуска. Уведомление содержит аргументы командной строки последующего экземпляра. Затем последующий экземпляр приложения закрывается до того, как будет выполнена инициализация.  
  
 Запускается приложение с одним экземпляром, которое проверяет, является ли он первым экземпляром или последующим экземпляром приложения:  
  
- Если это первый экземпляр, он запускается как обычно.  
  
- При каждой последующей попытке запустить приложение, в то время как первый экземпляр работает, поведение будет сильно отличаться. Последующая попытка уведомляет первый экземпляр о аргументах командной строки, а затем сразу же завершает работу. Первый экземпляр обрабатывает событие `StartupNextInstance`, чтобы определить аргументы командной строки последующего экземпляра и продолжить выполнение.  
  
     На этой схеме показано, как последующий экземпляр сигнализирует о первом экземпляре:  
  
     ![Схема, на которой показан образ приложения с одним экземпляром.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Обрабатывая событие `StartupNextInstance`, можно управлять тем, как ведет себя приложение с одним экземпляром. Например, Microsoft Outlook обычно выполняется как приложение с одним экземпляром. Когда Outlook запущен и вы снова попытаетесь запустить Outlook, фокус перемещается на исходный экземпляр, но другой экземпляр не открывается.  
  
## <a name="events-in-the-application-model"></a>События в модели приложения  

 В модели приложения находятся следующие события:  
  
- **Запуск приложения**. Приложение вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> при запуске. Обрабатывая это событие, можно добавить код, который инициализирует приложение перед загрузкой основной формы. Событие `Startup` также обеспечивает отмену выполнения приложения на этом этапе процесса запуска (при необходимости).  
  
     В приложении можно настроить отображение экрана-заставки во время выполнения кода запуска приложения. По умолчанию модель приложения подавляет экран-заставку при использовании аргумента командной строки `/nosplash` или `-nosplash`.  
  
- **Приложения с одним экземпляром**. Событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> возникает при запуске последующего экземпляра приложения с одним экземпляром. Событие передает аргументы командной строки последующего экземпляра.  
  
- **Необработанные исключения**. Если приложение встречает необработанное исключение, оно вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>. Обработчик для этого события может проверить исключение и определить, следует ли продолжать выполнение.  
  
     В некоторых обстоятельствах событие `UnhandledException` не возникает. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Изменения в подключении к сети**. При изменении доступности сети на компьютере приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
     В некоторых обстоятельствах событие `NetworkAvailabilityChanged` не возникает. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- **Завершение работы приложения**. Приложение предоставляет событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> для сигнализации о завершении работы. В этом обработчике событий можно убедиться, что операции, которые должны выполняться приложением (например, закрытие и сохранение), завершены. Можно настроить приложение для завершения работы при закрытии главной формы или завершить работу только при закрытии всех форм.  
  
## <a name="availability"></a>Доступность  

 По умолчанию модель приложения Visual Basic доступна для проектов Windows Forms. Если настроить приложение для использования другого объекта запуска или запустить код приложения с помощью настраиваемого `Sub Main`, то для использования модели приложения этому объекту или классу может потребоваться предоставить реализацию класса <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Сведения об изменении объекта запуска см. в разделе [Страница "приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
