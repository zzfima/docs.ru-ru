---
title: 'Пошаговое руководство: Создание элемента управления Windows Forms, в котором используются преимущества возможностей Visual Studio, применяемых во время разработки'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
ms.openlocfilehash: 10905df76f2b638c10b14c1dd8c181b9652ea963
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529744"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a>Пошаговое руководство: Создание элемента управления Windows Forms, в котором используются преимущества возможностей Visual Studio, применяемых во время разработки
Возможности разработки для пользовательского элемента управления можно улучшить путем создания и настройки связанного с ним пользовательский конструктор.  
  
 В этом пошаговом руководстве показано, как создать пользовательский конструктор для пользовательского элемента управления. Следует реализовать `MarqueeControl` тип и связанный класс конструктора, называется `MarqueeControlRootDesigner`.  
  
 `MarqueeControl` Тип реализует аналогичного используемому в область «театр», с анимированного индикатора и мигающим текстом.  
  
 Конструктор для этого элемента управления взаимодействует со средой разработки для предоставления пользовательского интерфейса во время разработки. С помощью пользовательского конструктора можно создать пользовательскую `MarqueeControl` реализацию с анимированного индикатора и мигающим текстом во многих сочетаниях. Можно использовать полученный элемент управления в форме, как любой другой элемент управления Windows Forms.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта  
  
-   Создание проекта библиотеки элементов управления  
  
-   Ссылка на проект пользовательского элемента управления  
  
-   Определение пользовательского элемента управления и его конструктора  
  
-   Создание экземпляра пользовательского элемента управления  
  
-   Настройка проекта для отладки во время разработки  
  
-   Реализация пользовательского элемента управления  
  
-   Создание дочернего элемента управления для элемента управления  
  
-   Создание MarqueeBorder дочерний элемент управления  
  
-   Создание пользовательского конструктора для тени и фильтрации свойств  
  
-   Обработка изменений компонентов  
  
-   Добавление команд конструктора в пользовательский конструктор  
  
-   Создание пользовательского редактора UITypeEditor  
  
