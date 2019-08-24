---
title: Пошаговое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b72c449ab68c9bb2ceea6f8ee78abe6771b9a8bd
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016012"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>Пошаговое руководство. Создание элемента управления, использующего преимущества функций времени разработки

Интерфейс времени разработки для пользовательского элемента управления можно расширить путем создания связанного пользовательского конструктора.

В этой статье показано, как создать пользовательский конструктор для пользовательского элемента управления. Вы реализуете `MarqueeControl` тип и связанный класс конструктора с именем `MarqueeControlRootDesigner`.

`MarqueeControl` Тип реализует вид, аналогичный области театра с анимированными индикаторами и мигающим текстом.

Конструктор для этого элемента управления взаимодействует с средой разработки, чтобы обеспечить пользовательский интерфейс во время разработки. С помощью пользовательского конструктора можно собирать пользовательскую `MarqueeControl` реализацию с анимированными индикаторами и мигающим текстом во многих сочетаниях. Собранный элемент управления можно использовать в форме, как и любой другой элемент управления Windows Forms.

По завершении работы с этим пошаговым руководством пользовательский элемент управления будет выглядеть примерно следующим образом:

![Приложение, показывающее текст с текстом и кнопки запуска и окончания.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Полный листинг кода см. в разделе [как Создайте элемент управления Windows Forms, который использует преимущества функций](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))времени разработки.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого пошагового руководства вам потребуется Visual Studio.

## <a name="create-the-project"></a>Создание проекта

Первым шагом является создание проекта приложения. Этот проект будет использоваться для создания приложения, в котором размещается пользовательский элемент управления.

В Visual Studio создайте новый проект приложения Windows Forms и назовите его **маркуиконтролтест**.

## <a name="create-the-control-library-project"></a>Создание проекта библиотеки элементов управления

1. Добавьте в решение проект библиотеки элементов управления Windows Forms. Назовите проект **маркуиконтроллибрари**.

2. С помощью **Обозреватель решений**удалите элемент управления проекта по умолчанию, удалив исходный файл с именем "UserControl1.cs" или "UserControl1. vb" в зависимости от выбранного языка.

3. Добавьте новый <xref:System.Windows.Forms.UserControl> элемент `MarqueeControlLibrary` в проект. Присвойте новому исходному файлу базовое имя **маркуиконтрол**.

4. С помощью **Обозреватель решений**создайте новую папку в `MarqueeControlLibrary` проекте.

5. Щелкните правой кнопкой мыши папку **конструктора** и добавьте новый класс. Назовите его **маркуиконтролрутдесигнер**.

6. Необходимо использовать типы из сборки System. Design, поэтому добавьте эту ссылку в `MarqueeControlLibrary` проект.

## <a name="reference-the-custom-control-project"></a>Ссылка на проект пользовательского элемента управления

Для тестирования пользовательского элемента `MarqueeControlTest` управления будет использоваться проект. Тестовый проект будет получать информацию о пользовательском элементе управления при добавлении в нее `MarqueeControlLibrary` ссылки на проект.

В проекте добавьте в `MarqueeControlLibrary` сборку ссылку на проект. `MarqueeControlTest` Обязательно используйте вкладку **проекты** в диалоговом окне **Добавление ссылки** вместо непосредственной ссылки на `MarqueeControlLibrary` сборку.

## <a name="define-a-custom-control-and-its-custom-designer"></a>Определение пользовательского элемента управления и его пользовательского конструктора

Пользовательский элемент управления будет производным от <xref:System.Windows.Forms.UserControl> класса. Это позволяет элементу управления содержать другие элементы управления, а также обеспечивает большую часть функциональных возможностей по умолчанию.

Пользовательский элемент управления будет иметь связанный пользовательский конструктор. Это позволяет создать уникальный интерфейс разработки, специально предназначенный для пользовательского элемента управления.

Элемент управления связывается с конструктором с помощью <xref:System.ComponentModel.DesignerAttribute> класса. Поскольку вы разрабатываете все поведение пользовательского элемента управления во время разработки, Пользовательский конструктор будет реализовывать <xref:System.ComponentModel.Design.IRootDesigner> интерфейс.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Определение пользовательского элемента управления и его пользовательского конструктора

