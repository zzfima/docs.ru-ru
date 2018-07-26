---
title: Расширение модели приложения Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 64c175216cf21b7947462cf79e4b88ab6fcd6d86
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245652"
---
# <a name="extending-the-visual-basic-application-model"></a>Расширение модели приложения Visual Basic
Можно добавить функциональность в модель приложения путем переопределения `Overridable` членами <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> класса. Этот метод позволяет настроить поведение модели приложения и добавить вызовы собственных методов, как приложение запускается и завершает работу.  
  
## <a name="visual-overview-of-the-application-model"></a>Визуальный Обзор модели приложения  
 В этом разделе наглядно представлена последовательность вызовов функций в модели приложения Visual Basic. В следующем разделе описывается назначение каждой функции подробно.  
  
 На следующем рисунке показан последовательность вызовов модели приложения в обычных приложениях Windows Forms Visual Basic. Последовательность начинается, когда `Sub Main` вызовы процедур <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> метод.  
  
 ![Модель приложения Visual Basic &#45; &#45; запуска](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 Модель приложения Visual Basic также предоставляет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> и <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> события. На следующем рисунке показаны механизм для создания этих событий.  
  
 ![Модель приложения Visual Basic &#45; &#45; Далее экземпляра](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Необработанное исключение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>Переопределении базовых методов  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Метод определяет порядок, в котором `Application` выполнения методов. По умолчанию `Sub Main` вызывает процедуру для приложения Windows Forms <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> метод.  
  
 Если приложение является обычного приложения (несколько экземпляров приложения), или первый экземпляр приложения одного экземпляра, <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> выполняет метод `Overridable` методы в следующем порядке:  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. По умолчанию этот метод задает визуальные стили, стили отображения текста и текущего участника для основного потока приложения (если приложение использует проверку подлинности Windows) и вызывает метод `ShowSplashScreen` Если ни один из `/nosplash` , ни `-nosplash` используется в качестве аргумент командной строки.  
  
     Последовательность запуска приложения отменяется, если эта функция возвращает `False`. Это может быть полезно в том случае, если существуют ситуации, в которых приложение не запускается.  
  
     <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Метод вызывает следующие методы:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. Определяет, имеет ли приложение заставку и если да, отображает на экране-заставке в отдельном потоке.  
  
         <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Метод содержит код, отображающий заставка экрана для по крайней мере число миллисекунд, определенных в <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> свойство. Чтобы использовать эту функцию, необходимо добавить экран-заставка для приложения с помощью **конструктор проектов** (какие наборы `My.Application.MinimumSplashScreenDisplayTime` свойства две секунды), или задать `My.Application.MinimumSplashScreenDisplayTime` свойство в методе, который переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> или <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> метод. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Позволяет разработчику создавать код, инициализирующий экран-заставка.  
  
         По умолчанию этот метод не выполняет никаких действий. Если выбран экран-заставку для приложения в Visual Basic **конструктор проектов**, конструктор переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> метод с методом, который задает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> свойства новый экземпляр формы экрана заставки .  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. Предоставляет точку расширения для вызова `Startup` событий. Последовательность запуска приложения останавливается, если эта функция возвращает `False`.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> событий. Если обработчик событий задает <xref:System.ComponentModel.CancelEventArgs.Cancel> свойства аргумента события для `True`, метод возвращает `False` отменить запуск приложения.  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. Предоставляет отправную точку для момента, когда основное приложение будет готово к началу запуска после выполнения инициализации.  
  
     По умолчанию, прежде чем он входит в цикл обработки сообщений Windows Forms, этот метод вызывает `OnCreateMainForm` (для создания главной формы приложения) и `HideSplashScreen` (чтобы закрыть экран-заставка) методы:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. Позволяет разработчику создавать код инициализации главной формы.  
  
         По умолчанию этот метод не выполняет никаких действий. Тем не менее, при выборе главной формы приложения в Visual Basic **конструктор проектов**, конструктор переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> метод с методом, который задает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> свойства новый экземпляр главной формы.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. Если приложение имеет определенную заставку, и он открыт, этот метод закрывает экран-заставка.  
  
         По умолчанию этот метод закрывает экран-заставка.  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. Предоставляет способ настраивать поведение приложения при запуске другого экземпляра приложения.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> событий.  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. Предоставляет точку расширения для вызова `Shutdown` событий. Этот метод не выполняется при возникновении необработанного исключения в главном приложении.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> событий.  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. Выполняется при возникновении необработанного исключения в любом из перечисленных выше методов.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> , пока не присоединен отладчик и приложение обрабатывает событие `UnhandledException` событий.  
  
 Если приложение является приложением одним экземпляром, и приложение уже выполняется, последующий экземпляр приложения вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> метод на исходный экземпляр приложения, а затем завершает работу.  
 
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> Конструктор вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> свойство, чтобы определить, какой механизм отрисовки текста для форм приложения. По умолчанию <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> возвращает `False`, указывающее, что использовать механизм отрисовки текста GDI, который используется по умолчанию в [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]. Можно переопределить <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> возвращаемое свойство `True`, который указывает, что использовать механизм отрисовки текста GDI +, который используется по умолчанию в Visual Basic .NET 2002 и Visual Basic .NET 2003.  
  
## <a name="configuring-the-application"></a>Настройка приложения  
 Как часть модели приложения Visual Basic <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering> класс предоставляет защищенные свойства для настройки приложения. Эти свойства должны быть установлены в конструкторе реализующего класса.  
  
 В проекте Windows Forms по умолчанию **конструктор проектов** создает код для задания свойств с параметрами конструктора. Свойства используются только в том случае, при запуске приложения; Задание их после запуска приложения не влияет.  
  
|Свойство.|Определяет|Параметр в области "приложение" в конструкторе проектов|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Выполняется ли приложение в одном или нескольких экземпляров приложения.|**Создать приложение одного экземпляра** "флажок"|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Если приложение будет использовать визуальные стили, которые соответствуют Windows XP.|**Включить визуальные стили XP** "флажок"|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Если приложение автоматически сохраняет изменения пользовательских параметров приложения при выходе приложения.|**Сохранять My.Settings при завершении работы** "флажок"|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Что вызывает завершение работы, например когда закрывается начальная форма или при закрытии последней формы приложения.|**Режим завершения работы** списка|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 [Обзор модели приложения в Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 [Страница "Приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
