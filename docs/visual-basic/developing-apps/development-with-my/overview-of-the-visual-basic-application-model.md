---
title: "Обзор модели приложения в Visual Basic | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Application - объект, Visual Basic - модель приложения"
  - "Visual Basic - модель приложения"
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Обзор модели приложения в Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет четко определенную модель управления поведением приложений Windows Forms: модель приложения [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Эта модель включает события для управления запуском и завершением работы приложения, а также события для перехвата необработанных исключений.  Она также поддерживает разработку приложений, допускающих одновременное выполнение только одного своего экземпляра.  Модель приложения является расширяемой, поэтому разработчики могут настраивать переопределяемые методы модели.  
  
## Использование модели приложений  
 Типичное приложение выполняет некоторые действия при запуске и завершении работы.  Например, при запуске приложение может отображать экран\-заставку, подключаться к базе данных, загружать сохраненные сведения о состоянии и т.д.  При завершении работы приложение может закрывать подключения к базе данных, сохранять текущее состояние и т.д.  Кроме того, приложение может выполнить определенный код при непредвиденном завершении работы, например в случае возникновения необработанного исключения.  
  
 Модель приложения [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] упрощает создание *приложения, допускающего одновременное выполнение только одной копии*.  Такие приложения отличаются от обычных приложений тем, что только один экземпляр приложения может выполняться в один момент времени.  При попытке запуска другого экземпляра такого приложения первоначальный экземпляр уведомляется об этом посредством события `StartupNextInstance`.  Уведомление содержит аргументы командной строки последующего экземпляра.  Последующий экземпляр приложения затем закрывается, прежде чем будут выполнены любые действия по инициализации.  
  
 При запуске приложение, допускающее одновременное выполнение только одной копии, проверяет, является ли оно первым или последующим экземпляром приложения.  
  
-   Если это первый экземпляр, оно запускается обычным образом.  
  
-   Если выполняется первый экземпляр приложения, то при попытке запуска последующих экземпляров приложение будет вести себя по\-другому.  При последующих попытках запуска первый экземпляр уведомляется об аргументах командной строки, следующий экземпляр сразу же завершает работу.  Первый экземпляр обрабатывает событие `StartupNextInstance`, чтобы определить аргументы командной строки последующих экземпляров, а затем продолжает работу.  
  
     На рисунке ниже показано, как последующий экземпляр уведомляет первый экземпляр.  
  
     ![Изображение приложения одного экземпляра](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 Обработка события `StartupNextInstance` позволяет управлять поведением приложения, допускающего одновременное выполнение только одной копии.  Например, приложение Microsoft Outlook обычно запускается в виде приложения, допускающего одновременное выполнение только одной копии. Если приложение Outlook уже выполняется, то при попытке запуска другого экземпляра фокус переходит в исходный экземпляр, а другой экземпляр не открывается.  
  
## События в модели приложения  
 В модели приложения предусмотрены следующие события.  
  
-   **Запуск приложения**.  При запуске приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>.  При обработке этого события можно добавить код, который инициализирует приложение до загрузки главной формы.  Событие `Startup` также предоставляет возможность при необходимости отменить выполнение приложения на этом этапе процесса загрузки.  
  
     Можно настроить приложение для отображения заставки при выполнении кода запуска приложения.  По умолчанию модель приложения отключает заставку при использовании аргумента командной строки `/nosplash` или `-nosplash`.  
  
-   **Приложения, допускающие одновременное выполнение только одной своей копии**.  При запуске последующего экземпляра приложения, допускающего одновременное выполнение только одного своего экземпляра, создается событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>.  Событие передает аргументы командной строки последующего экземпляра.  
  
-   **Необработанные исключения**.  При обнаружении необработанного исключения приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  Обработчик этого события может проверить исключение и определить, следует ли продолжить выполнение.  
  
     Событие `UnhandledException` не возникает в некоторых случаях.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
-   **Изменения сетевого подключения**.  При изменении доступности сети компьютера приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
     В некоторых случаях событие `NetworkAvailabilityChanged` не создается.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
-   **Завершение работы приложения**.  Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> для оповещения о том, что оно собирается завершить работу.  В этом обработчике событий можно убедиться в выполнении необходимых операций приложения, таких как закрытие и сохранение.  Можно настроить приложение на завершение работы при закрытии главной формы или при закрытии всех форм.  
  
## Доступность  
 По умолчанию модель приложения [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] доступна в проектах Windows Forms.  Если приложение настроено на использование другого автоматически запускаемого объекта или запуск кода приложения с пользовательской процедурой `Sub Main`, то может потребоваться предоставить объекту или классу реализацию класса <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> для использования модели приложения.  Сведения об изменении автоматически запускаемого объекта см. в разделе [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)