1. Откройте исходный файл в **редакторе кода.** `MarqueeControl` В верхней части файла импортируйте следующие пространства имен:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <xref:System.ComponentModel.DesignerAttribute> Добавьте`MarqueeControl` в объявление класса. При этом пользовательский элемент управления связывается с его конструктором.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Откройте исходный файл в **редакторе кода.** `MarqueeControlRootDesigner` В верхней части файла импортируйте следующие пространства имен:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Измените объявление `MarqueeControlRootDesigner` для наследования <xref:System.Windows.Forms.Design.DocumentDesigner> от класса. Примените <xref:System.ComponentModel.ToolboxItemFilterAttribute> , чтобы указать взаимодействие конструктора с **панелью элементов**.

   > [!NOTE]
   > Определение `MarqueeControlRootDesigner` класса было заключено в пространство имен с именем маркуиконтроллибрари. Design. Это объявление помещает конструктор в специальное пространство имен, зарезервированное для типов, связанных с конструированием.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Определите конструктор для `MarqueeControlRootDesigner` класса. <xref:System.Diagnostics.Trace.WriteLine%2A> Вставьте оператор в тело конструктора. Это будет полезно для отладки.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>Создание экземпляра пользовательского элемента управления

1. Добавьте новый <xref:System.Windows.Forms.UserControl> элемент `MarqueeControlTest` в проект. Присвойте новому исходному файлу базовое имя **демомаркуиконтрол**.

2. Откройте файл в **редакторе кода.** `DemoMarqueeControl` В верхней части файла импортируйте `MarqueeControlLibrary` пространство имен:

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. Измените объявление `DemoMarqueeControl` для наследования `MarqueeControl` от класса.

4. Выполните построение проекта.

5. Откройте форму Form1 в конструктор Windows Forms.

6. Найдите вкладку **компоненты маркуиконтролтест** на **панели элементов** и откройте ее. Перетащите элемент `DemoMarqueeControl` из **области элементов** на форму.

7. Выполните построение проекта.

## <a name="set-up-the-project-for-design-time-debugging"></a>Настройка проекта для отладки во время разработки

При разработке настраиваемой среды разработки необходимо выполнить отладку элементов управления и компонентов. Существует простой способ настройки проекта, позволяющий выполнять отладку во время разработки. Дополнительные сведения см. в разделе [Пошаговое руководство: Отладка пользовательских элементов управления Windows Forms во](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)время разработки.

1. Щелкните `MarqueeControlLibrary` правой кнопкой мыши проект и выберите пункт **Свойства**.

2. В диалоговом окне **страницы свойств маркуиконтроллибрари** выберите страницу **Отладка** .

3. В разделе **действие при запуске** выберите **Запуск внешней программы**. Вы будете выполнять отладку отдельного экземпляра Visual Studio, поэтому нажмите кнопку с многоточием![(...) в окно свойств в Visual Studio](./media/visual-studio-ellipsis-button.png)), чтобы найти интегрированную среду разработки Visual Studio. Имя исполняемого файла — devenv. exe, и если вы установили в расположение по умолчанию, его путь: *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<Edition > \Common7\IDE\devenv.exe*.

4. Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.

5. Щелкните правой кнопкой мыши проект Маркуиконтроллибрари и выберите **Назначить запускаемым проектом** , чтобы включить эту конфигурацию отладки.

## <a name="checkpoint"></a>Контрольная точка

Теперь все готово для отладки поведения пользовательского элемента управления во время разработки. После определения правильности настройки среды отладки вы проверите связь между пользовательским элементом управления и пользовательским конструктором.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Тестирование среды отладки и ассоциации конструктора

1. Откройте исходный файл маркуиконтролрутдесигнер в **редакторе кода** и поместите точку останова в <xref:System.Diagnostics.Trace.WriteLine%2A> инструкцию.

2. Нажмите клавишу **F5** , чтобы запустить сеанс отладки.

   Создается новый экземпляр Visual Studio.

3. В новом экземпляре Visual Studio откройте решение Маркуиконтролтест. Решение можно легко найти, выбрав **последние проекты** в меню **файл** . Файл решения Маркуиконтролтест. sln будет указан как последний использовавшийся файл.

4. `DemoMarqueeControl` Откройте в конструкторе.

   Экземпляр отладки Visual Studio получает фокус и выполнение останавливается в точке останова. Нажмите клавишу **F5** , чтобы продолжить сеанс отладки.

На этом этапе все готово для разработки и отладки пользовательского элемента управления и связанного с ним пользовательского конструктора. Оставшаяся часть этой статьи сосредоточена на деталях реализации функций элемента управления и конструктора.