-   Тестирование элемента управления в конструкторе  
  
 Когда вы закончите, пользовательский элемент управления будет выглядеть примерно следующим образом:  
  
 ![Возможный порядок MarqueeControl](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")  
  
 Полный пример кода, в разделе [как: создание Windows Forms, принимает преимущества из разработки возможности управления](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, где установлена среда Visual Studio.  
  
## <a name="creating-the-project"></a>Создание проекта  
 Первым шагом является создание проекта приложения. Этот проект будет использован для построения приложения, на котором размещается пользовательский элемент управления.  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
-   Создайте проект приложения Windows Forms, называется «MarqueeControlTest». Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## <a name="creating-a-control-library-project"></a>Создание проекта библиотеки элементов управления  
 Следующим шагом является создание проекта библиотеки элементов управления. Вы создадите новый пользовательский элемент управления и его соответствующего конструктора.  
  
#### <a name="to-create-the-control-library-project"></a>Создание проекта библиотеки элементов управления  
  
1.  Добавьте в решение проект библиотеки элементов управления Windows Forms. Назовите проект «MarqueeControlLibrary».  
  
2.  С помощью **обозревателе решений**, удалите элемент управления проекта по умолчанию, удаляя исходный файл «UserControl1.cs» или «UserControl1.vb» в зависимости от выбранного языка. Дополнительные сведения см. в разделе [NIB: Практическое: удаление, Delete и исключить элементы](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Добавьте новый <xref:System.Windows.Forms.UserControl> элемент `MarqueeControlLibrary` проекта. Предоставить новый исходный файл базовое имя «MarqueeControl».  
  
4.  С помощью **обозревателе решений**, создайте новую папку в `MarqueeControlLibrary` проекта. Дополнительные сведения см. в разделе [NIB: Практическое: Добавление новых элементов проекта](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce). Имя новой папки «Конструктор».  
  
5.  Щелкните правой кнопкой мыши **разработки** папки и добавьте новый класс. Предоставьте исходный файл базовое имя «MarqueeControlRootDesigner.»  
  
6.  Необходимо использовать типы из сборки System.Design, поэтому добавьте данную ссылку, чтобы `MarqueeControlLibrary` проекта.  
  
    > [!NOTE]
    >  Для применения сборки System.Design, проект необходимо использовать полную версию .NET Framework, а не клиентский профиль .NET Framework. Чтобы изменить целевую платформу, см. [как: целевой версии платформы .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).  
  
## <a name="referencing-the-custom-control-project"></a>Ссылка на проект пользовательского элемента управления  
 Вы воспользуетесь `MarqueeControlTest` проекта для тестирования пользовательского элемента управления. Тестовый проект получит данные о пользовательского элемента управления при добавлении ссылку на проект `MarqueeControlLibrary` сборки.  
  
#### <a name="to-reference-the-custom-control-project"></a>Для ссылки на проект пользовательского элемента управления  
  
-   В `MarqueeControlTest` проект, добавить ссылку на проект `MarqueeControlLibrary` сборки. Обязательно используйте **проекты** вкладку в **добавить ссылку** вместо ссылки на диалоговое окно `MarqueeControlLibrary` непосредственно сборки.  
  
## <a name="defining-a-custom-control-and-its-custom-designer"></a>Определение пользовательского элемента управления и его конструктора  
 Пользовательский элемент управления, производной от <xref:System.Windows.Forms.UserControl> класса. Это позволяет управления содержать другие элементы управления, и он предоставляет значительные возможности по умолчанию функциональные возможности элемента управления.  
  
 Пользовательский элемент управления будет иметь связанный с ним пользовательский конструктор. Это позволяет создать уникальный интерфейс разработки, предназначенная специально для пользовательского элемента управления.  
  
 Связывание элемента управления с его конструктор посредством <xref:System.ComponentModel.DesignerAttribute> класса. Поскольку вы разрабатываете всей поведение времени разработки пользовательского элемента управления, пользовательский конструктор будет реализовывать <xref:System.ComponentModel.Design.IRootDesigner> интерфейса.  
  
#### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Чтобы определить пользовательский элемент управления и его конструктора  
  
1.  Откройте `MarqueeControl` исходный файл в **редактор кода**. В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  Добавить <xref:System.ComponentModel.DesignerAttribute> для `MarqueeControl` объявления класса. Это связывает пользовательский элемент управления с его конструктор.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  Откройте `MarqueeControlRootDesigner` исходный файл в **редактор кода**. В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  Измените объявление `MarqueeControlRootDesigner` наследование от <xref:System.Windows.Forms.Design.DocumentDesigner> класса. Применить <xref:System.ComponentModel.ToolboxItemFilterAttribute> для определения взаимодействия конструктора с **элементов**.  
  
     **Примечание** определение `MarqueeControlRootDesigner` класса заключается в пространство имен с именем «MarqueeControlLibrary.Design.» Это объявление помещает конструктор в специальном пространстве имен для типов, связанных с зарезервированным.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  Определение конструктора для `MarqueeControlRootDesigner` класса. Вставить <xref:System.Diagnostics.Trace.WriteLine%2A> инструкции в теле конструктора. Это будет использована для отладки.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## <a name="creating-an-instance-of-your-custom-control"></a>Создание экземпляра пользовательского элемента управления  
 Чтобы увидеть, пользовательское поведение времени разработки элемента управления, будет размещен экземпляр элемента управления в форме в `MarqueeControlTest` проекта.  
  
#### <a name="to-create-an-instance-of-your-custom-control"></a>Для создания экземпляра пользовательского элемента управления  
  
1.  Добавьте новый <xref:System.Windows.Forms.UserControl> элемент `MarqueeControlTest` проекта. Предоставить новый исходный файл базовое имя «DemoMarqueeControl.»  
  
2.  Откройте `DemoMarqueeControl` файла в **редактор кода**. В верхней части файла, Импорт `MarqueeControlLibrary` пространство имен:  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  Измените объявление `DemoMarqueeControl` наследование от `MarqueeControl` класса.  
  
2.  Выполните построение проекта.  
  
3.  Откройте `Form1` в конструкторе Windows Forms.  
  
4.  Найти **MarqueeControlTest компоненты** вкладке **элементов** и откройте его. Перетащите `DemoMarqueeControl` из **элементов** на форму.  
  
5.  Выполните построение проекта.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Настройка проекта для отладки во время разработки  
 При разработке пользовательского взаимодействия во время разработки, он будут необходимы для отладки элементов управления и компонентов. Отсутствует простой способ настроить проект для отладки во время разработки. Дополнительные сведения см. в разделе [Пошаговое руководство: Отладка пользовательского управления Windows Forms во время разработки](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>Настройка проекта для отладки во время разработки  
  
1.  Щелкните правой кнопкой мыши `MarqueeControlLibrary` проект и выберите **свойства**.  
  
2.  В диалоговом окне «Страницы свойств MarqueeControlLibrary» выберите **отладки** страницы.  
  
3.  В **действие при запуске** выберите **запуск внешней программы**. Можно отладка отдельного экземпляра Visual Studio, поэтому нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) чтобы выбрать Интегрированной среде разработки Visual Studio. Имя исполняемого файла — devenv.exe, и если установлен в расположение по умолчанию, его путь — 9.0\Common7\IDE\devenv.exe %programfiles%\Microsoft Visual Studio.  
  
4.  Нажмите кнопку ОК, чтобы закрыть диалоговое окно.  
  
5.  Щелкните правой кнопкой мыши `MarqueeControlLibrary` проекта и выберите «Назначить запускаемым проектом», чтобы включить конфигурацию отладки.  
  
## <a name="checkpoint"></a>Контрольная точка  
 Теперь вы готовы отладки поведения пользовательского элемента управления во время разработки. После определения правильно настроить среду отладки можно проверить связь пользовательского элемента управления и пользовательский конструктор.  
  
#### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Для тестирования среды отладки и связи конструктора  
  
1.  Откройте `MarqueeControlRootDesigner` исходный файл в **редактор кода** и установить точку останова на <xref:System.Diagnostics.Trace.WriteLine%2A> инструкции.  
  
2.  Нажмите клавишу F5 для запуска сеанса отладки. Обратите внимание, что создается новый экземпляр Visual Studio.  
  
3.  В новом экземпляре Visual Studio откройте решение «MarqueeControlTest». Решение можно легко найти, выбрав **последние проекты** из **файл** меню. Файл решения «MarqueeControlTest.sln» будут указаны как список последних использовавшихся файлов.  
  
4.  Откройте `DemoMarqueeControl` в конструкторе. Обратите внимание, что отладки экземпляр Visual Studio получает фокус, и выполнение останавливается в точке останова. Нажмите клавишу F5, чтобы продолжить сеанс отладки.  
  
 На этом этапе все, что находится в месте, для разработки и отладки пользовательского элемента управления и его связанного конструктора. В оставшейся части этого пошагового руководства будет посвящена подробности реализации функции управления и конструктором.  
  
## <a name="implementing-your-custom-control"></a>Реализация пользовательского элемента управления  
 `MarqueeControl` — <xref:System.Windows.Forms.UserControl> С небольшим количеством настройки. Он предоставляет два метода: `Start`, которая запускает анимации области выделения и `Stop`, остановка анимации. Так как `MarqueeControl` содержит дочерние элементы управления, которые реализуют `IMarqueeWidget` интерфейс, `Start` и `Stop` перечисления каждого дочернего элемента управления и вызова `StartMarquee` и `StopMarquee` методов, соответственно, для каждого дочернего элемента управления реализующий `IMarqueeWidget`.  
  
 Внешний вид `MarqueeBorder` и `MarqueeText` элементов управления зависит от макета, поэтому `MarqueeControl` переопределяет <xref:System.Windows.Forms.Control.OnLayout%2A> метода и вызывает метод <xref:System.Windows.Forms.Control.PerformLayout%2A> на дочерние элементы этого типа.  
  
 Это область `MarqueeControl` настроек. Функции времени выполнения реализуются `MarqueeBorder` и `MarqueeText` элементы управления и компоненты времени разработки реализуются `MarqueeBorderDesigner` и `MarqueeControlRootDesigner` классы.  
  
#### <a name="to-implement-your-custom-control"></a>Для реализации пользовательского элемента управления  
  
1.  Откройте `MarqueeControl` исходный файл в **редактор кода**. Реализуйте `Start` и `Stop` методы.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  Переопределите метод <xref:System.Windows.Forms.Control.OnLayout%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## <a name="creating-a-child-control-for-your-custom-control"></a>Создание дочернего элемента управления для элемента управления  
 `MarqueeControl` Будут размещены два вида дочернего элемента управления: `MarqueeBorder` управления и `MarqueeText` элемента управления.  
  
-   `MarqueeBorder`: Этот элемент управления рисует «индикаторов» вокруг его границ. Индикаторы мигают, поэтому они появляются на перемещение вокруг границы. Скорость, с которой индикаторы флэш-управляется свойство с именем `UpdatePeriod`. Несколько других пользовательских свойств определяют другие характеристики внешнего вида элемента управления. Два метода, `StartMarquee` и `StopMarquee`, контролировать, когда анимация начинается и останавливается.  
  
-   `MarqueeText`: Этот элемент управления отрисовывается Мерцающий строки. Как `MarqueeBorder` управления, скорость мигания текста управляется `UpdatePeriod` свойство. `MarqueeText` Управления также имеет `StartMarquee` и `StopMarquee` методы общих с `MarqueeBorder` элемента управления.  
  
 Во время разработки `MarqueeControlRootDesigner` позволяет эти типы двух элементов управления для добавления `MarqueeControl` в любой комбинации.  
  
 Общие свойства этих двух элементов управления представлены в интерфейсе `IMarqueeWidget`. Это позволяет `MarqueeControl` определять все дочерние элементы управления и обрабатывать их особым образом.  
  
 Чтобы реализовать анимации, используется <xref:System.ComponentModel.BackgroundWorker> объектов из <xref:System.ComponentModel?displayProperty=nameWithType> пространства имен. Можно использовать <xref:System.Windows.Forms.Timer> объектов, но когда много `IMarqueeWidget` присутствуют объекты, возможно, один поток пользовательского интерфейса может справиться с анимацией.  
  
#### <a name="to-create-a-child-control-for-your-custom-control"></a>Для создания дочернего элемента управления для элемента управления  
  
1.  Добавить новый элемент класса в `MarqueeControlLibrary` проекта. Предоставить новый исходный файл базовое имя «IMarqueeWidget».  
  
2.  Откройте `IMarqueeWidget` исходный файл в **редактор кода** и замените объявление с `class` для `interface`:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  Добавьте следующий код в `IMarqueeWidget` интерфейс для предоставления двух методов и свойства, анимацией бегущей строки:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  Добавьте новый **пользовательский элемент управления** элемент `MarqueeControlLibrary` проекта. Предоставить новый исходный файл базовое имя «MarqueeText».  
  
5.  Перетащите <xref:System.ComponentModel.BackgroundWorker> из **элементов** на ваш `MarqueeText` элемента управления. Этот компонент обеспечит `MarqueeText` управления асинхронное обновление.  
  
6.  В окне свойств задайте <xref:System.ComponentModel.BackgroundWorker> компонента `WorkerReportsProgess` и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> свойства `true`. Эти параметры позволяют <xref:System.ComponentModel.BackgroundWorker> компонент периодически вызывать <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> событий и для отмены асинхронного обновления. Дополнительные сведения см. в разделе [компонента BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
7.  Откройте `MarqueeText` исходный файл в **редактор кода**. В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  Измените объявление `MarqueeText` наследование от <xref:System.Windows.Forms.Label> и реализовать `IMarqueeWidget` интерфейс:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. Объявите переменные экземпляра, соответствующие этим свойствам и инициализируйте их в конструкторе. `isLit` Поле определяет, является ли текст для рисования с помощью цвета `LightColor` свойство.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. Реализовать интерфейс `IMarqueeWidget`.  
  
     `StartMarquee` И `StopMarquee` методы вызывают <xref:System.ComponentModel.BackgroundWorker> компонента <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> и <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> методы для запуска и остановки анимации.  
  
     <xref:System.ComponentModel.CategoryAttribute.Category%2A> И <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> атрибуты будут применены к `UpdatePeriod` свойства, поэтому оно отображается в пользовательском разделе окна "Свойства" под названием «Marquee».  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. Реализации методов доступа свойства. Предоставляет два свойства для клиентов: `LightColor` и `DarkColor`. <xref:System.ComponentModel.CategoryAttribute.Category%2A> И <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> атрибуты будут применены к этим свойствам, поэтому они отображаются в пользовательском разделе окна "Свойства" под названием «Marquee».  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. Реализуйте обработчики для <xref:System.ComponentModel.BackgroundWorker> компонента <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> события.  
  
     <xref:System.ComponentModel.BackgroundWorker.DoWork> Обработчик событий бездействует в течение указанного числа миллисекунд `UpdatePeriod` затем вызывает <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> до момента, когда код останавливает анимацию путем вызова <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Текст между состоянии светлые и темные, чтобы эмулировать мигать переключает обработчика событий.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. Переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> способ включения анимации.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. Нажмите клавишу F6 для построения решения.  
  
## <a name="create-the-marqueeborder-child-control"></a>Создание MarqueeBorder дочерний элемент управления  
 `MarqueeBorder` Управления немного сложнее, чем `MarqueeText` элемента управления. Он имеет дополнительные свойства и анимации в <xref:System.Windows.Forms.Control.OnPaint%2A> несколько сложнее. В принципе, он похож на `MarqueeText` элемента управления.  
  
 Поскольку `MarqueeBorder` элемент управления может иметь дочерние элементы управления, ему необходимо иметь в виду <xref:System.Windows.Forms.Control.Layout> события.  
  
#### <a name="to-create-the-marqueeborder-control"></a>Создание элемента управления MarqueeBorder  
  
1.  Добавьте новый **пользовательский элемент управления** элемент `MarqueeControlLibrary` проекта. Предоставить новый исходный файл базовое имя «MarqueeBorder».  
  
2.  Перетащите <xref:System.ComponentModel.BackgroundWorker> из **элементов** на ваш `MarqueeBorder` элемента управления. Этот компонент обеспечит `MarqueeBorder` управления асинхронное обновление.  
  
3.  В окне свойств задайте <xref:System.ComponentModel.BackgroundWorker> компонента `WorkerReportsProgess` и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> свойства `true`. Эти параметры позволяют <xref:System.ComponentModel.BackgroundWorker> компонент периодически вызывать <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> событий и для отмены асинхронного обновления. Дополнительные сведения см. в разделе [компонента BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
4.  В окне «Свойства» нажмите кнопку события. Присоединение обработчиков для <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> события.  
  
5.  Откройте `MarqueeBorder` исходный файл в **редактор кода**. В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  Измените объявление `MarqueeBorder` наследование от <xref:System.Windows.Forms.Panel> и реализовать `IMarqueeWidget` интерфейса.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  Объявите два перечисления для управления `MarqueeBorder` состояние элемента управления: `MarqueeSpinDirection`, который определяет направление, в котором индикаторы «запустить» вокруг границы, и `MarqueeLightShape`, который определяет форму получаемого индикаторы (квадратную или круглую). Поместите эти объявления до `MarqueeBorder` объявления класса.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  Объявите переменные экземпляра, соответствующие этим свойствам и инициализируйте их в конструкторе.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. Реализовать интерфейс `IMarqueeWidget`.  
  
     `StartMarquee` И `StopMarquee` методы вызывают <xref:System.ComponentModel.BackgroundWorker> компонента <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> и <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> методы для запуска и остановки анимации.  
  
     Поскольку `MarqueeBorder` элемент управления может содержать дочерние элементы управления `StartMarquee` метод перечисляет все дочерние элементы управления и вызывает `StartMarquee` на те, которые реализуют `IMarqueeWidget`. `StopMarquee` Метод имеет аналогичную реализацию.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. Реализации методов доступа свойства. `MarqueeBorder` Управления имеет несколько свойств, внешний вид.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. Реализуйте обработчики для <xref:System.ComponentModel.BackgroundWorker> компонента <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> события.  
  
     <xref:System.ComponentModel.BackgroundWorker.DoWork> Обработчик событий бездействует в течение указанного числа миллисекунд `UpdatePeriod` затем вызывает <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> до момента, когда код останавливает анимацию путем вызова <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Обработчик событий изменяет положение «базового» light, из которого определяется состояние светлой и темной другие индикаторы, и вызывает метод <xref:System.Windows.Forms.Control.Refresh%2A> метод, чтобы элемент управления окрашивание.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. Реализуйте вспомогательные методы `IsLit` и `DrawLight`.  
  
     `IsLit` Метод определяет цвет источника света в заданной позиции. «Включен» являются рисуются с помощью цвета `LightColor` свойство и тех, которые находятся в «темной» рисуются с помощью цвета `DarkColor` свойство.  
  
     `DrawLight` Метод выводит индикатор с помощью соответствующего цвета, фигуры и положения.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. Переопределить <xref:System.Windows.Forms.Control.OnLayout%2A> и <xref:System.Windows.Forms.Control.OnPaint%2A> методы.  
  
     <xref:System.Windows.Forms.Control.OnPaint%2A> Метод формирует индикаторы на границах `MarqueeBorder` элемента управления.  
  
     Поскольку <xref:System.Windows.Forms.Control.OnPaint%2A> метод зависит от измерения `MarqueeBorder` элемента управления, необходимо вызвать его при каждом изменении макета. Чтобы сделать это, переопределите <xref:System.Windows.Forms.Control.OnLayout%2A> и вызвать <xref:System.Windows.Forms.Control.Refresh%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a>Создание пользовательского конструктора для тени и фильтрации свойств  
 `MarqueeControlRootDesigner` Класс предоставляет реализацию базового конструктора. В дополнение к этому конструктору, работающему над `MarqueeControl`, вам потребуется пользовательский конструктор, связанный с `MarqueeBorder` элемента управления. Этот конструктор предоставляет пользовательское поведение, которое подходит в контексте пользовательского корневого конструктора.  
  
 В частности `MarqueeBorderDesigner` будет «тень» и отфильтрует определенные свойства `MarqueeBorder` элемента управления, изменив их взаимодействие со средой разработки.  
  
 Перехват вызовов к методу доступа свойства компонента, называется «затенение». Он позволяет разработчику отслеживать значения, задаваемого пользователем и при необходимости передавать это значение в создаваемый компонент.  
  
 В этом примере <xref:System.Windows.Forms.Control.Visible%2A> и <xref:System.Windows.Forms.Control.Enabled%2A> будут затенены `MarqueeBorderDesigner`, что предотвращает создание пользователя `MarqueeBorder` управления активация невидимого или отключенного во время разработки.  
  
 Конструкторы можно также добавлять и удалять свойства. В этом примере <xref:System.Windows.Forms.Control.Padding%2A> свойство будет удалено во время разработки, так как `MarqueeBorder` управления программным образом задается заполнения, исходя из размера индикаторов, определяемое `LightSize` свойство.  
  
 Базовый класс для `MarqueeBorderDesigner` — <xref:System.ComponentModel.Design.ComponentDesigner>, который содержит методы, которые можно изменить атрибуты, свойства и события, предоставляемые элементом управления во время разработки:  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 При изменении общего интерфейса компонента с помощью этих методов, необходимо соблюдать следующие правила:  
  
-   Добавить или удалить элементы из `PreFilter` только методы  
  
-   Изменение существующих элементов в `PostFilter` только методы  
  
-   Всегда следует сначала вызвать базовую реализацию `PreFilter` методы  
  
-   Всегда вызывайте базовую реализацию последней в `PostFilter` методы  
  
 Выполнение этих правил гарантирует все конструкторы в среде разработки согласованное представление всех разрабатываемых компонентов.  
  
 <xref:System.ComponentModel.Design.ComponentDesigner> Класс предоставляет словарь для управления значением затененных свойств, что снимает необходимость создавать отдельные переменные экземпляров.  
  
#### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Создание пользовательского конструктора тени и фильтрации свойств  
  
1.  Щелкните правой кнопкой мыши **разработки** папки и добавьте новый класс. Предоставьте исходный файл базовое имя «MarqueeBorderDesigner.»  
  
2.  Откройте `MarqueeBorderDesigner` исходный файл в **редактор кода**. В верхней части файла импортируйте следующие пространства имен:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  Измените объявление `MarqueeBorderDesigner` наследование от <xref:System.Windows.Forms.Design.ParentControlDesigner>.  
  
     Поскольку `MarqueeBorder` элемент управления может содержать дочерние элементы управления `MarqueeBorderDesigner` наследует от <xref:System.Windows.Forms.Design.ParentControlDesigner>, которая обрабатывает взаимодействие родители потомки.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  Переопределить базовую реализацию <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  Реализуйте свойства <xref:System.Windows.Forms.Control.Enabled%2A> и <xref:System.Windows.Forms.Control.Visible%2A>. Эти реализации скрывать свойства элемента управления.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## <a name="handling-component-changes"></a>Обработка изменений компонентов  
 `MarqueeControlRootDesigner` Класс предоставляет пользовательские возможности разработки для вашего `MarqueeControl` экземпляров. Большинство функций разработки наследуется от <xref:System.Windows.Forms.Design.DocumentDesigner> класса; ваш код будет реализовать два изменения: обработки компонентов и добавление команд конструктора.  
  
 Как пользователям при проектировании их `MarqueeControl` экземпляров, корневой конструктор будет отслеживать изменения в `MarqueeControl` и его дочерние элементы. Среда разработки предусмотрена служба, <xref:System.ComponentModel.Design.IComponentChangeService>для отслеживания изменений состояния компонентов.  
  
 Получить ссылку на эту службу с помощью запроса к среде с <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> метод. Если запрос выполнен успешно, может быть присоединен конструктор обработчик <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> событий и выполнения всех задач, необходимых для обеспечения согласованного состояния во время разработки.  
  
 В случае использования `MarqueeControlRootDesigner` , будет вызывать <xref:System.Windows.Forms.Control.Refresh%2A> метод на каждом `IMarqueeWidget` объект, содержащийся в `MarqueeControl`. Это приведет к `IMarqueeWidget` объект примет соответствующие при свойства, такие как его родительский <xref:System.Windows.Forms.Control.Size%2A> изменяются.  
  
#### <a name="to-handle-component-changes"></a>Обработка изменений компонентов  
  
1.  Откройте `MarqueeControlRootDesigner` исходный файл в **редактор кода** и Переопределите <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> метод. Вызвать базовую реализацию <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> и запросить <xref:System.ComponentModel.Design.IComponentChangeService>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  Реализуйте <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> обработчика событий. Проверьте тип компонента отправки, и если это `IMarqueeWidget`, вызовите его <xref:System.Windows.Forms.Control.Refresh%2A> метод.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## <a name="adding-designer-verbs-to-your-custom-designer"></a>Добавление команд конструктора в пользовательский конструктор  
 Командой конструктора называется команда меню, связанная с обработчиком событий. Команды конструктора добавляются в контекстное меню компонента во время разработки. Дополнительные сведения см. в разделе <xref:System.ComponentModel.Design.DesignerVerb>.  
  
 Вы добавите две команды в конструкторы: **запустить тест** и **Остановить тест**. Эти команды позволит просмотреть его поведение во время выполнения `MarqueeControl` во время разработки. Эти команды будут добавлены к `MarqueeControlRootDesigner`.  
  
 При **запустить тест** — вызове вызывает обработчик событий команда `StartMarquee` метод `MarqueeControl`. При **Остановить тест** — вызове вызывает обработчик событий команда `StopMarquee` метод `MarqueeControl`. Реализация `StartMarquee` и `StopMarquee` методы вызывать эти методы в элементах управления, реализующих `IMarqueeWidget`, поэтому любые содержащиеся `IMarqueeWidget` элементов управления также будут участвовать в тесте.  
  
#### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Добавление команд конструктора в пользовательский конструктор  
  
1.  В `MarqueeControlRootDesigner` добавьте обработчики событий с именем `OnVerbRunTest` и `OnVerbStopTest`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  Соедините эти обработчики событий с соответствующими командами конструктора. `MarqueeControlRootDesigner` наследует <xref:System.ComponentModel.Design.DesignerVerbCollection> от своего базового класса. Вы создадите два новых <xref:System.ComponentModel.Design.DesignerVerb> объектов и добавить их в эту коллекцию в <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> метод.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## <a name="creating-a-custom-uitypeeditor"></a>Создание пользовательского редактора UITypeEditor  
 При создании пользовательского взаимодействия во время разработки для пользователей, часто желательно изменить взаимодействие с помощью окна «Свойства». Это можно сделать путем создания <xref:System.Drawing.Design.UITypeEditor>. Дополнительные сведения см. в разделе [как: создать редактор типов пользовательского интерфейса](http://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd).  
  
 `MarqueeBorder` Управления содержит несколько свойств в окне «Свойства». Два из этих свойств `MarqueeSpinDirection` и `MarqueeLightShape` , представлены перечислениями. Чтобы проиллюстрировать использование редактор типов пользовательского интерфейса, `MarqueeLightShape` свойство будет иметь связанный с ним <xref:System.Drawing.Design.UITypeEditor> класса.  
  
#### <a name="to-create-a-custom-ui-type-editor"></a>Чтобы создать редактор типов пользовательского интерфейса  
  
1.  Откройте `MarqueeBorder` исходный файл в **редактор кода**.  
  
2.  В определении `MarqueeBorder` класса, объявите класс с именем `LightShapeEditor` , производный от <xref:System.Drawing.Design.UITypeEditor>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  Объявите <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> экземпляр переменной с именем `editorService`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  Переопределите метод <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>. Эта реализация возвращает <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, который указывает способ отображения в среде разработки `LightShapeEditor`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  Переопределите метод <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>. Эта реализация запрашивает в среде разработки для <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> объекта. Если успешно, он создает `LightShapeSelectionControl`. <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> Метод вызывается для запуска `LightShapeEditor`. Возвращаемое значение из этого вызова возвращается в среду разработки.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a>Создание элемента управления просмотром для пользовательского редактора UITypeEditor  
  
1.  `MarqueeLightShape` Свойство поддерживает два типа простых фигур: `Square` и `Circle`. Вы создадите пользовательский элемент управления, используется исключительно для графическое отображение этих значений в окне «Свойства». Этот пользовательский элемент управления будет использоваться вашей <xref:System.Drawing.Design.UITypeEditor> для взаимодействия в окне "Свойства".  
  
#### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Создание элемента управления представления для пользовательского типа редактора  
  
1.  Добавьте новый <xref:System.Windows.Forms.UserControl> элемент `MarqueeControlLibrary` проекта. Предоставить новый исходный файл базовое имя «LightShapeSelectionControl.»  
  
2.  Перетащите два <xref:System.Windows.Forms.Panel> управляет из **элементов** на `LightShapeSelectionControl`. Назовите их `squarePanel` и `circlePanel`. Расположите их рядом друг с другом. Задать <xref:System.Windows.Forms.Control.Size%2A> свойства обоих <xref:System.Windows.Forms.Panel> элементы управления (60, 60). Задать <xref:System.Windows.Forms.Control.Location%2A> свойство `squarePanel` управления (8, 10). Задать <xref:System.Windows.Forms.Control.Location%2A> свойство `circlePanel` управления (80, 10). Задайте <xref:System.Windows.Forms.Control.Size%2A> свойство `LightShapeSelectionControl` для (150, 80).  
  
3.  Откройте `LightShapeSelectionControl` исходный файл в **редактор кода**. В верхней части файла, Импорт <xref:System.Windows.Forms.Design?displayProperty=nameWithType> пространство имен:  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  Реализуйте <xref:System.Windows.Forms.Control.Click> обработчики событий для `squarePanel` и `circlePanel` элементов управления. Эти методы вызывают <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> для окончания <xref:System.Drawing.Design.UITypeEditor> сеанса редактирования.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  Объявите <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> экземпляр переменной с именем `editorService`.  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  Объявите `MarqueeLightShape` экземпляр переменной с именем `lightShapeValue`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  В `LightShapeSelectionControl` конструктор, подключите <xref:System.Windows.Forms.Control.Click> обработчики событий для `squarePanel` и `circlePanel` элементов управления <xref:System.Windows.Forms.Control.Click> события. Кроме того, определить перегрузку конструктора, который присваивает `MarqueeLightShape` значение из среды разработки для `lightShapeValue` поля.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  В <xref:System.ComponentModel.Component.Dispose%2A> метода отсоединения <xref:System.Windows.Forms.Control.Click> обработчики событий.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  В **обозревателе решений** нажмите кнопку **Показать все файлы**. Откройте файл LightShapeSelectionControl.Designer.cs или LightShapeSelectionControl.Designer.vb и удалить определение по умолчанию <xref:System.ComponentModel.Component.Dispose%2A> метод.  
  
5.  Реализуйте свойство `LightShape`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  Переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A>. Эта реализация прорисовывает квадрат с заливкой и круг. Также она выделит выбранное значение путем рисования границы вокруг одной формы или другого.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## <a name="testing-your-custom-control-in-the-designer"></a>Тестирование элемента управления в конструкторе  
 На этом этапе можно построить `MarqueeControlLibrary` проекта. Проверьте реализацию, создав элемент управления, который наследует от `MarqueeControl` класс и использовать его в форме.  
  
#### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Чтобы создать пользовательскую реализацию MarqueeControl  
  
1.  Откройте `DemoMarqueeControl` в конструкторе Windows Forms. Это создает экземпляр `DemoMarqueeControl` введите и отображает его в экземпляр `MarqueeControlRootDesigner` типа.  
  
2.  В **элементов**откройте **компоненты MarqueeControlLibrary** вкладки. Вы увидите `MarqueeBorder` и `MarqueeText` элементов управления, доступных для выбора.  
  
3.  Перетащите экземпляр `MarqueeBorder` управления `DemoMarqueeControl` область конструктора. Прикрепите `MarqueeBorder` элемента управления в родительском элементе управления.  
  
4.  Перетащите экземпляр `MarqueeText` управления `DemoMarqueeControl` область конструктора.  
  
5.  Постройте решение.  
  
6.  Щелкните правой кнопкой мыши `DemoMarqueeControl` и в контекстном меню пункт **запустить тест** возможность немедленного начала анимации. Нажмите кнопку **Остановить тест** для остановки анимации.  
  
7.  Откройте **Form1** в режиме конструктора.  
  
8.  Разместите две <xref:System.Windows.Forms.Button> элементов управления в форме. Назовите их `startButton` и `stopButton`и измените <xref:System.Windows.Forms.Control.Text%2A> значения свойств следует **запустить** и **остановить**соответственно.  
  
9. Реализуйте <xref:System.Windows.Forms.Control.Click> обработчики событий для обоих <xref:System.Windows.Forms.Button> элементов управления.  
  
10. В **элементов**откройте **компоненты MarqueeControlTest** вкладки. Вы увидите `DemoMarqueeControl` доступные для выбора.  
  
11. Перетащите экземпляр `DemoMarqueeControl` на **Form1** область конструктора.  
  
12. В <xref:System.Windows.Forms.Control.Click> вызывать обработчики событий, `Start` и `Stop` методы `DemoMarqueeControl`.  
  
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
  
1.  Задать `MarqueeControlTest` проект в качестве запускаемого проекта и запустите его. Отобразится форма вашей `DemoMarqueeControl`. Нажмите кнопку **запустить** кнопку, чтобы запустить анимацию. Вы увидите мигающий текст и индикаторы перемещение вокруг границы.  
  
## <a name="next-steps"></a>Следующие шаги  
 `MarqueeControlLibrary` Показан пример простой реализации пользовательских элементов управления и связанные с ним конструкторы. В этом примере можно делать более сложным несколькими способами:  
  
-   Изменить значения свойств для `DemoMarqueeControl` в конструкторе. Добавить дополнительные `MarqueBorder` управляет и прикрепите их к родительским экземплярам для создания эффекта вложенной. Поэкспериментируйте с различными настройками для `UpdatePeriod` и свойствами, связанным с подсветкой.  
  
-   Создавать собственные реализации `IMarqueeWidget`. Можно например, создать Мерцающий «neon вход» или знака анимированных изображений.  
  
-   Дополнительно настроить среду разработки. Можно попробовать затенение больше свойств, чем <xref:System.Windows.Forms.Control.Enabled%2A> и <xref:System.Windows.Forms.Control.Visible%2A>, а также добавить новые свойства. Добавьте новые команды конструктора, чтобы упростить общие задачи, такие как закрепление дочерних элементов управления.  
  
-   Лицензия `MarqueeControl`. Дополнительные сведения см. в разделе [как: лицензии компонентов и элементов управления](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57).  
  
-   Управление сериализацией элементов управления и как создать код для них. Дополнительные сведения см. в разделе [динамическое создание исходного кода и компиляция](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Design.ParentControlDesigner>  
 <xref:System.Windows.Forms.Design.DocumentDesigner>  
 <xref:System.ComponentModel.Design.IRootDesigner>  
 <xref:System.ComponentModel.Design.DesignerVerb>  
 <xref:System.Drawing.Design.UITypeEditor>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Практическое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций, применяемых во время разработки](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)  
 [Расширения поддержки времени разработки](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [Пользовательские конструкторы](http://msdn.microsoft.com/library/ca11988e-d38e-44d8-a05d-71362ae7844d)  
 [Библиотека фигур .NET: Образец конструктора](http://windowsforms.net/articles/shapedesigner.aspx)
