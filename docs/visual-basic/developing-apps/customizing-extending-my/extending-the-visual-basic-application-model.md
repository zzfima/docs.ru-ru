---
title: Расширение модели приложения Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 46c18ab540c90c4147514685c2acc824755b435f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976864"
---
# <a name="extending-the-visual-basic-application-model"></a>Расширение модели приложения Visual Basic

Вы можете добавить функциональные возможности в модель приложения, переопределив члены `Overridable` класса <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Эта методика позволяет настраивать поведение модели приложения и добавлять вызовы к собственным методам при запуске и завершении работы приложения.

## <a name="visual-overview-of-the-application-model"></a>Визуальный обзор модели приложения

В этом разделе визуально представлена последовательность вызовов функций в модели приложения Visual Basic. В следующем разделе подробно описывается назначение каждой функции.

На следующем рисунке показана последовательность вызовов модели приложения в стандартном Visual Basic Windows Forms приложении. Последовательность начинается, когда процедура `Sub Main` вызывает метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>.

![Схема, показывающая последовательность вызовов модели приложения.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

Visual Basic модель приложения также предоставляет события <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> и <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>. На следующем рисунке показан механизм вызова этих событий.

![Схема, показывающая метод Онстартупнекстинстанце, вызывающий событие Стартупнекстинстанце.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![Схема, показывающая метод Онунхандледексцептион, вызывающий событие UnhandledException.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>Переопределение базовых методов

Метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> определяет порядок, в котором выполняются методы `Application`. По умолчанию `Sub Main` процедура для Windows Forms приложения вызывает метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>.

Если приложение является обычным приложением (приложение с несколькими экземплярами) или первым экземпляром приложения с одним экземпляром, метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> выполняет методы `Overridable` в следующем порядке:

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> По умолчанию этот метод задает стили оформления, стили отображения текста и текущий субъект для основного потока приложения (если приложение использует проверку подлинности Windows) и вызывает `ShowSplashScreen`, если в качестве аргумента командной строки не используется ни `/nosplash`, ни `-nosplash`.

     Последовательность запуска приложения отменяется, если эта функция возвращает `False`. Это может быть полезно, если есть обстоятельства, в которых приложение не должно выполняться.

     Метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> вызывает следующие методы:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Определяет, определен ли в приложении экран-заставка, и, если он есть, отображает экран-заставку в отдельном потоке.

         Метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> содержит код, отображающий экран-заставку по крайней мере для числа миллисекунд, заданных свойством <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>. Чтобы использовать эту функцию, необходимо добавить экран-заставку в приложение с помощью **конструктора проектов** (который задает свойство `My.Application.MinimumSplashScreenDisplayTime` равным двум секундам) или задать свойство `My.Application.MinimumSplashScreenDisplayTime` в методе, который переопределяет метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> или <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Позволяет конструктору создавать код, который инициализирует экран-заставку.

         По умолчанию этот метод не выполняет никаких действий. Если выбрать экран-заставку для приложения в **конструкторе проектов**Visual Basic, конструктор переопределит метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> с помощью метода, который задает для свойства <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> новый экземпляр формы-заставки.

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> Предоставляет точку расширения для вызова события `Startup`. Последовательность запуска приложения останавливается, если эта функция возвращает `False`.

     По умолчанию этот метод вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>. Если обработчик событий задает для свойства <xref:System.ComponentModel.CancelEventArgs.Cancel> аргумента события значение `True`, метод возвращает `False`, чтобы отменить запуск приложения.

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> Предоставляет отправную точку для момента, когда основное приложение будет готово к началу запуска после выполнения инициализации.

     По умолчанию перед входом в цикл обработки сообщений Windows Forms этот метод вызывает `OnCreateMainForm` (для создания главной формы приложения) и `HideSplashScreen` (для закрытия экрана-заставки):

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Предоставляет конструктору способ создания кода, который инициализирует главную форму.

         По умолчанию этот метод не выполняет никаких действий. Однако при выборе главной формы для приложения в **конструкторе проектов**Visual Basic конструктор переопределяет метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> с помощью метода, устанавливающего свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> в новый экземпляр главной формы.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> Если приложение имеет определенный экран-заставку и открыто, этот метод закрывает экран-заставку.

         По умолчанию этот метод закрывает экран-заставку.

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Предоставляет способ настройки работы приложения с одним экземпляром при запуске другого экземпляра приложения.

     По умолчанию этот метод вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>.

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> Предоставляет точку расширения для вызова события `Shutdown`. Этот метод не выполняется, если в основном приложении возникает необработанное исключение.

     По умолчанию этот метод вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>.

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> Выполняется при возникновении необработанного исключения в любом из перечисленных выше методов.

     По умолчанию этот метод вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>, если отладчик не присоединен и приложение обрабатывает событие `UnhandledException`.

 Если приложение является приложением с одним экземпляром и приложение уже запущено, последующий экземпляр приложения вызывает метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> на исходном экземпляре приложения, а затем завершает работу.

 Конструктор <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> вызывает свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>, чтобы определить, какой обработчик отрисовки текста следует использовать для форм приложения. По умолчанию свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> возвращает `False`, что означает, что используется механизм визуализации текста GDI, который используется по умолчанию в Visual Basic 2005 и более поздних версиях. Можно переопределить свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>, чтобы оно возвращало `True`, которое указывает, что используется механизм визуализации текста GDI+, который используется по умолчанию в Visual Basic .NET 2002 и Visual Basic .NET 2003.

## <a name="configuring-the-application"></a>Настройка приложения

 В составе модели приложения Visual Basic класс <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> предоставляет защищенные свойства, которые настраивают приложение. Эти свойства должны быть заданы в конструкторе реализующего класса.

 В проекте Windows Forms по умолчанию **Конструктор проектов** создает код для задания свойств с помощью параметров конструктора. Свойства используются только при запуске приложения. их задание после запуска приложения не оказывает никакого влияния.

|свойство;|Задает|Настройка в области приложений в конструкторе проектов|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Выполняется ли приложение как приложение с одним или несколькими экземплярами.|Флажок " **установить приложение с одним экземпляром** "|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Если приложение будет использовать стили оформления, соответствующие Windows XP.|Флажок " **включить стили Visual XP** "|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Если приложение автоматически сохраняет изменения параметров пользователя приложения при выходе из приложения.|Флажок **сохранить My. Settings при завершении работы**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Что приводит к завершению работы приложения, например при закрытии начальной формы или при закрытии последней формы.|Список **режимов завершения работы**|

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Обзор модели приложения в Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [Страница "Приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