## <a name="implement-the-custom-control"></a>Реализация пользовательского элемента управления

`MarqueeControl` —Этос<xref:System.Windows.Forms.UserControl> небольшой настройкой. Он предоставляет два метода: `Start`, который запускает анимацию бегущей строки и `Stop`, в результате которой останавливается анимация. `StartMarquee` `IMarqueeWidget` `StopMarquee` `Stop` `Start` Поскольку содержит дочерние элементы управления, реализующие интерфейс, и перечисляет каждый дочерний элемент управления и вызывают методы и соответственно для каждого дочернего элемента управления. `MarqueeControl` , реализующий интерфейс `IMarqueeWidget`.

Внешний вид `MarqueeBorder` элементов управления и `MarqueeText` зависит от <xref:System.Windows.Forms.Control.OnLayout%2A> макета, поэтому `MarqueeControl` переопределяет метод и вызывает <xref:System.Windows.Forms.Control.PerformLayout%2A> дочерние элементы управления этого типа.

Это экстент `MarqueeControl` настроек. `MarqueeBorder` Функции времени выполнения реализуются элементами управления и `MarqueeText` , а `MarqueeBorderDesigner` функции времени разработки реализуются классами и `MarqueeControlRootDesigner` .

### <a name="to-implement-your-custom-control"></a>Реализация пользовательского элемента управления

1. Откройте исходный файл в **редакторе кода.** `MarqueeControl` Реализуйте методы `Stop`и. `Start`

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Переопределите метод <xref:System.Windows.Forms.Control.OnLayout%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>Создание дочернего элемента управления для пользовательского элемента управления

В `MarqueeControl` будет размещено два вида дочерних элементов управления `MarqueeBorder` : элемент управления и `MarqueeText` элемент управления.

- `MarqueeBorder`: Этот элемент управления рисует границу «огни» вокруг ее границ. Индикаторы помещаются поочередно, поэтому они перемещаются вокруг границы. Скорость, с которой мигают световые индикаторы, определяется свойством `UpdatePeriod`. Несколько других пользовательских свойств определяют другие аспекты внешнего вида элемента управления. Два метода, `StartMarquee` называемые `StopMarquee`и, управляют началом и остановкой анимации.

- `MarqueeText`: Этот элемент управления закрашивает мигающую строку. Как и `UpdatePeriod` элемент управления, скорость, с которой происходит мигание текста, определяется свойством. `MarqueeBorder` Элемент управления также `StartMarquee` имеет методы и `StopMarquee` , общие с `MarqueeBorder` элементом управления. `MarqueeText`

Во время `MarqueeControlRootDesigner` разработки позволяет добавлять `MarqueeControl` эти два типа элементов управления в любое сочетание.

Общие функции двух элементов управления делятся на интерфейс с именем `IMarqueeWidget`. Это позволяет элементу `MarqueeControl` обнаруживать все дочерние элементы управления, связанные с областью, и давать им специальную обработку.

Чтобы реализовать функцию периодической анимации, вы будете использовать <xref:System.ComponentModel.BackgroundWorker> объекты <xref:System.ComponentModel?displayProperty=nameWithType> из пространства имен. Можно использовать <xref:System.Windows.Forms.Timer> объекты, но при наличии большого `IMarqueeWidget` числа объектов один поток пользовательского интерфейса может не поддерживать анимацию.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Создание дочернего элемента управления для пользовательского элемента управления

1. Добавьте в `MarqueeControlLibrary` проект новый элемент класса. Присвойте новому исходному файлу базовое имя "Имаркуивиджет".

2. Откройте исходный файл в **редакторе кода** и измените объявление с `class` на: `interface` `IMarqueeWidget`

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Добавьте следующий код в `IMarqueeWidget` интерфейс, чтобы предоставить два метода и свойство, управляющие анимацией области.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Добавьте в `MarqueeControlLibrary` проект новый элемент **пользовательского элемента управления** . Присвойте новому исходному файлу базовое имя "Маркуитекст".

5. Перетащите компонент из **панели элементов** на элементуправления.`MarqueeText` <xref:System.ComponentModel.BackgroundWorker> Этот компонент позволит `MarqueeText` элементу управления обновляться в асинхронном режиме.

6. В окне **Свойства** установите <xref:System.ComponentModel.BackgroundWorker> для компонента `WorkerReportsProgress` и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> свойства **значение true**. Эти параметры позволяют <xref:System.ComponentModel.BackgroundWorker> компоненту периодически <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> вызывать событие и отменять асинхронные обновления.

   Дополнительные сведения см. в разделе [компонент BackgroundWorker](backgroundworker-component.md).

