---
title: "Пошаговое руководство: Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "функциональные возможности времени разработки, Windows Forms"
  - "DocumentDesigner - класс [Windows Forms]"
  - "пошаговые руководства [Windows Forms], элементы управления"
  - "элементы управления Windows Forms, создание"
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
caps.latest.revision: 46
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 46
---
# Пошаговое руководство: Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки
При создании пользовательского элемента управления можно создать пользовательский конструктор.  
  
 В этом пошаговом руководстве описывается создание пользовательского конструктора для пользовательского элемента управления.  Будет реализован тип `MarqueeControl` и связанный класс конструктора под названием `MarqueeControlRootDesigner`.  
  
 Тип `MarqueeControl` реализует отображение текста, похожее на бегущую строку, с анимацией огней и мигающим текстом.  
  
 Конструктор этого элемента управления взаимодействует со средой разработки.  С помощью пользовательского конструктора можно создать пользовательскую реализацию `MarqueeControl` с различными сочетаниями анимации огней и мигающим текстом.  Полученный элемент управления можно использовать в форме, как и любой другой элемент управления Windows Forms.  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание проекта  
  
-   Создание проекта библиотеки элемента управления  
  
-   Создание ссылок для проекта пользовательского элемента управления  
  
-   Определение пользовательского элемента управления и его конструктора  
  
-   Создание экземпляра пользовательского элемента управления  
  
-   Настройка проекта для отладки во время разработки  
  
-   Реализация пользовательского элемента управления  
  
-   Создание дочернего элемента управления для пользовательского элемента управления  
  
-   Создание дочернего элемента управления MarqueeBorder  
  
-   Создание пользовательского конструктора для создания тени и фильтрации свойств  
  
-   Обработка изменений компонентов  
  
-   Добавление команд конструктора в пользовательский конструктор  
  
-   Создание пользовательского редактора UITypeEditor  
  
