---
title: "Расширение модели приложения Visual Basic | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 9752cdfa79d3db4c8b07daa95aea2c842e06cc36
ms.lasthandoff: 03/13/2017

---
# <a name="extending-the-visual-basic-application-model"></a>Расширение модели приложения Visual Basic
Можно добавить функциональные возможности модели приложения путем переопределения `Overridable` членов <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>класса.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Этот способ позволяет настроить поведение модели приложения и добавлять вызовы собственных методов, как приложение запускается и завершает работу.  
  
## <a name="visual-overview-of-the-application-model"></a>Общие сведения о модели приложения  
 В этом разделе наглядно представлена последовательность вызовов функций в модели приложения Visual Basic. В следующем разделе описывается назначение каждой функции подробно.  
  
 Приведенный ниже рисунок показывает последовательность вызовов модели приложения в обычном приложении Windows Forms Visual Basic. Последовательность начинается, когда `Sub Main` вызовы процедур <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>метод.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
 ![Модель приложения Visual Basic – Запуск](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 Модель приложения Visual Basic также предоставляет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>и <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>события.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> На следующем рисунке показан механизм возникновения этих событий.  
  
 ![Модель приложения Visual Basic--Далее экземпляр](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Необработанное исключение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>Переопределение базовых методов  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>Метод определяет порядок, в котором `Application` выполнения методов.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> По умолчанию `Sub Main` процедура для приложения Windows Forms вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>метод.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
 Если приложение является обычного приложения (приложения для нескольких экземпляров), или первый экземпляр приложения с одним экземпляром, <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>выполняет метод `Overridable` методы в следующем порядке:</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> По умолчанию этот метод устанавливает стили оформления, стили отображения текста и текущего участника для основного потока приложения (если приложение использует проверку подлинности Windows) и вызывает метод `ShowSplashScreen` Если ни одна из `/nosplash` , ни `-nosplash` используется в качестве аргумента командной строки.  
  
     Последовательность запуска приложения отменяется, если эта функция возвращает `False`. Это может быть полезно, если существуют ситуации, в которых приложение не запускается.  
  
     <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>Метод вызывает следующие методы:</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Определяет, имеет ли приложение заставку и если это так, отображает заставку в отдельном потоке.  
  
         <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>Метод содержит код, который отображает заставку экрана для менее указанного числа миллисекунд <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>свойство.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Чтобы использовать эту функциональность, необходимо добавить экрана-заставки для приложения с помощью **конструктора проектов** (какие наборы `My.Application.MinimumSplashScreenDisplayTime` свойство две секунды), или задать `My.Application.MinimumSplashScreenDisplayTime` свойство в методе, который переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>или <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>метод.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Позволяет разработчику создавать код, инициализирующий экран-заставка.  
  
         По умолчанию этот метод не выполняет никаких действий. Если выбрать экран-заставку для приложения в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **конструктора проектов**, конструктор переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>метод с методом, который задает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>Свойства новый экземпляр формы экрана заставки.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> Предоставляет точку расширения для вызова `Startup` события. Последовательность запуска приложения останавливается, если эта функция возвращает `False`.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>событий.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Если обработчик событий задает @System.ComponentModel.CancelEventArgs.Cancel свойство аргумента события для `True`, метод возвращает `False` для отмены запуска приложения.  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> Предоставляет начальную точку для когда основное приложение будет готово к началу запуска после выполнения инициализации.  
  
     Перед переходом в цикл обработки сообщений Windows Forms, вызывает этот метод `OnCreateMainForm` (для создания главной формы приложения) и `HideSplashScreen` (для закрытия заставки) методы:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Позволяет разработчику создавать код инициализации главной формы.  
  
         По умолчанию этот метод не выполняет никаких действий. Однако при выборе главной формы приложения в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **конструктора проектов**, конструктор переопределяет <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>метод с методом, который задает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>Свойства новый экземпляр главной формы.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> Если приложение имеет определенную заставку, и она открыта, этот метод закрывает заставку.  
  
         По умолчанию этот метод закрывает заставку.  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Предоставляет способ настраивать поведение приложения при запуске другого экземпляра приложения.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>событий.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> Предоставляет точку расширения для вызова `Shutdown` события. Этот метод не выполняется при возникновении необработанного исключения в главном приложении.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>событий.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> Выполняется при возникновении необработанного исключения в любом из перечисленных выше методов.  
  
     По умолчанию этот метод вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>, пока не присоединен отладчик и приложение обрабатывает событие `UnhandledException` событий.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
  
 Если приложение является приложением одним экземпляром, и приложение уже запущено, последующий экземпляр приложения вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>метод на исходный экземпляр приложения, а затем завершает работу.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>  
  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>Конструктор вызывает <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>свойство, чтобы определить, какой механизм отрисовки текста для форм приложения.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> По умолчанию <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>возвращает `False`, указывающее, использовать механизм визуализации текста GDI, который используется по умолчанию в [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)].</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> Можно переопределить <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>возвращаемое свойство `True`, который указывает, что использовать механизм визуализации текста GDI +, используемом по умолчанию в Visual Basic .NET 2002 и Visual Basic .NET 2003.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>  
  
## <a name="configuring-the-application"></a>Настройка приложения  
 В составе [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] модель приложения <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>класс предоставляет защищенные свойства, предназначенные для настройки приложения.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Эти свойства должны быть установлены в конструкторе реализующего класса.  
  
 В проекте Windows Forms по умолчанию **конструктора проектов** создает код для задания свойств с параметрами конструктора. Свойства используются только при запуске приложения; Установка их после запуска приложения не имеет эффекта.  
  
|Свойство|Определяет|Параметр в области приложения, в конструкторе проектов|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Выполняется ли приложение в одном или нескольких экземпляров приложения.|**Создать приложение одного экземпляра** флажок|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Если приложение будет использовать визуальные стили, которые соответствуют Windows XP.|**Включить визуальные стили XP** флажок|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Если приложение автоматически сохраняет изменения пользовательских параметров приложения, при выходе из приложения.|**Сохранять My.Settings при завершении работы** флажок|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Что приводит к завершению работы, например, при закрытии формы запуска или при закрытии последней формы приложения.|**Режим завершения работы** список|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Обзор модели приложения Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)   
 [Страница "Приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)