7. Откройте исходный файл в **редакторе кода.** `MarqueeText` В верхней части файла импортируйте следующие пространства имен:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Измените объявление `MarqueeText` для наследования от <xref:System.Windows.Forms.Label> и для реализации `IMarqueeWidget` интерфейса:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Объявите переменные экземпляра, соответствующие предоставляемым свойствам, и инициализируйте их в конструкторе. Поле определяет, следует ли закрасить текст в цвет, заданный `LightColor` свойством. `isLit`

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Реализовать интерфейс `IMarqueeWidget`.

    `StartMarquee` Методыи`StopMarquee` вызывают методыкомпонента<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> и для запуска и завершения анимации. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> <xref:System.ComponentModel.BackgroundWorker>

    Атрибуты и применяются<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> к свойству,поэтомуоноотображаетсявпользовательскомразделеокносвойствсименем«бегущая`UpdatePeriod`строка». <xref:System.ComponentModel.CategoryAttribute.Category%2A>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Реализуйте методы доступа к свойствам. Вы будете предоставлять клиентам два свойства: `LightColor` и. `DarkColor` К этим <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> свойствам применяются атрибуты и,поэтомусвойстваотображаютсявпользовательскомразделеокносвойствсименем«бегущаястрока».<xref:System.ComponentModel.CategoryAttribute.Category%2A>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Реализуйте обработчики для <xref:System.ComponentModel.BackgroundWorker> событий <xref:System.ComponentModel.BackgroundWorker.DoWork> компонента и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> .

    Обработчик событий закладывается на число миллисекунд, `UpdatePeriod` указанное затем, вызывает <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> событие, пока код не прекратит анимацию, вызвав <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>. <xref:System.ComponentModel.BackgroundWorker.DoWork>

    Обработчик <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> событий переключает текст между светлым и темным состоянием, чтобы придать ему внешний вид.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Переопределите <xref:System.Windows.Forms.Control.OnPaint%2A> метод, чтобы включить анимацию.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Нажмите клавишу **F6** , чтобы создать решение.

## <a name="create-the-marqueeborder-child-control"></a>Создание дочернего элемента управления Маркуибордер

Элемент управления является немного более сложным, `MarqueeText` чем элемент управления. `MarqueeBorder` Он имеет больше свойств, и анимация в <xref:System.Windows.Forms.Control.OnPaint%2A> методе является более сложной. В принципе, он очень похож на `MarqueeText` элемент управления.

Поскольку элемент управления может иметь дочерние элементы управления, он должен <xref:System.Windows.Forms.Control.Layout> знать о событиях. `MarqueeBorder`

### <a name="to-create-the-marqueeborder-control"></a>Создание элемента управления Маркуибордер

1. Добавьте в `MarqueeControlLibrary` проект новый элемент **пользовательского элемента управления** . Присвойте новому исходному файлу базовое имя "Маркуибордер".

2. Перетащите компонент из **панели элементов** на элементуправления.`MarqueeBorder` <xref:System.ComponentModel.BackgroundWorker> Этот компонент позволит `MarqueeBorder` элементу управления обновляться в асинхронном режиме.

3. В окне **Свойства** установите <xref:System.ComponentModel.BackgroundWorker> для компонента `WorkerReportsProgress` и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> свойства **значение true**. Эти параметры позволяют <xref:System.ComponentModel.BackgroundWorker> компоненту периодически <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> вызывать событие и отменять асинхронные обновления. Дополнительные сведения см. в разделе [компонент BackgroundWorker](backgroundworker-component.md).

4. В окне **Свойства** нажмите кнопку **события** . Присоединение обработчиков <xref:System.ComponentModel.BackgroundWorker.DoWork> для <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> событий и.