-   Тестирование элемента управления в конструкторе  
  
 По завершении работы элемент управления будет выглядеть примерно так, как показано на рисунке:  
  
 ![Возможный порядок MarqueeControl](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")  
  
 Полный пример кода см. в разделе [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена Visual Studio.  
  
## Создание проекта  
 Для начала следует создать проект приложения.  Этот проект будет использован для создания приложения, в котором будет размещен элемент управления.  
  
#### Создание проекта  
  
-   Создать проект приложения Windows Forms с именем "MarqueeControlTest". Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## Создание проекта библиотеки элемента управления  
 На следующем этапе необходимо создать проект библиотеки элементов управления.  Мы создадим пользовательский элемент управления и связанный с ним пользовательский конструктор.  
  
#### Создание проекта библиотеки элементов управления  
  
1.  Добавьте в решение проект "Библиотека элементов управления Windows Forms".  Назовите проект "MarqueeControlLibrary".  
  
2.  В **обозревателе решений** удалите элемент управления по умолчанию для этого проекта, удалив исходный файл "UserControl1.cs" или "UserControl1.vb" в зависимости от выбранного языка.  Дополнительные сведения см. в разделе [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/ru-ru/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Добавьте новый элемент <xref:System.Windows.Forms.UserControl> в проект `MarqueeControlLibrary`.  Назовите новый исходный файл "MarqueeControl".  
  
4.  С помощью **обозревателя решений** создайте новую папку в проекте `MarqueeControlLibrary`.  Дополнительные сведения см. в разделе [NIB:How to: Add New Project Items](http://msdn.microsoft.com/ru-ru/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  Назовите новую папку "Разработка".  
  
5.  Щелкните правой кнопкой мыши папку **Разработка** и добавьте новый класс.  Назовите новый исходный файл "MarqueeControlRootDesigner".  
  
6.  Потребуется использовать типы из сборки System.Design, поэтому добавьте данную ссылку в проект `MarqueeControlLibrary`.  
  
    > [!NOTE]
    >  Чтобы использовать сборку System.Design, в проекте должна использоваться полная версия .NET Framework, а не клиентский профиль .NET Framework.  Чтобы изменить требуемую версию .NET Framework, обратитесь к разделу [Практическое руководство. Определение целевой версии .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
## Создание ссылок для проекта пользовательского элемента управления  
 Проект `MarqueeControlTest` будет использован для тестирования пользовательского элемента управления.  Тестовый проект получит данные о пользовательском элементе управления при добавлении ссылки на проект в сборку `MarqueeControlLibrary`.  
  
#### Создание ссылок для проекта пользовательского элемента управления  
  
-   В проекте `MarqueeControlTest` добавьте ссылку на сборку `MarqueeControlLibrary`.  Убедитесь, что используется вкладка **Проекты** в окне **Добавить ссылку** вместо создания прямой ссылки на сборку `MarqueeControlLibrary`.  
  
## Определение пользовательского элемента управления и его конструктора  
 Пользовательский элемент управления будет производным от класса <xref:System.Windows.Forms.UserControl>.  То позволит элементу управления содержать другие элементы управления; а также обеспечит широкий набор функций по умолчанию.  
  
 Для пользовательского элемента управления будет реализован собственный конструктор.  Это позволит создать уникальный интерфейс разработки, предназначенный только для вашего элемента управления.  
  
 Для связи элемента управления с конструктором служит класс <xref:System.ComponentModel.DesignerAttribute>.  Мы разрабатываем все функции пользовательского элемента управления во время разработки, поэтому пользовательский конструктор будет реализовывать интерфейс <xref:System.ComponentModel.Design.IRootDesigner>.  
  
#### Определение пользовательского элемента управления и его конструктора  
  
1.  Откройте файл исходного кода `MarqueeControl` в **Редакторе кода**.  В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  Добавьте <xref:System.ComponentModel.DesignerAttribute> в объявление класса `MarqueeControl`.  При этом элемент управления связывается со своим конструктором.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  Откройте файл исходного кода `MarqueeControlRootDesigner` в **Редакторе кода**.  В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  Измените объявление `MarqueeControlRootDesigner` для наследования класса <xref:System.Windows.Forms.Design.DocumentDesigner>.  Примените <xref:System.ComponentModel.ToolboxItemFilterAttribute> для определения взаимодействия конструктора с **панелью элементов**.  
  
     **Примечание.** Определение класса `MarqueeControlRootDesigner` существует в пространстве имен "MarqueeControlLibrary.Design". Это объявление помещает конструктор в отдельное пространство имен, предназначенное для типов, связанных с конструктором.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  Определите конструктор для класса `MarqueeControlRootDesigner`.  Вставьте инструкцию <xref:System.Diagnostics.Trace.WriteLine%2A> в текст конструктора.  Она будет использована для отладки.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## Создание экземпляра пользовательского элемента управления  
 Для проверки работы пользовательского элемента управления во время разработки поместите экземпляр элемента управления в форму в проекте `MarqueeControlTest`.  
  
#### Создание экземпляра пользовательского элемента управления  
  
1.  Добавьте новый элемент <xref:System.Windows.Forms.UserControl> в проект `MarqueeControlTest`.  Назовите новый исходный файл "DemoMarqueeControl".  
  
2.  Откройте файл `DemoMarqueeControl` в **Редакторе кода**.  В верхней части файла импортируйте пространство имен `MarqueeControlLibrary`.  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  Измените объявление `DemoMarqueeControl` для наследования класса `MarqueeControl`.  
  
2.  Выполните построение проекта.  
  
3.  Откройте форму `Form1` в конструкторе Windows Forms.  
  
4.  Найдите вкладку **Компоненты MarqueeControlTest** в **панели элементов** и откройте ее.  Перетащите `DemoMarqueeControl` из **панели элементов** на свою форму.  
  
5.  Выполните построение проекта.  
  
## Настройка проекта для отладки во время разработки  
 При создании пользовательской среды разработки часто приходится отлаживать элементы управления и компоненты.  Существует простой способ настроить проект для отладки во время разработки.  Дополнительные сведения см. в разделе [Пример. Отладка пользовательских элементов управления Windows Forms во время разработки](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
#### Для настройки проекта для отладки во время разработки выполните следующие действия.  
  
1.  Щелкните правой кнопкой мыши проект `MarqueeControlLibrary` и выберите **Свойства**.  
  
2.  В окне "Страницы свойств MarqueeControlLibrary" выберите страницу **Отладка**.  
  
3.  В разделе **Действие при запуске** выберите **Запуск внешней программы**.  Отладка будет выполняться в отдельном экземпляре Visual Studio, поэтому нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) для выбора Visual Studio IDE.  Имя исполняемого файла — devenv.exe, и его путь по умолчанию — "%ProgramFiles%\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe".  
  
4.  Нажмите кнопку ОК, чтобы закрыть диалоговое окно.  
  
5.  Щелкните правой кнопкой мыши проект `MarqueeControlLibrary` и выберите "Установить как проект для запуска", чтобы включить конфигурацию отладки.  
  
## Контрольная точка  
 Теперь все готово к отладке поведения пользовательского элемента управления.  Убедившись в правильной настройке среды отладки можно проверить связь между пользовательским элементом управления и конструктором.  
  
#### Для тестирования среды отладки и связи конструктора  
  
1.  Откройте исходный файл `MarqueeControlRootDesigner` в **редакторе кода** и поместите точку останова на инструкцию <xref:System.Diagnostics.Trace.WriteLine%2A>.  
  
2.  Нажмите клавишу F5 для запуска сеанса отладки.  Обратите внимание, что создается новый экземпляр Visual Studio.  
  
3.  В новом экземпляре Visual Studio откройте решение "MarqueeControlTest".  Его можно найти, выбрав **Последние проекты** в меню **Файл**.  Файл решения "MarqueeControlTest.sln" будет указан как самый последний.  
  
4.  Откройте `DemoMarqueeControl` в конструкторе.  Обратите внимание, что при изменении отладочный экземпляр Visual Studio получает фокус, а выполнение останавливается в точке останова.  Нажмите клавишу F5 для продолжения отладки.  
  
 Теперь все готово для разработки и отладки пользовательского элемента управления и связанного с ним конструктора.  В оставшейся части этого пошагового руководства рассматриваются подробности реализации функций элемента управления и конструктора.  
  
## Реализация пользовательского элемента управления  
 Элемент управления `MarqueeControl` представляет собой немного измененный элемент управления <xref:System.Windows.Forms.UserControl>.  Он раскрывает два метода: `Start` \(запуск анимации бегущей строки\) и `Stop` \(остановка анимации\).  Элемент управления `MarqueeControl` содержит дочерние элементы управления, реализующие интерфейс `IMarqueeWidget`, поэтому `Start` и `Stop` перечисляют каждый дочерний элемент управления и вызывают соответственно методы `StartMarquee` и `StopMarquee` для каждого дочернего элемента управления, реализующего `IMarqueeWidget`.  
  
 Внешний вид элементов управления `MarqueeBorder` и `MarqueeText` зависит от макета, поэтому `MarqueeControl` заменяет метод <xref:System.Windows.Forms.Control.OnLayout%2A> и вызывает <xref:System.Windows.Forms.Control.PerformLayout%2A> для дочерних элементов управления этого типа.  
  
 Это расширение настроек `MarqueeControl`.  Функции времени выполнения реализованы элементами управления `MarqueeBorder` и `MarqueeText`, функции времени разработки реализованы классами `MarqueeBorderDesigner` и `MarqueeControlRootDesigner`.  
  
#### Реализация пользовательского элемента управления  
  
1.  Откройте файл исходного кода `MarqueeControl` в **Редакторе кода**.  Реализуйте методы `Start` и `Stop`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  Переопределите метод <xref:System.Windows.Forms.Control.OnLayout%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## Создание дочернего элемента управления для пользовательского элемента управления  
 В элементе `MarqueeControl` будет два дочерних элемента управления: `MarqueeBorder` и `MarqueeText`.  
  
-   `MarqueeBorder`: этот элемент управления рисует "огни" вдоль краев.  Огни по очереди мигают, поэтому создается впечатление, что они движутся вдоль краев.  Скорость мигания огней зависит от свойства `UpdatePeriod`.  Несколько других пользовательских свойств определяют другие характеристики внешнего виде элемента управления.  Два метода, `StartMarquee` и `StopMarquee`, управляют запуском и остановкой анимации.  
  
-   `MarqueeText`: этот элемент управления рисует мигающую строку.  Как и для элемента управления `MarqueeBorder`, скорость мигания текста определяется свойством `UpdatePeriod`.  Элемент управления `MarqueeText` также имеет методы `StartMarquee` и `StopMarquee`, аналогично элементу управления `MarqueeBorder`.  
  
 Во время разработки конструктор `MarqueeControlRootDesigner` позволяет добавить эти два элемента управления в `MarqueeControl` в любом сочетании.  
  
 Общие свойства этих двух элементов управления представлены в интерфейсе `IMarqueeWidget`.  Это позволяет элементу `MarqueeControl` определять все дочерние элементы управления и обрабатывать их особым образом.  
  
 Для реализации анимации используем объекты <xref:System.ComponentModel.BackgroundWorker> из пространства имен <xref:System.ComponentModel?displayProperty=fullName>.  Можно использовать объекты <xref:System.Windows.Forms.Timer>, но при наличии слишком многих объектов `IMarqueeWidget` один поток пользовательского интерфейса может не справиться с анимацией.  
  
#### Создание дочернего элемента управления для пользовательского элемента управления  
  
1.  Добавьте новый класс в проект `MarqueeControlLibrary`.  Назовите новый исходный файл "IMarqueeWidget".  
  
2.  Откройте файл `IMarqueeWidget` в **редакторе кода** и замените объявление с `class` на `interface`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  Добавьте следующий код в интерфейс `IMarqueeWidget` для открытия двух методов и свойства, управляющих анимацией бегущей строки:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  Добавьте новый элемент **Пользовательский элемент управления** в проект `MarqueeControlLibrary`.  Назовите новый исходный файл "MarqueeText".  
  
5.  Перетащите компонент <xref:System.ComponentModel.BackgroundWorker> из **панели элементов** в элемент управления `MarqueeText`.  Этот компонент обеспечит асинхронное обновление элемента управления `MarqueeText`.  
  
6.  В окне "Свойства" установите для компонента <xref:System.ComponentModel.BackgroundWorker> свойства `WorkerReportsProgess` и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> равными `true`.  Эти параметры позволят компоненту <xref:System.ComponentModel.BackgroundWorker> периодически создавать событие <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> и отменять асинхронное обновление.  Дополнительные сведения см. в разделе [Компонент BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
7.  Откройте файл исходного кода `MarqueeText` в **Редакторе кода**.  В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  Измените объявление `MarqueeText` для наследования <xref:System.Windows.Forms.Label> и для реализации интерфейса `IMarqueeWidget`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. Объявите переменные экземпляра, соответствующие этим свойствам, и инициализируйте их в конструкторе.  Поле `isLit` определяет, следует ли прорисовывать текст цветом, определяемым свойством `LightColor`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. Реализуйте интерфейс `IMarqueeWidget`.  
  
     Методы `StartMarquee` и `StopMarquee` вызывают для компонента <xref:System.ComponentModel.BackgroundWorker> методы <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> и <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> для запуска и остановки анимации.  
  
     Атрибуты <xref:System.ComponentModel.CategoryAttribute.Category%2A> и <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> применяются к свойству `UpdatePeriod`, поэтому оно отображается в пользовательском разделе окна "Свойства" под названием "Marquee".  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. Реализуйте методы доступа к свойству.  Клиентам будут предоставлены два свойства: `LightColor` и `DarkColor`.  Атрибуты <xref:System.ComponentModel.CategoryAttribute.Category%2A> и <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> применяются к этим свойствам, поэтому они отображаются в пользовательском разделе окна "Свойства" под названием "Marquee".  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. Реализуйте обработчики для событий <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> компонента <xref:System.ComponentModel.BackgroundWorker>.  
  
     Обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork> находится в состоянии ожидания в течение числа миллисекунд, указанного в `UpdatePeriod`, затем создает событие <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> до момента, когда код останавливает анимацию путем вызова <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     Обработчик событий <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> переключает светлое и темное состояние текста, создавая впечатление мигающего текста.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. Переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A> для включения анимации.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. Нажать клавишу F6 для построения решения.  
  
## Создание дочернего элемента управления MarqueeBorder  
 Элемент управления `MarqueeBorder` немного сложнее элемента управления `MarqueeText`.  У него больше свойств, а анимация в <xref:System.Windows.Forms.Control.OnPaint%2A> несколько сложнее.  В принципе, он похож на элемент управления `MarqueeText`.  
  
 Элемент управления `MarqueeBorder` может иметь дочерние элементы управления, поэтому он должен получать данные о событиях <xref:System.Windows.Forms.Control.Layout>.  
  
#### Создание дочернего элемента управления MarqueeBorder  
  
1.  Добавьте новый элемент **Пользовательский элемент управления** в проект `MarqueeControlLibrary`.  Назовите новый исходный файл "MarqueeBorder".  
  
2.  Перетащите компонент <xref:System.ComponentModel.BackgroundWorker> из **панели элементов** в элемент управления `MarqueeBorder`.  Этот компонент обеспечит асинхронное обновление элемента управления `MarqueeBorder`.  
  
3.  В окне "Свойства" установите для компонента <xref:System.ComponentModel.BackgroundWorker> свойства `WorkerReportsProgess` и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> равными `true`.  Эти параметры позволят компоненту <xref:System.ComponentModel.BackgroundWorker> периодически создавать событие <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> и отменять асинхронное обновление.  Дополнительные сведения см. в разделе [Компонент BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
4.  В окне "Свойства" нажмите кнопку "События".  Присоедините обработчики для событий <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.  
  
5.  Откройте файл исходного кода `MarqueeBorder` в **Редакторе кода**.  В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  Измените объявление `MarqueeBorder` для наследования <xref:System.Windows.Forms.Panel> и для реализации интерфейса `IMarqueeWidget`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  Объявите два перечисления для управлением состояния элемента управления `MarqueeBorder`: `MarqueeSpinDirection`, определяющее направление "движения" огней вдоль границы, и `MarqueeLightShape`, определяющее форму огней \(квадратную или круглую\).  Поместите эти объявление перед объявлением класса `MarqueeBorder`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  Объявите переменные экземпляра, соответствующие этим свойствам, и инициализируйте их в конструкторе.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. Реализуйте интерфейс `IMarqueeWidget`.  
  
     Методы `StartMarquee` и `StopMarquee` вызывают для компонента <xref:System.ComponentModel.BackgroundWorker> методы <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> и <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> для запуска и остановки анимации.  
  
     Элемент управления `MarqueeBorder` может содержать дочерние элементы управления, поэтому метод `StartMarquee` перечисляет все дочерние элементы управления и вызывает `StartMarquee` для элементов, реализующих `IMarqueeWidget`.  Метод `StopMarquee` обладает схожей реализацией.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. Реализуйте методы доступа к свойству.  Внешний вид элемента управления `MarqueeBorder` зависит от нескольких свойств.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. Реализуйте обработчики для событий <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> компонента <xref:System.ComponentModel.BackgroundWorker>.  
  
     Обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork> находится в состоянии ожидания в течение числа миллисекунд, указанного в `UpdatePeriod`, затем создает событие <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> до момента, когда код останавливает анимацию путем вызова <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     Обработчик событий <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> изменяет положение "основного" огня, на основании которого определяется состояние \("светлое" или "темное"\) других огней, и вызывает метод <xref:System.Windows.Forms.Control.Refresh%2A> для повторной прорисовки элемента управления.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. Реализуйте вспомогательные методы `IsLit` и `DrawLight`.  
  
     Метод `IsLit` определяет цвет огня в определенном положении.  "Зажженные" огни рисуются с помощью цвета, определяемого свойством `LightColor`, а "погасшие" огни рисуются с помощью цвета, определяемого свойством `DarkColor`.  
  
     Метод `DrawLight` изображает огонь с использованием соответствующего цвета, фигуры и положения.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. Переопределите методы <xref:System.Windows.Forms.Control.OnLayout%2A> и <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
     Метод <xref:System.Windows.Forms.Control.OnPaint%2A> рисует огни вдоль границ элементов управления `MarqueeBorder`.  
  
     Метод <xref:System.Windows.Forms.Control.OnPaint%2A> зависит от размеров элемента управления `MarqueeBorder`, поэтому этот метод нужно вызывать при каждом изменении макета.  Для этого переопределите <xref:System.Windows.Forms.Control.OnLayout%2A> и вызовите <xref:System.Windows.Forms.Control.Refresh%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## Создание пользовательского конструктора для создания тени и фильтрации свойств  
 Класс `MarqueeControlRootDesigner` обеспечивает реализацию корневого конструктора.  В дополнение к этому конструктору, работающему над `MarqueeControl`, потребуется пользовательский конструктор, связанный с элементом управления `MarqueeBorder`.  Этот конструктор поддерживает настраиваемые действия в соответствии с контекстом пользовательского корневого конструктора.  
  
 В частности, конструктор `MarqueeBorderDesigner` "затенит" и отфильтрует определенные свойства элемента управления `MarqueeBorder`, изменив их взаимодействие со средой разработки.  
  
 "Затенением" называется перехват вызовов к методу доступа свойства компонента. "Затенение" позволяет отслеживать установленное пользователем значение и при необходимости передавать это значение в создаваемый компонент.  
  
 Например, свойства <xref:System.Windows.Forms.Control.Visible%2A> и <xref:System.Windows.Forms.Control.Enabled%2A> будут затенены конструктором `MarqueeBorderDesigner`, который не позволяет пользователю сделать элемент управления `MarqueeBorder` невидимым или отключить его при разработке.  
  
 Конструкторы также могут добавлять и удалять свойства.  В данном примере свойство <xref:System.Windows.Forms.Control.Padding%2A> будет удалено на этапе разработки, поскольку элемент управления `MarqueeBorder` программно указывает отступ на основе размера огней, указанных свойством `LightSize`.  
  
 Базовый класс для `MarqueeBorderDesigner` — <xref:System.ComponentModel.Design.ComponentDesigner>, он обладает методами, которые могут изменять атрибуты, свойства и события, раскрытые элементом управления во время разработки:  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 При изменении общего интерфейса компонента с помощью этих методов необходимо соблюдать следующие правила.  
  
-   Добавление и удаление элементов допускается только в методах `PreFilter`.  
  
-   Изменение существующих элементов допускается только в методах `PostFilter`.  
  
-   Всегда вызывайте базовую реализацию первой в методах `PreFilter`.  
  
-   Всегда вызывайте базовую реализацию последней в методах `PostFilter`.  
  
 Выполнение этих правил позволит обеспечить для всех разработчиков единое представление всех разрабатываемых компонентов.  
  
 Класс <xref:System.ComponentModel.Design.ComponentDesigner> предоставляет словарь для управления значением затененных свойств, что снимает необходимость создавать отдельные переменные экземпляров.  
  
#### Создание пользовательского конструктора для создания тени и фильтрации свойств  
  
1.  Щелкните правой кнопкой мыши папку **Разработка** и добавьте новый класс.  Назовите исходный файл "MarqueeBorderDesigner".  
  
2.  Откройте файл `MarqueeBorderDesigner` в **редакторе кода**.  В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  Измените объявление `MarqueeBorderDesigner` для наследования <xref:System.Windows.Forms.Design.ParentControlDesigner>.  
  
     Элемент управления `MarqueeBorder` может содержать дочерние элементы управления, поэтому `MarqueeBorderDesigner` наследует <xref:System.Windows.Forms.Design.ParentControlDesigner>, который обрабатывает взаимодействие между дочерними и родительскими объектами.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  Замените базовую реализацию <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  Реализуйте свойства <xref:System.Windows.Forms.Control.Enabled%2A> и <xref:System.Windows.Forms.Control.Visible%2A>.  Эти реализации затеняют свойства элемента управления.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## Обработка изменений компонентов  
 Класс `MarqueeControlRootDesigner` обеспечивает настраиваемые возможности разработки для экземпляров `MarqueeControl`.  Большая часть функций разработки наследуется от класса <xref:System.Windows.Forms.Design.DocumentDesigner>; в коде будет два изменения: изменение обработки компонентов и добавление команд конструктора.  
  
 По мере разработки пользователями своих экземпляров `MarqueeControl` корневой конструктор будет отслеживать изменения в `MarqueeControl` и дочерних элементах управления.  В среде разработки предусмотрена служба <xref:System.ComponentModel.Design.IComponentChangeService> для отслеживания изменений состояния компонентов.  
  
 Ссылку на эту службу можно получить путем запроса среды с помощью метода <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>.  Если запрос выполнен успешно, конструктор может присоединить обработчик к событию <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> и выполнять любые задачи, необходимые для обеспечения однородного состояния при разработке.  
  
 Что касается класса `MarqueeControlRootDesigner`, необходимо будет вызвать метод <xref:System.Windows.Forms.Control.Refresh%2A> для каждого объекта `IMarqueeWidget`, содержащегося в `MarqueeControl`.  При этом объект `IMarqueeWidget` примет соответствующие изменения при изменений свойств <xref:System.Windows.Forms.Control.Size%2A> родительского элемента.  
  
#### Обработка изменений компонентов  
  
1.  Откройте файл `MarqueeControlRootDesigner` в **редакторе кода** и замените метод <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>.  Вызовите базовую реализацию <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> и запросите <xref:System.ComponentModel.Design.IComponentChangeService>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  Реализуйте обработчик событий <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>.  Проверьте тип компонента отправки, и если он находится в `IMarqueeWidget`, вызовите его метод <xref:System.Windows.Forms.Control.Refresh%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## Добавление команд конструктора в пользовательский конструктор  
 Командой конструктора называется команда меню, связанная с обработчиком событий.  Команды конструктора добавляются в контекстное меню компонента при разработке.  Дополнительные сведения см. в разделе <xref:System.ComponentModel.Design.DesignerVerb>.  
  
 В конструкторы нужно добавить две команды: **Запустить тест** и **Остановить тест**.  Эти команды помогут проверить работу `MarqueeControl` во время разработки.  Эти команды будут добавлены в `MarqueeControlRootDesigner`.  
  
 При вызове команды **Запустить тест** обработчик событий команды вызовет метод `StartMarquee` для `MarqueeControl`.  При вызове команды **Остановить тест** обработчик событий команды вызовет метод `StopMarquee` для `MarqueeControl`.  Реализация методов `StartMarquee` и `StopMarquee` вызывает эти методы в элементах управления, реализующих `IMarqueeWidget`, поэтому любые содержащиеся в них элементы управления `IMarqueeWidget` также будут участвовать в тесте.  
  
#### Добавление команд конструктора в пользовательский конструктор  
  
1.  В классе `MarqueeControlRootDesigner` добавьте обработчики событий `OnVerbRunTest` и `OnVerbStopTest`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  Подключите эти обработчики событий к соответствующим командам конструктора.  Класс `MarqueeControlRootDesigner` является производным от базового класса <xref:System.ComponentModel.Design.DesignerVerbCollection>.  Нужно будет создать два новых объекта <xref:System.ComponentModel.Design.DesignerVerb> и добавить их в эту коллекцию в методе <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## Создание пользовательского редактора UITypeEditor  
 При создании пользовательской среды разработки часто желательно изменить взаимодействие с окном "Свойства".  Это можно выполнить с путем создания редактора <xref:System.Drawing.Design.UITypeEditor>.  Дополнительные сведения см. в разделе [How to: Create a UI Type Editor](../Topic/How%20to:%20Create%20a%20UI%20Type%20Editor.md).  
  
 Элемент управления `MarqueeBorder` содержит несколько свойств в окне "Свойства".  Два из этих свойств, `MarqueeSpinDirection` и `MarqueeLightShape`, представлены перечислениями.  Чтобы продемонстрировать использование редактора типов, свойство `MarqueeLightShape` получит связанный класс <xref:System.Drawing.Design.UITypeEditor>.  
  
#### Чтобы создать редактор типов пользовательского интерфейса  
  
1.  Откройте файл исходного кода `MarqueeBorder` в **Редакторе кода**.  
  
2.  В определении класса `MarqueeBorder` определите класс `LightShapeEditor`, производный от <xref:System.Drawing.Design.UITypeEditor>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  Объявите переменную экземпляра <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> под названием `editorService`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  Переопределите метод <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>.  Эта реализация возвращает <xref:System.Drawing.Design.UITypeEditorEditStyle>, согласно которому среда разработки отображает `LightShapeEditor`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  Переопределите метод <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>.  Эта реализация запрашивает в среде разработки объект <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>.  В случае успеха она создает `LightShapeSelectionControl`.  Метод <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> вызывается для запуска `LightShapeEditor`.  При этом возвращаемое при этом вызове значение возвращается в среду разработки.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## Создание элемента управления просмотром для пользовательского редактора UITypeEditor  
  
1.  Свойство `MarqueeLightShape` поддерживает два типа простых фигур: `Square` и `Circle`.  Мы создадим элемент управления, единственной целью которого будет графическое отображение этих значений в окне "Свойства".  Пользовательский элемент управления будет использован редактором <xref:System.Drawing.Design.UITypeEditor> для взаимодействия с окном "Свойства".  
  
#### Создание элемента управления просмотром для пользовательского редактора UITypeEditor  
  
1.  Добавьте новый элемент <xref:System.Windows.Forms.UserControl> в проект `MarqueeControlLibrary`.  Назовите новый исходный файл "LightShapeSelectionControl".  
  
2.  Из **панели элементов** перетащите в `LightShapeSelectionControl` два элемента управления <xref:System.Windows.Forms.Panel>.  Назовите их `squarePanel` и `circlePanel`.  Расположите их рядом.  Установите свойство <xref:System.Windows.Forms.Control.Size%2A> обоих элементов управления <xref:System.Windows.Forms.Panel> равным \(60, 60\).  Установите свойство <xref:System.Windows.Forms.Control.Location%2A> элемента управления `squarePanel` равным \(8, 10\).  Установите свойство <xref:System.Windows.Forms.Control.Location%2A> элемента управления `circlePanel` равным \(80, 10\).  Затем установите свойство <xref:System.Windows.Forms.Control.Size%2A> элемента управления `LightShapeSelectionControl` равным \(150, 80\).  
  
3.  Откройте исходный файл `LightShapeSelectionControl` в **редакторе кода**.  В верхней части файла импортируйте пространство имен <xref:System.Windows.Forms.Design?displayProperty=fullName>.  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  Реализуйте обработчики событий <xref:System.Windows.Forms.Control.Click> для элементов управления `squarePanel` и `circlePanel`.  Эти методы вызывают <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> для окончания сеанса редактирования <xref:System.Drawing.Design.UITypeEditor>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  Объявите переменную экземпляра <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> под названием `editorService`.  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  Объявите переменную экземпляра `MarqueeLightShape` под названием `lightShapeValue`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  В конструкторе `LightShapeSelectionControl` присоедините обработчики событий <xref:System.Windows.Forms.Control.Click> к событиям <xref:System.Windows.Forms.Control.Click> элементов управления `squarePanel` и `circlePanel`.  Кроме того, определите перегрузку конструктора, присваивающую значение `MarqueeLightShape` из среды конструктора полю `lightShapeValue`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  В методе <xref:System.ComponentModel.Component.Dispose%2A> отделите обработчики событий <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  В **обозревателе решений** нажмите кнопку **Показать все файлы**.  Откройте файл LightShapeSelectionControl.Designer.cs или LightShapeSelectionControl.Designer.vb и удалите определение по умолчанию метода <xref:System.ComponentModel.Component.Dispose%2A>.  
  
5.  Реализуйте свойство `LightShape`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  Переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A>.  Эта реализация отобразит квадрат с заливкой и круг.  Также она выделит выбранное значение путем рисования границы вокруг одной или другой фигуры.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## Тестирование элемента управления в конструкторе  
 Теперь можно построить проект `MarqueeControlLibrary`.  Проверьте реализацию, создав элемент управления, наследующий класс `MarqueeControl` и использующий его в форме.  
  
#### Создание пользовательской реализации MarqueeControl  
  
1.  Откройте форму `DemoMarqueeControl` в конструкторе Windows Forms.  При этом будет создан экземпляр типа `DemoMarqueeControl`, он будет отображен в экземпляре типа `MarqueeControlRootDesigner`.  
  
2.  В **панели элементов** перейдите на вкладку **Компоненты MarqueeControlLibrary**.  Появятся элементы управления `MarqueeBorder`и `MarqueeText`, доступные для выбора.  
  
3.  Перетащите экземпляр элемента управления `MarqueeBorder` на рабочую поверхность `DemoMarqueeControl`.  Прикрепите элемент управления `MarqueeBorder` к родительскому элементу управления.  
  
4.  Перетащите экземпляр элемента управления `MarqueeText` на рабочую поверхность `DemoMarqueeControl`.  
  
5.  Выполните построение решения.  
  
6.  Щелкните `DemoMarqueeControl` правой кнопкой мыши и выберите команду **Запустить тест**, чтобы включить анимацию.  Нажмите **Остановить тест**, чтобы выключить анимацию.  
  
7.  Откройте форму **Form1** в режиме конструктора.  
  
8.  Добавьте в форму два элемента управления <xref:System.Windows.Forms.Button>.  Назовите их `startButton` и `stopButton` и измените значения свойства <xref:System.Windows.Forms.Control.Text%2A> на Start и Stop соответственно.  
  
9. Реализуйте обработчики событий <xref:System.Windows.Forms.Control.Click> для обоих элементов управления <xref:System.Windows.Forms.Button>.  
  
10. В **панели элементов** перейдите на вкладку **Компоненты MarqueeControlTest**.  Появится элемент управления `DemoMarqueeControl`, доступный для выбора.  
  
11. Перетащите экземпляр элемента управления `DemoMarqueeControl` на рабочую поверхность **Form1**.  
  
12. В обработчиках событий <xref:System.Windows.Forms.Control.Click> вызовите методы `Start` и `Stop` в `DemoMarqueeControl`.  
  
```vb  
Private Sub startButton_Click(sender As Object, e As System.EventArgs)  
    Me.demoMarqueeControl1.Start()  
End Sub 'startButton_Click  
  
Private Sub stopButton_Click(sender As Object, e As System.EventArgs)  
Me.demoMarqueeControl1.Stop()  
End Sub 'stopButton_Click  
```  
  
```csharp  
private void startButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Start();  
}  
  
private void stopButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Stop();  
}  
```  
  
1.  Установите проект `MarqueeControlTest` в качестве проекта для запуска и запустите его.  Появится элемент форма с четырьмя элементами `DemoMarqueeControl`.  Нажмите кнопку **Пуск** для запуска анимации.  Текст начнет мигать, а огни двигаться вдоль границы.  
  
## Следующие действия  
 Библиотека `MarqueeControlLibrary` демонстрирует простую реализацию пользовательских элементов управления и связанных с ними конструкторов.  Этот пример можно усложнить следующим образом.  
  
-   Измените значения свойств `DemoMarqueeControl` в конструкторе.  Добавьте еще несколько элементов управления `MarqueBorder` и прикрепите их к родительским экземплярам для создания многоуровневого эффекта.  Попробуйте применить различные параметры к `UpdatePeriod` и свойствам, связанным с подсветкой.  
  
-   Создайте собственные реализации `IMarqueeWidget`.  Например, можно создать мигающую "неоновую вывеску" или анимированную вывеску с разными изображениями.  
  
-   Можно изменить действия при разработке.  Попробуйте затенить больше свойств, чем <xref:System.Windows.Forms.Control.Enabled%2A> и <xref:System.Windows.Forms.Control.Visible%2A>, а также добавить новые свойства.  Добавьте новые команды конструктора для упрощения часто выполняемых задач, таких как закрепление дочерних элементов управления.  
  
-   Лицензируйте `MarqueeControl`.  Дополнительные сведения см. в разделе [How to: License Components and Controls](../Topic/How%20to:%20License%20Components%20and%20Controls.md).  
  
-   Управляйте сериализацией элементов управления и создаваемым для них кодом.  Дополнительные сведения см. в разделе [Dynamic Source Code Generation and Compilation](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).  
  
## См. также  
 <xref:System.Windows.Forms.UserControl>   
 <xref:System.Windows.Forms.Design.ParentControlDesigner>   
 <xref:System.Windows.Forms.Design.DocumentDesigner>   
 <xref:System.ComponentModel.Design.IRootDesigner>   
 <xref:System.ComponentModel.Design.DesignerVerb>   
 <xref:System.Drawing.Design.UITypeEditor>   
 <xref:System.ComponentModel.BackgroundWorker>   
 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Custom Designers](../Topic/Custom%20Designers.md)   
 [.NET Shape Library: A Sample Designer](http://windowsforms.net/articles/shapedesigner.aspx)