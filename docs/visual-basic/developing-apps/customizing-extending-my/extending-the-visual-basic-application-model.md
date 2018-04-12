---
title: Расширение модели приложения Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 15e6ea1a8b2df0b8ed1b84abceee9e6be2c556f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="extending-the-visual-basic-application-model"></a>Расширение модели приложения Visual Basic
Можно добавить функциональные возможности модели приложения путем переопределения `Overridable` члены <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> класса. Этот метод позволяет настроить поведение модели приложения и добавлять вызовы собственных методов, как приложение запускается и завершает работу.  
  
## <a name="visual-overview-of-the-application-model"></a>Общие сведения о модели приложения  
 В этом разделе наглядно представлена последовательность вызовов функций в модели приложения Visual Basic. В следующем разделе описывается назначение каждой функции подробно.  
  
 Приведенный ниже рисунок показывает последовательность вызовов модели приложения в обычных приложениях Windows Forms Visual Basic. Последовательность начинается, когда `Sub Main` вызовы процедур <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> метод.  
  
 ![Модель приложения Visual Basic &#45; &#45; Запустите](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 Модель приложения Visual Basic также предоставляет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> и <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> события. На следующем рисунке показан механизм возникновения этих событий.  
  
 ![Модель приложения Visual Basic &#45; &#45; Затем экземпляр](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Необработанное исключение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>Переопределение базовых методов  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Метод определяет порядок, в котором `Application` выполнения методов. По умолчанию `Sub Main` процедура для приложения Windows Forms вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> метод.  
  
 Если приложение является обычного приложения (приложения для нескольких экземпляров) или первый экземпляр приложения с одним экземпляром, <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> выполняет метод `Overridable` методы в следующем порядке:  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. По умолчанию, этот метод устанавливает стили оформления, стили отображения текста и текущего участника для основного потока приложения (если приложение использует проверку подлинности Windows) и вызывает метод `ShowSplashScreen` Если ни одна из `/nosplash` , ни `-nosplash` используется в качестве аргумент командной строки.  
  
     Последовательность запуска приложения отменяется, если эта функция возвращает `False`. Это может быть полезно, если существуют ситуации, в которых не следует запускать приложения.  
  
     <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Метод вызывает следующие методы:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. Определяет, имеет ли приложение заставку и если это так, отображает заставку в отдельном потоке.  
  
         <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Метод содержит код, отображающий splash экрана для по крайней мере указанного числа миллисекунд <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> свойство. Для применения этих функциональных возможностей, необходимо добавить экран-заставка приложения с помощью **конструктора проектов** (которая задает `My.Application.MinimumSplashScreenDisplayTime` свойство две секунды), или задать `My.Application.MinimumSplashScreenDisplayTime` свойства в методе, который переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> или <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> метод. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Позволяет разработчику создавать код, который инициализирует экран-заставка.  
  
         По умолчанию этот метод не выполняет никаких действий. Если выбрать экран-заставку для приложения в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] **конструктора проектов**, конструктор переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> метод с помощью метода, который задает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> свойства новый экземпляр экрана заставки форма.  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. Предоставляет точку расширения для вызова `Startup` событий. Последовательность запуска приложения останавливается, если эта функция возвращает `False`.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> событий. Если обработчик событий устанавливает <xref:System.ComponentModel.CancelEventArgs.Cancel> свойство аргумента события в `True`, метод возвращает `False` для отмены запуска приложения.  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. Предоставляет начальную точку для при основное приложение будет готово к началу запуска после выполнения инициализации.  
  
     Перед переходом в цикл обработки сообщений Windows Forms, вызывает этот метод `OnCreateMainForm` (для создания главной формы приложения) и `HideSplashScreen` (чтобы закрыть экран-заставка) методы:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. Позволяет разработчику создавать код, который инициализирует главной формы.  
  
         По умолчанию этот метод не выполняет никаких действий. Тем не менее, при выборе главной формы приложения в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] **конструктора проектов**, конструктор переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> метода, задает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> свойство к новому экземпляру главной формы .  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. Если приложение имеет определенную заставку, и он открыт, этот метод закрывает экран-заставка.  
  
         По умолчанию этот метод закрывает экран-заставка.  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. Позволяет настроить поведение приложения при запуске другого экземпляра приложения.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> событий.  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. Предоставляет точку расширения для вызова `Shutdown` событий. Этот метод не выполняется при возникновении необработанного исключения в основное приложение.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> событий.  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. Выполняется при возникновении необработанного исключения в любом из перечисленных выше методов.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> при условии, что отладчик не присоединен, и приложение обрабатывает событие `UnhandledException` событий.  
  
 Если приложение является приложением экземпляра, и приложение уже запущено, последующий экземпляр приложения вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> метод на исходный экземпляр приложения, а затем завершает работу.  
 
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> Вызовы конструктора <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> свойство, чтобы определить, какой механизм отрисовки текста для форм приложения. По умолчанию <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> возвращает `False`, указывающее, что использовать механизм отрисовки текста GDI, которая используется по умолчанию в [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]. Можно переопределить <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> возвращаемое свойство `True`, который указывает, что использовать механизм отрисовки текста GDI +, используемого по умолчанию в Visual Basic .NET 2002 и Visual Basic .NET 2003.  
  
## <a name="configuring-the-application"></a>Настройка приложения  
 В составе [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] модель приложения <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering> класс предоставляет защищенные свойства для настройки приложения. Эти свойства должны быть установлены в конструкторе реализующего класса.  
  
 В проекте Windows Forms по умолчанию **конструктора проектов** создает код для задания свойств с параметрами конструктора. Свойства используются только при запуске приложения; Установка их после запуска приложения не имеет эффекта.  
  
|Свойство|Определяет|На панели приложения в конструкторе проектов|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Выполняется ли приложение в одном или нескольких экземпляров приложения.|**Создать приложение одного экземпляра** флажок|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Если приложение будет использовать визуальные стили, которые соответствуют Windows XP.|**Включить визуальные стили XP** флажок|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Если приложение автоматически сохраняет изменения пользовательских параметров приложения при завершении работы приложения.|**Сохранять My.Settings при завершении работы** флажок|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|То, что приводит к завершению работы, например, когда закрывается начальная форма или когда закрывается последняя форма приложения.|**Режим завершения работы** списка|  
  
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