5. Откройте исходный файл в **редакторе кода.** `MarqueeBorder` В верхней части файла импортируйте следующие пространства имен:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Измените объявление `MarqueeBorder` для наследования от <xref:System.Windows.Forms.Panel> и для реализации `IMarqueeWidget` интерфейса.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Объявите два перечисления для `MarqueeBorder` управления состоянием элемента управления: `MarqueeSpinDirection`, которое определяет направление, в котором огни вращается вокруг границы, и `MarqueeLightShape`, определяющий форму огней (квадратный или круглый). Поместите эти объявления перед `MarqueeBorder` объявлением класса.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Объявите переменные экземпляра, соответствующие предоставляемым свойствам, и инициализируйте их в конструкторе.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Реализовать интерфейс `IMarqueeWidget`.

    `StartMarquee` Методыи`StopMarquee` вызывают методыкомпонента<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> и для запуска и завершения анимации. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> <xref:System.ComponentModel.BackgroundWorker>

    Поскольку элемент управления может содержать дочерние элементы `StartMarquee` управления, метод перечисляет все дочерние `StartMarquee` элементы управления и вызывает методы, реализующие `IMarqueeWidget`. `MarqueeBorder` `StopMarquee` Метод имеет аналогичную реализацию.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Реализуйте методы доступа к свойствам. `MarqueeBorder` Элемент управления имеет несколько свойств для управления его внешним видом.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Реализуйте обработчики для <xref:System.ComponentModel.BackgroundWorker> событий <xref:System.ComponentModel.BackgroundWorker.DoWork> компонента и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> .

    Обработчик событий закладывается на число миллисекунд, `UpdatePeriod` указанное затем, вызывает <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> событие, пока код не прекратит анимацию, вызвав <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>. <xref:System.ComponentModel.BackgroundWorker.DoWork>

    Обработчик событий увеличивает расположение «базового» освещения, из которого определяется светлое или темное состояние других источников света, и <xref:System.Windows.Forms.Control.Refresh%2A> вызывает метод, чтобы элемент управления переводился в перерисовку. <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Реализуйте вспомогательные методы `IsLit` и `DrawLight`.

    `IsLit` Метод определяет цвет освещения в заданной позиции. Лампочки, которые являются «освещенными», рисуются цветом, `LightColor` заданным свойством, а те, которые являются «темными», рисуются `DarkColor` цветом, заданным свойством.

    `DrawLight` Метод рисует источник освещения с помощью соответствующего цвета, формы и расположения.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Переопределите методы <xref:System.Windows.Forms.Control.OnPaint%2A>и. <xref:System.Windows.Forms.Control.OnLayout%2A>

    Метод рисует индикаторы вдоль краев `MarqueeBorder` элемента управления. <xref:System.Windows.Forms.Control.OnPaint%2A>

    Поскольку метод зависит от измерений `MarqueeBorder` элемента управления, его необходимо вызывать при каждом изменении макета. <xref:System.Windows.Forms.Control.OnPaint%2A> Чтобы добиться этого, переопределите <xref:System.Windows.Forms.Control.OnLayout%2A> и вызовите метод. <xref:System.Windows.Forms.Control.Refresh%2A>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>Создание пользовательского конструктора для тени и фильтрации свойств

`MarqueeControlRootDesigner` Класс предоставляет реализацию для корневого конструктора. Помимо этого конструктора, который работает `MarqueeControl`с, необходим пользовательский конструктор, специально связанный `MarqueeBorder` с элементом управления. Этот конструктор предоставляет настраиваемое поведение, которое подходит для контекста пользовательского корневого конструктора.

В `MarqueeBorderDesigner` частности, выполнит "тень" и отфильтрует определенные `MarqueeBorder` свойства элемента управления, изменив их взаимодействие с средой разработки.

Перехват вызовов метода доступа к свойству компонента называется "тенью". Он позволяет конструктору отслеживанить значение, заданное пользователем, и при необходимости передать это значение в разрабатываемый компонент.

В этом примере <xref:System.Windows.Forms.Control.Visible%2A> свойства и <xref:System.Windows.Forms.Control.Enabled%2A> будут скрыты с `MarqueeBorderDesigner`помощью `MarqueeBorder` , что не позволяет пользователю сделать элемент управления невидимым или отключенным во время разработки.

Конструкторы также могут добавлять и удалять свойства. В этом примере <xref:System.Windows.Forms.Control.Padding%2A> свойство будет удалено во время разработки, `MarqueeBorder` так как элемент управления программно устанавливает заполнение на основе размера источников света, заданных `LightSize` свойством.

Базовый класс для `MarqueeBorderDesigner` — <xref:System.ComponentModel.Design.ComponentDesigner>, который содержит методы, которые могут изменять атрибуты, свойства и события, предоставляемые элементом управления во время разработки:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

При изменении открытого интерфейса компонента с помощью этих методов следует соблюдать следующие правила.

- Добавлять или удалять элементы только в `PreFilter` методах

- Изменение существующих элементов только в `PostFilter` методах

- Всегда вызывайте базовую реализацию сначала в `PreFilter` методах

- Всегда вызывайте базовую реализацию последней в `PostFilter` методах

Соблюдение этих правил гарантирует, что все конструкторы в среде времени разработки будут иметь единообразное представление всех разрабатываемых компонентов.

<xref:System.ComponentModel.Design.ComponentDesigner> Класс предоставляет словарь для управления значениями затененных свойств, что освобождает вас от необходимости создавать конкретные переменные экземпляра.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Создание пользовательского конструктора для теневого копирования и свойств фильтра

1. Щелкните правой кнопкой мыши папку **конструктора** и добавьте новый класс. Присвойте исходному файлу базовое имя **маркуибордердесигнер**.

2. Откройте исходный файл Маркуибордердесигнер в **редакторе кода**. В верхней части файла импортируйте следующие пространства имен:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Измените объявление `MarqueeBorderDesigner` , чтобы наследовать от <xref:System.Windows.Forms.Design.ParentControlDesigner>.

    Поскольку элемент управления может содержать дочерние `MarqueeBorderDesigner` элементы управления, <xref:System.Windows.Forms.Design.ParentControlDesigner>наследует от, который обрабатывает взаимодействие типа «родители-потомки». `MarqueeBorder`

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Переопределите базовую реализацию <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Реализуйте свойства <xref:System.Windows.Forms.Control.Enabled%2A> и <xref:System.Windows.Forms.Control.Visible%2A>. Эти реализации затениют свойства элемента управления.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>Обработку изменений компонентов

Класс предоставляет пользовательские возможности времени разработки `MarqueeControl` для экземпляров. `MarqueeControlRootDesigner` Большая часть функций времени разработки наследуется от <xref:System.Windows.Forms.Design.DocumentDesigner> класса. В коде будут реализованы две определенные настройки: обработка изменений компонентов и Добавление команд конструктора.

По мере разработки пользователями `MarqueeControl` своих экземпляров корневой конструктор будет отслеживанию изменений `MarqueeControl` в и его дочерних элементах управления. Среда разработки предоставляет удобную службу <xref:System.ComponentModel.Design.IComponentChangeService>для отслеживания изменений состояния компонента.

Чтобы получить ссылку на эту службу, запросите среду с помощью <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> метода. Если запрос выполнен успешно, конструктор может присоединить обработчик для <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> события и выполнить все задачи, необходимые для поддержания стабильного состояния во время разработки.

В случае `MarqueeControlRootDesigner` класса <xref:System.Windows.Forms.Control.Refresh%2A> метод будет вызываться для каждого `IMarqueeWidget` объекта, содержащегося в `MarqueeControl`. Это приведет к тому `IMarqueeWidget` , что объект будет правильно перерисовываться при изменении свойств <xref:System.Windows.Forms.Control.Size%2A> , таких как его родительский элемент.

### <a name="to-handle-component-changes"></a>Для управления изменениями компонентов

1. Откройте исходный файл в **редакторе кода** и переопределите <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> метод. `MarqueeControlRootDesigner` Вызовите базовую реализацию <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> запроса и <xref:System.ComponentModel.Design.IComponentChangeService>для.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Реализуйте <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> обработчик событий. Проверьте тип компонента отправки и, если он является `IMarqueeWidget`, вызовите его <xref:System.Windows.Forms.Control.Refresh%2A> метод.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>Добавление команд конструктора в пользовательский конструктор

Команда конструктора — это команда меню, связанная с обработчиком событий. Команды конструктора добавляются в контекстное меню компонента во время разработки. Дополнительные сведения см. в разделе <xref:System.ComponentModel.Design.DesignerVerb>.

В конструкторы вы добавите две команды конструктора: **Запустите тест** и **завершите тест**. Эти глаголы позволяют просматривать поведение во время выполнения в `MarqueeControl` процессе разработки. Эти команды будут добавлены в `MarqueeControlRootDesigner`.

При вызове **запуска теста** обработчик событий команды вызывает `StartMarquee` метод для. `MarqueeControl` При вызове `StopMarquee` метода " `MarqueeControl`приостанавливается" обработчик событий команды вызывает метод для. Реализация `StartMarquee` методов и `StopMarquee` вызывает эти методы для вложенных элементов управления, которые реализуют `IMarqueeWidget`, поэтому все `IMarqueeWidget` содержащиеся в нем элементы управления также будут участвовать в тестировании.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Добавление команд конструктора в пользовательские конструкторы

1. В классе добавьте обработчики событий с именами `OnVerbRunTest` и `OnVerbStopTest`. `MarqueeControlRootDesigner`

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Соедините эти обработчики событий с соответствующими командами конструктора. `MarqueeControlRootDesigner`наследует <xref:System.ComponentModel.Design.DesignerVerbCollection> от своего базового класса. Вы создадите два новых <xref:System.ComponentModel.Design.DesignerVerb> объекта и добавите их в эту коллекцию <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> в методе.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>Создание настраиваемого UITypeEditor

При создании пользовательской среды разработки для пользователей часто желательно создать пользовательское взаимодействие с окно свойств. Это можно сделать, создав <xref:System.Drawing.Design.UITypeEditor>.

`MarqueeBorder` Элемент управления предоставляет несколько свойств в окно свойств. Два из этих свойств `MarqueeSpinDirection` и `MarqueeLightShape` представлены перечислениями. Чтобы продемонстрировать использование редактора типов пользовательского интерфейса, `MarqueeLightShape` свойство будет иметь связанный <xref:System.Drawing.Design.UITypeEditor> класс.

### <a name="to-create-a-custom-ui-type-editor"></a>Создание пользовательского редактора типов пользовательского интерфейса

1. Откройте исходный файл в **редакторе кода.** `MarqueeBorder`

2. В определении `MarqueeBorder` класса объявите класс с именем `LightShapeEditor` , производным от <xref:System.Drawing.Design.UITypeEditor>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Объявите <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> переменную экземпляра `editorService`с именем.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Переопределите метод <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> . Эта реализация возвращает <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, что указывает среде разработки, как `LightShapeEditor`отобразить.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Переопределите метод <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> . Эта реализация запрашивает в среде <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> разработки объект. В `LightShapeSelectionControl`случае успеха создается. Метод вызывается для `LightShapeEditor`запуска. <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> Возвращаемое значение этого вызова возвращается в среду разработки.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>Создание элемента управления View для пользовательского UITypeEditor

Свойство поддерживает два типа простых фигур: `Square` и `Circle`. `MarqueeLightShape` Вы создадите пользовательский элемент управления, используемый исключительно в целях графического отображения этих значений в окно свойств. Этот пользовательский элемент управления будет использоваться <xref:System.Drawing.Design.UITypeEditor> для взаимодействия с окно свойств.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Создание элемента управления представления для пользовательского редактора типов пользовательского интерфейса

1. Добавьте новый <xref:System.Windows.Forms.UserControl> элемент `MarqueeControlLibrary` в проект. Присвойте новому исходному файлу базовое имя **лигхтшапеселектионконтрол**.

2. Перетащите два <xref:System.Windows.Forms.Panel> элемента управления из **панели элементов** в `LightShapeSelectionControl`область. Назовите `squarePanel` их `circlePanel`и. Расположите их параллельно. Задайте для <xref:System.Windows.Forms.Panel>свойстваобоих элементов управления значение **(60, 60).** <xref:System.Windows.Forms.Control.Size%2A> Присвойте `squarePanel`свойству элемента управления значение **(8, 10).** <xref:System.Windows.Forms.Control.Location%2A> Присвойте `circlePanel`свойству элемента управления значение **(80, 10).** <xref:System.Windows.Forms.Control.Location%2A> Наконец, задайте <xref:System.Windows.Forms.Control.Size%2A> для свойства значение `LightShapeSelectionControl` **(150, 80)** .

3. Откройте исходный файл в **редакторе кода.** `LightShapeSelectionControl` В верхней части файла импортируйте <xref:System.Windows.Forms.Design?displayProperty=nameWithType> пространство имен:

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. Реализуйте <xref:System.Windows.Forms.Control.Click> обработчики событий `squarePanel` для `circlePanel` элементов управления и. Эти методы вызывают <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> для завершения пользовательского <xref:System.Drawing.Design.UITypeEditor> сеанса редактирования.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. Объявите <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> переменную экземпляра `editorService`с именем.

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. Объявите `MarqueeLightShape` переменную экземпляра `lightShapeValue`с именем.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. `circlePanel` <xref:System.Windows.Forms.Control.Click> `squarePanel` В конструкторе присоедините обработчики событий<xref:System.Windows.Forms.Control.Click> к событиям элементов управления и. `LightShapeSelectionControl` Кроме того, определите перегрузку конструктора, которая `MarqueeLightShape` назначает значение `lightShapeValue` полю в среде разработки.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. В методе отсоедините обработчики <xref:System.Windows.Forms.Control.Click>событий. <xref:System.ComponentModel.Component.Dispose%2A>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. В **обозревателе решений** нажмите кнопку **Показать все файлы**. Откройте файл LightShapeSelectionControl.Designer.cs или лигхтшапеселектионконтрол. Designer. vb и удалите определение <xref:System.ComponentModel.Component.Dispose%2A> метода по умолчанию.

10. Реализуйте свойство `LightShape`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. Переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A> . В этой реализации будет нарисован закрашенный квадрат и круг. Он также выделяет выбранное значение, рисуя границу вокруг одной или другой фигуры.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>Тестирование пользовательского элемента управления в конструкторе

На этом этапе можно построить `MarqueeControlLibrary` проект. Протестируйте реализацию, создав элемент управления, который наследует от `MarqueeControl` класса и использует его в форме.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Создание пользовательской реализации Маркуиконтрол

1. Откройте `DemoMarqueeControl` в конструкторе Windows Forms. При этом создается экземпляр `DemoMarqueeControl` типа, который отображается в экземпляре `MarqueeControlRootDesigner` типа.

2. На **панели элементов**откройте вкладку **компоненты маркуиконтроллибрари** . Вы увидите элементы управления `MarqueeBorder` и `MarqueeText` , доступные для выбора.

3. Перетащите экземпляр `MarqueeBorder` элемента управления `DemoMarqueeControl` на поверхность конструктора. Закрепление `MarqueeBorder` этого элемента управления в родительском элементе управления.

4. Перетащите экземпляр `MarqueeText` элемента управления `DemoMarqueeControl` на поверхность конструктора.

5. Постройте решение.

6. Щелкните `DemoMarqueeControl` правой кнопкой мыши и в контекстном меню выберите пункт **запустить тест** , чтобы запустить анимацию. Нажмите кнопку " **Закрыть тест** ", чтобы прерывать анимацию.

7. Откройте форму **Form1** в конструкторе.

8. Поместите два <xref:System.Windows.Forms.Button> элемента управления в форму. Присвойте `startButton` им `stopButton`имя и и измените <xref:System.Windows.Forms.Control.Text%2A> значения свойств на **Start** и **останавливаться**соответственно.

9. Реализуйте <xref:System.Windows.Forms.Control.Click> обработчики событий <xref:System.Windows.Forms.Button> для обоих элементов управления.

10. На **панели элементов**откройте вкладку **компоненты маркуиконтролтест** . Вы увидите `DemoMarqueeControl` доступные для выбора.

11. Перетащите экземпляр `DemoMarqueeControl` на поверхность конструктора **Form1** .

12. В обработчиках `Start` `Stop` `DemoMarqueeControl`событий вызовите методы и для. <xref:System.Windows.Forms.Control.Click>

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

13. `MarqueeControlTest` Задайте проект в качестве запускаемого проекта и запустите его. Вы увидите форму, в которой отображается `DemoMarqueeControl`. Нажмите кнопку **запустить** , чтобы запустить анимацию. Вы увидите, что текст мигает и индикаторы перемещаются вокруг границы.

## <a name="next-steps"></a>Следующие шаги

В `MarqueeControlLibrary` примере демонстрируется простая реализация пользовательских элементов управления и связанных с ними конструкторов. Сделать этот пример более сложным можно несколькими способами:

- Измените значения свойств для `DemoMarqueeControl` в конструкторе. Добавьте дополнительные `MarqueBorder` элементы управления и закрепите их в своих родительских экземплярах, чтобы создать вложенный результат. Экспериментируйте с различными настройками `UpdatePeriod` для и свойств, связанных с источниками.

- Создайте собственные реализации `IMarqueeWidget`. Например, можно создать мигающий знак «Neon» или анимированный знак с несколькими изображениями.

- Дальнейшая настройка взаимодействия во время разработки. Можно попытаться затенить больше <xref:System.Windows.Forms.Control.Enabled%2A> свойств <xref:System.Windows.Forms.Control.Visible%2A>, чем и, и добавить новые свойства. Добавьте новые команды конструктора для упрощения распространенных задач, таких как закрепление дочерних элементов управления.

- `MarqueeControl`Лицензия.

- Управление сериализацией элементов управления и созданием кода для них. Дополнительные сведения см. в разделе [Динамическое создание и компиляция исходного кода](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
