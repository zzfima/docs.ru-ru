---
title: 'Пошаговое руководство: Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки'
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 64f637b232cf21701185e7b87d86f63fdece5127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459521"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>Пошаговое руководство. Создание элемента управления, который использует преимущества функций времени разработки

Интерфейс времени разработки для пользовательского элемента управления можно расширить путем создания связанного пользовательского конструктора.

В этой статье показано, как создать пользовательский конструктор для пользовательского элемента управления. Вы реализуете тип `MarqueeControl` и связанный класс конструктора с именем `MarqueeControlRootDesigner`.

Тип `MarqueeControl` реализует вид, аналогичный области театра с анимированными индикаторами и мигающим текстом.

Конструктор для этого элемента управления взаимодействует с средой разработки, чтобы обеспечить пользовательский интерфейс во время разработки. С помощью пользовательского конструктора можно собрать пользовательскую реализацию `MarqueeControl` с анимированными индикаторами и мигающим текстом во многих сочетаниях. Собранный элемент управления можно использовать в форме, как и любой другой элемент управления Windows Forms.

По завершении работы с этим пошаговым руководством пользовательский элемент управления будет выглядеть примерно следующим образом:

![Приложение, показывающее текст с текстом и кнопки запуска и окончания.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Полный листинг кода см. в разделе [как создать элемент управления Windows Forms, который использует преимущества функций времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).

## <a name="prerequisites"></a>Необходимые компоненты

Для выполнения этого пошагового руководства вам потребуется Visual Studio.

## <a name="create-the-project"></a>Создание проекта

Первым шагом является создание проекта приложения. Этот проект будет использоваться для создания приложения, в котором размещается пользовательский элемент управления.

В Visual Studio создайте новый проект приложения Windows Forms и назовите его **маркуиконтролтест**.

## <a name="create-the-control-library-project"></a>Создание проекта библиотеки элементов управления

1. Добавьте в решение проект библиотеки элементов управления Windows Forms. Назовите проект **маркуиконтроллибрари**.

2. С помощью **Обозреватель решений**удалите элемент управления проекта по умолчанию, удалив исходный файл с именем "UserControl1.cs" или "UserControl1. vb" в зависимости от выбранного языка.

3. Добавьте новый элемент <xref:System.Windows.Forms.UserControl> в проект `MarqueeControlLibrary`. Присвойте новому исходному файлу базовое имя **маркуиконтрол**.

4. С помощью **Обозреватель решений**создайте новую папку в проекте `MarqueeControlLibrary`.

5. Щелкните правой кнопкой мыши папку **конструктора** и добавьте новый класс. Назовите его **маркуиконтролрутдесигнер**.

6. Необходимо использовать типы из сборки System. Design, поэтому добавьте эту ссылку в проект `MarqueeControlLibrary`.

## <a name="reference-the-custom-control-project"></a>Ссылка на проект пользовательского элемента управления

Для тестирования пользовательского элемента управления будет использоваться проект `MarqueeControlTest`. Тестовый проект будет получать информацию о пользовательском элементе управления при добавлении ссылки проекта на сборку `MarqueeControlLibrary`.

В проекте `MarqueeControlTest` добавьте ссылку на проект для сборки `MarqueeControlLibrary`. Обязательно используйте вкладку **проекты** в диалоговом окне **Добавление ссылки** вместо ссылки на сборку `MarqueeControlLibrary` напрямую.

## <a name="define-a-custom-control-and-its-custom-designer"></a>Определение пользовательского элемента управления и его пользовательского конструктора

Пользовательский элемент управления будет производным от класса <xref:System.Windows.Forms.UserControl>. Это позволяет элементу управления содержать другие элементы управления, а также обеспечивает большую часть функциональных возможностей по умолчанию.

Пользовательский элемент управления будет иметь связанный пользовательский конструктор. Это позволяет создать уникальный интерфейс разработки, специально предназначенный для пользовательского элемента управления.

Элемент управления связывается с конструктором с помощью класса <xref:System.ComponentModel.DesignerAttribute>. Поскольку вы разрабатываете все поведение пользовательского элемента управления во время разработки, Пользовательский конструктор будет реализовывать интерфейс <xref:System.ComponentModel.Design.IRootDesigner>.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Определение пользовательского элемента управления и его пользовательского конструктора

1. Откройте исходный файл `MarqueeControl` в **редакторе кода**. В верхней части файла импортируйте следующие пространства имен:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Добавьте <xref:System.ComponentModel.DesignerAttribute> в объявление класса `MarqueeControl`. При этом пользовательский элемент управления связывается с его конструктором.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Откройте исходный файл `MarqueeControlRootDesigner` в **редакторе кода**. В верхней части файла импортируйте следующие пространства имен:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Измените объявление `MarqueeControlRootDesigner` для наследования от класса <xref:System.Windows.Forms.Design.DocumentDesigner>. Примените <xref:System.ComponentModel.ToolboxItemFilterAttribute>, чтобы указать взаимодействие конструктора с **панелью элементов**.

   > [!NOTE]
   > Определение класса `MarqueeControlRootDesigner` было заключено в пространство имен с именем Маркуиконтроллибрари. Design. Это объявление помещает конструктор в специальное пространство имен, зарезервированное для типов, связанных с конструированием.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Определите конструктор для класса `MarqueeControlRootDesigner`. Вставьте оператор <xref:System.Diagnostics.Trace.WriteLine%2A> в тексте конструктора. Это будет полезно для отладки.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>Создание экземпляра пользовательского элемента управления

1. Добавьте новый элемент <xref:System.Windows.Forms.UserControl> в проект `MarqueeControlTest`. Присвойте новому исходному файлу базовое имя **демомаркуиконтрол**.

2. Откройте файл `DemoMarqueeControl` в **редакторе кода**. В верхней части файла импортируйте `MarqueeControlLibrary` пространство имен:

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. Измените объявление `DemoMarqueeControl` для наследования от класса `MarqueeControl`.

4. Выполните построение проекта.

5. Откройте форму Form1 в конструктор Windows Forms.

6. Найдите вкладку **компоненты маркуиконтролтест** на **панели элементов** и откройте ее. Перетащите `DemoMarqueeControl` с **панели элементов** на форму.

7. Выполните построение проекта.

## <a name="set-up-the-project-for-design-time-debugging"></a>Настройка проекта для отладки во время разработки

При разработке настраиваемой среды разработки необходимо выполнить отладку элементов управления и компонентов. Существует простой способ настройки проекта, позволяющий выполнять отладку во время разработки. Дополнительные сведения см. [в разделе Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

1. Щелкните правой кнопкой мыши проект `MarqueeControlLibrary` и выберите пункт **Свойства**.

2. В диалоговом окне **страницы свойств маркуиконтроллибрари** выберите страницу **Отладка** .

3. В разделе **действие при запуске** выберите **Запуск внешней программы**. Вы будете выполнять отладку отдельного экземпляра Visual Studio, поэтому нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio](./media/visual-studio-ellipsis-button.png)), чтобы найти интегрированную среду разработки Visual Studio. Имя исполняемого файла — devenv. exe, и если вы установили в расположение по умолчанию, его путь: *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<edition > \Common7\IDE\devenv.exe*.

4. Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.

5. Щелкните правой кнопкой мыши проект Маркуиконтроллибрари и выберите **Назначить запускаемым проектом** , чтобы включить эту конфигурацию отладки.

## <a name="checkpoint"></a>Контрольная точка

Теперь все готово для отладки поведения пользовательского элемента управления во время разработки. После определения правильности настройки среды отладки вы проверите связь между пользовательским элементом управления и пользовательским конструктором.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Тестирование среды отладки и ассоциации конструктора

1. Откройте исходный файл Маркуиконтролрутдесигнер в **редакторе кода** и поместите точку останова в оператор <xref:System.Diagnostics.Trace.WriteLine%2A>.

2. Нажмите клавишу **F5** , чтобы запустить сеанс отладки.

   Создается новый экземпляр Visual Studio.

3. В новом экземпляре Visual Studio откройте решение Маркуиконтролтест. Решение можно легко найти, выбрав **последние проекты** в меню **файл** . Файл решения Маркуиконтролтест. sln будет указан как последний использовавшийся файл.

4. Откройте `DemoMarqueeControl` в конструкторе.

   Экземпляр отладки Visual Studio получает фокус и выполнение останавливается в точке останова. Нажмите клавишу **F5** , чтобы продолжить сеанс отладки.

На этом этапе все готово для разработки и отладки пользовательского элемента управления и связанного с ним пользовательского конструктора. Оставшаяся часть этой статьи сосредоточена на деталях реализации функций элемента управления и конструктора.

## <a name="implement-the-custom-control"></a>Реализация пользовательского элемента управления

`MarqueeControl` является <xref:System.Windows.Forms.UserControl> с небольшой настройкой. Он предоставляет два метода: `Start`, которые запускают анимацию бегущей строки и `Stop`, что останавливает анимацию. Поскольку `MarqueeControl` содержит дочерние элементы управления, реализующие интерфейс `IMarqueeWidget`, `Start` и `Stop` перечисление каждого дочернего элемента управления и вызов методов `StartMarquee` и `StopMarquee` соответственно, для каждого дочернего элемента управления, реализующего `IMarqueeWidget`.

Внешний вид элементов управления `MarqueeBorder` и `MarqueeText` зависит от макета, поэтому `MarqueeControl` переопределяет метод <xref:System.Windows.Forms.Control.OnLayout%2A> и вызывает <xref:System.Windows.Forms.Control.PerformLayout%2A> для дочерних элементов управления этого типа.

Это экстент настроек `MarqueeControl`. Функции времени выполнения реализуются элементами управления `MarqueeBorder` и `MarqueeText`, а функции времени разработки реализуются классами `MarqueeBorderDesigner` и `MarqueeControlRootDesigner`.

### <a name="to-implement-your-custom-control"></a>Реализация пользовательского элемента управления

1. Откройте исходный файл `MarqueeControl` в **редакторе кода**. Реализуйте методы `Start` и `Stop`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Переопределите метод <xref:System.Windows.Forms.Control.OnLayout%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>Создание дочернего элемента управления для пользовательского элемента управления

В `MarqueeControl` будут размещаться два вида дочерних элементов управления: элемент управления `MarqueeBorder` и элемент управления `MarqueeText`.

- `MarqueeBorder`: этот элемент управления рисует границу «огни» вокруг ее границ. Индикаторы помещаются поочередно, поэтому они перемещаются вокруг границы. Скорость, с которой мигают световые индикаторы, определяется свойством `UpdatePeriod`. Несколько других пользовательских свойств определяют другие аспекты внешнего вида элемента управления. Два метода, называемые `StartMarquee` и `StopMarquee`, управляют началом и остановкой анимации.

- `MarqueeText`: этот элемент управления рисует мигающую строку. Как и элемент управления `MarqueeBorder`, скорость, с которой происходит мигание текста, определяется свойством `UpdatePeriod`. Элемент управления `MarqueeText` также имеет `StartMarquee` и `StopMarquee` методы, общие с элементом управления `MarqueeBorder`.

Во время разработки `MarqueeControlRootDesigner` позволяет добавлять эти два типа элементов управления в `MarqueeControl` в любом сочетании.

Общие функции двух элементов управления делятся на интерфейс с именем `IMarqueeWidget`. Это позволяет `MarqueeControl` обнаруживать дочерние элементы управления, связанные с областью, и давать им специальную обработку.

Чтобы реализовать функцию периодической анимации, вы будете использовать <xref:System.ComponentModel.BackgroundWorker> объекты из пространства имен <xref:System.ComponentModel?displayProperty=nameWithType>. Можно использовать <xref:System.Windows.Forms.Timer> объекты, но если имеется много `IMarqueeWidget` объектов, то один поток пользовательского интерфейса может не поддерживать анимацию.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Создание дочернего элемента управления для пользовательского элемента управления

1. Добавьте новый элемент класса в проект `MarqueeControlLibrary`. Присвойте новому исходному файлу базовое имя "Имаркуивиджет".

2. Откройте исходный файл `IMarqueeWidget` в **редакторе кода** и измените объявление с `class` на `interface`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Добавьте следующий код в интерфейс `IMarqueeWidget`, чтобы предоставить два метода и свойство, управляющие анимацией области.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Добавьте новый элемент **пользовательского элемента управления** в проект `MarqueeControlLibrary`. Присвойте новому исходному файлу базовое имя "Маркуитекст".

5. Перетащите <xref:System.ComponentModel.BackgroundWorker> компонент с **панели элементов** на элемент управления `MarqueeText`. Этот компонент позволяет асинхронно обновлять элемент управления `MarqueeText`.

6. В окне **Свойства** задайте для свойств `WorkerReportsProgress` и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> компонента <xref:System.ComponentModel.BackgroundWorker> **значение true**. Эти параметры позволяют компоненту <xref:System.ComponentModel.BackgroundWorker> периодически создавать событие <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> и отменять асинхронные обновления.

   Дополнительные сведения см. в разделе [компонент BackgroundWorker](backgroundworker-component.md).

7. Откройте исходный файл `MarqueeText` в **редакторе кода**. В верхней части файла импортируйте следующие пространства имен:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Измените объявление `MarqueeText` для наследования от <xref:System.Windows.Forms.Label> и для реализации интерфейса `IMarqueeWidget`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Объявите переменные экземпляра, соответствующие предоставляемым свойствам, и инициализируйте их в конструкторе. Поле `isLit` определяет, будет ли текст закрашен цветом, заданным свойством `LightColor`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Реализовать интерфейс `IMarqueeWidget`.

    Методы `StartMarquee` и `StopMarquee` вызывают методы <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> и <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> <xref:System.ComponentModel.BackgroundWorker> компонента для запуска и завершения анимации.

    Атрибуты <xref:System.ComponentModel.CategoryAttribute.Category%2A> и <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> применяются к свойству `UpdatePeriod`, поэтому оно отображается в пользовательском разделе окно свойств с названием «бегущая строка».

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Реализуйте методы доступа к свойствам. Клиентам предоставляются два свойства: `LightColor` и `DarkColor`. К этим свойствам применяются атрибуты <xref:System.ComponentModel.CategoryAttribute.Category%2A> и <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>, поэтому свойства отображаются в пользовательском разделе окно свойств с именем «бегущая строка».

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Реализуйте обработчики для событий <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> компонента <xref:System.ComponentModel.BackgroundWorker>.

    Обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork> приостанавливается на число миллисекунд, указанное в `UpdatePeriod` затем вызывает событие <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, пока код не прекратит анимацию, вызвав <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    Обработчик событий <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> переключает текст между светлым и темным состоянием, чтобы придать внешний вид мигающим.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A>, чтобы включить анимацию.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Нажмите клавишу **F6** , чтобы создать решение.

## <a name="create-the-marqueeborder-child-control"></a>Создание дочернего элемента управления Маркуибордер

Элемент управления `MarqueeBorder` является немного более сложным, чем элемент управления `MarqueeText`. Он имеет больше свойств, и анимация в методе <xref:System.Windows.Forms.Control.OnPaint%2A> является более сложной. В принципе, он очень похож на элемент управления `MarqueeText`.

Поскольку элемент управления `MarqueeBorder` может иметь дочерние элементы управления, он должен знать о событиях <xref:System.Windows.Forms.Control.Layout>.

### <a name="to-create-the-marqueeborder-control"></a>Создание элемента управления Маркуибордер

1. Добавьте новый элемент **пользовательского элемента управления** в проект `MarqueeControlLibrary`. Присвойте новому исходному файлу базовое имя "Маркуибордер".

2. Перетащите <xref:System.ComponentModel.BackgroundWorker> компонент с **панели элементов** на элемент управления `MarqueeBorder`. Этот компонент позволяет асинхронно обновлять элемент управления `MarqueeBorder`.

3. В окне **Свойства** задайте для свойств `WorkerReportsProgress` и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> компонента <xref:System.ComponentModel.BackgroundWorker> **значение true**. Эти параметры позволяют компоненту <xref:System.ComponentModel.BackgroundWorker> периодически создавать событие <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> и отменять асинхронные обновления. Дополнительные сведения см. в разделе [компонент BackgroundWorker](backgroundworker-component.md).

4. В окне **Свойства** нажмите кнопку **события** . Присоединение обработчиков для событий <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.

5. Откройте исходный файл `MarqueeBorder` в **редакторе кода**. В верхней части файла импортируйте следующие пространства имен:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Измените объявление `MarqueeBorder` для наследования от <xref:System.Windows.Forms.Panel> и для реализации интерфейса `IMarqueeWidget`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Объявите два перечисления для управления состоянием элемента управления `MarqueeBorder`: `MarqueeSpinDirection`, определяющее направление, в котором огни вращается вокруг границы, и `MarqueeLightShape`, который определяет форму огней (квадратная или круглая). Поместите эти объявления перед объявлением класса `MarqueeBorder`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Объявите переменные экземпляра, соответствующие предоставляемым свойствам, и инициализируйте их в конструкторе.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Реализовать интерфейс `IMarqueeWidget`.

    Методы `StartMarquee` и `StopMarquee` вызывают методы <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> и <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> <xref:System.ComponentModel.BackgroundWorker> компонента для запуска и завершения анимации.

    Поскольку элемент управления `MarqueeBorder` может содержать дочерние элементы управления, метод `StartMarquee` перечисляет все дочерние элементы управления и вызывает `StartMarquee` для тех, которые реализуют `IMarqueeWidget`. Метод `StopMarquee` имеет аналогичную реализацию.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Реализуйте методы доступа к свойствам. Элемент управления `MarqueeBorder` имеет несколько свойств для управления его внешним видом.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Реализуйте обработчики для событий <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> компонента <xref:System.ComponentModel.BackgroundWorker>.

    Обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork> приостанавливается на число миллисекунд, указанное в `UpdatePeriod` затем вызывает событие <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, пока код не прекратит анимацию, вызвав <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    Обработчик событий <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> увеличивает расположение «базового» освещения, из которого определяется Светлый/темный статус других источников света, и вызывает метод <xref:System.Windows.Forms.Control.Refresh%2A>, чтобы элемент управления переводился в перерисовку.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Реализуйте вспомогательные методы, `IsLit` и `DrawLight`.

    Метод `IsLit` определяет цвет освещения в заданной позиции. Световые индикаторы выводятся в цвете, заданном свойством `LightColor`, а те, которые являются "темными", рисуются цветом, заданным свойством `DarkColor`.

    Метод `DrawLight` рисует источник освещения с помощью соответствующего цвета, формы и расположения.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Переопределите методы <xref:System.Windows.Forms.Control.OnLayout%2A> и <xref:System.Windows.Forms.Control.OnPaint%2A>.

    Метод <xref:System.Windows.Forms.Control.OnPaint%2A> рисует индикаторы вдоль краев элемента управления `MarqueeBorder`.

    Поскольку метод <xref:System.Windows.Forms.Control.OnPaint%2A> зависит от измерений элемента управления `MarqueeBorder`, его необходимо вызывать при каждом изменении макета. Чтобы добиться этого, переопределите <xref:System.Windows.Forms.Control.OnLayout%2A> и вызовите <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>Создание пользовательского конструктора для тени и фильтрации свойств

Класс `MarqueeControlRootDesigner` предоставляет реализацию для корневого конструктора. Помимо этого конструктора, который работает с `MarqueeControl`, необходим пользовательский конструктор, специально связанный с элементом управления `MarqueeBorder`. Этот конструктор предоставляет настраиваемое поведение, которое подходит для контекста пользовательского корневого конструктора.

В частности, `MarqueeBorderDesigner` будет "Shadow" и отфильтровать определенные свойства элемента управления `MarqueeBorder`, изменив их взаимодействие с средой разработки.

Перехват вызовов метода доступа к свойству компонента называется "тенью". Он позволяет конструктору отслеживанить значение, заданное пользователем, и при необходимости передать это значение в разрабатываемый компонент.

В этом примере свойства <xref:System.Windows.Forms.Control.Visible%2A> и <xref:System.Windows.Forms.Control.Enabled%2A> будут скрыты с помощью `MarqueeBorderDesigner`, что не позволит пользователю сделать элемент управления `MarqueeBorder` невидимым или отключенным во время разработки.

Конструкторы также могут добавлять и удалять свойства. В этом примере свойство <xref:System.Windows.Forms.Control.Padding%2A> будет удалено во время разработки, поскольку элемент управления `MarqueeBorder` программно устанавливает заполнение на основе размера огней, заданных свойством `LightSize`.

Базовым классом для `MarqueeBorderDesigner` является <xref:System.ComponentModel.Design.ComponentDesigner>, который содержит методы, которые могут изменять атрибуты, свойства и события, предоставляемые элементом управления во время разработки:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

При изменении открытого интерфейса компонента с помощью этих методов следует соблюдать следующие правила.

- Добавлять или удалять элементы только в `PreFilter` методах

- Изменение существующих элементов только в `PostFilter` методах

- Всегда вызывайте базовую реализацию сначала в методах `PreFilter`

- Всегда вызывайте базовую реализацию последними в методах `PostFilter`

Соблюдение этих правил гарантирует, что все конструкторы в среде времени разработки будут иметь единообразное представление всех разрабатываемых компонентов.

Класс <xref:System.ComponentModel.Design.ComponentDesigner> предоставляет словарь для управления значениями затененных свойств, что освобождает вас от необходимости создавать конкретные переменные экземпляра.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Создание пользовательского конструктора для теневого копирования и свойств фильтра

1. Щелкните правой кнопкой мыши папку **конструктора** и добавьте новый класс. Присвойте исходному файлу базовое имя **маркуибордердесигнер**.

2. Откройте исходный файл Маркуибордердесигнер в **редакторе кода**. В верхней части файла импортируйте следующие пространства имен:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Измените объявление `MarqueeBorderDesigner` для наследования от <xref:System.Windows.Forms.Design.ParentControlDesigner>.

    Поскольку элемент управления `MarqueeBorder` может содержать дочерние элементы управления, `MarqueeBorderDesigner` наследует от <xref:System.Windows.Forms.Design.ParentControlDesigner>, который обрабатывает взаимодействие типа «родители-потомки».

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Переопределите базовую реализацию <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Реализуйте свойства <xref:System.Windows.Forms.Control.Enabled%2A> и <xref:System.Windows.Forms.Control.Visible%2A>. Эти реализации затениют свойства элемента управления.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>Обработку изменений компонентов

Класс `MarqueeControlRootDesigner` предоставляет пользовательский интерфейс времени разработки для экземпляров `MarqueeControl`. Большая часть функций времени разработки наследуется от класса <xref:System.Windows.Forms.Design.DocumentDesigner>. В коде будут реализованы две определенные настройки: обработка изменений компонентов и Добавление команд конструктора.

Когда пользователи разрабатывает свои `MarqueeControl` экземпляры, корневой конструктор будет отслеживанию изменений в `MarqueeControl` и его дочерних элементах управления. Среда времени разработки предлагает удобную службу, <xref:System.ComponentModel.Design.IComponentChangeService>для отслеживания изменений состояния компонента.

Чтобы получить ссылку на эту службу, запросите среду с помощью метода <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>. Если запрос выполнен успешно, конструктор может присоединить обработчик для события <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> и выполнить все задачи, необходимые для поддержания единообразного состояния во время разработки.

В случае класса `MarqueeControlRootDesigner` будет вызван метод <xref:System.Windows.Forms.Control.Refresh%2A> для каждого объекта `IMarqueeWidget`, содержащегося в `MarqueeControl`. Это приведет к тому, что объект `IMarqueeWidget` будет правильно перерисовываться при изменении свойств, таких как <xref:System.Windows.Forms.Control.Size%2A> родительского объекта.

### <a name="to-handle-component-changes"></a>Для управления изменениями компонентов

1. Откройте исходный файл `MarqueeControlRootDesigner` в **редакторе кода** и переопределите метод <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>. Вызовите базовую реализацию <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> и запросите <xref:System.ComponentModel.Design.IComponentChangeService>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Реализуйте обработчик событий <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>. Проверьте тип компонента отправки и, если это `IMarqueeWidget`, вызовите его метод <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>Добавление команд конструктора в пользовательский конструктор

Команда конструктора — это команда меню, связанная с обработчиком событий. Команды конструктора добавляются в контекстное меню компонента во время разработки. Для получения дополнительной информации см. <xref:System.ComponentModel.Design.DesignerVerb>.

В конструкторы вы добавите две команды конструктора: **запустить тест** и **закончить тест**. Эти команды позволяют просматривать поведение во время выполнения `MarqueeControl` во время разработки. Эти команды будут добавлены в `MarqueeControlRootDesigner`.

При вызове **запуска теста** обработчик событий verb вызывает метод `StartMarquee` для `MarqueeControl`. При вызове метода " **приостанавливается** " обработчик событий команды вызывает метод `StopMarquee` для `MarqueeControl`. Реализация методов `StartMarquee` и `StopMarquee` вызывает эти методы для вложенных элементов управления, которые реализуют `IMarqueeWidget`, поэтому любые содержащиеся `IMarqueeWidget` элементы управления также будут участвовать в тестировании.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Добавление команд конструктора в пользовательские конструкторы

1. В классе `MarqueeControlRootDesigner` добавьте обработчики событий с именами `OnVerbRunTest` и `OnVerbStopTest`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Соедините эти обработчики событий с соответствующими командами конструктора. `MarqueeControlRootDesigner` наследует <xref:System.ComponentModel.Design.DesignerVerbCollection> от своего базового класса. Вы создадите два новых <xref:System.ComponentModel.Design.DesignerVerb> объектов и добавите их в эту коллекцию в методе <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>Создание настраиваемого UITypeEditor

При создании пользовательской среды разработки для пользователей часто желательно создать пользовательское взаимодействие с окно свойств. Это можно сделать, создав <xref:System.Drawing.Design.UITypeEditor>.

Элемент управления `MarqueeBorder` предоставляет несколько свойств в окно свойств. Два из этих свойств, `MarqueeSpinDirection` и `MarqueeLightShape`, представлены перечислениями. Чтобы продемонстрировать использование редактора типов пользовательского интерфейса, свойство `MarqueeLightShape` будет иметь связанный <xref:System.Drawing.Design.UITypeEditor> класс.

### <a name="to-create-a-custom-ui-type-editor"></a>Создание пользовательского редактора типов пользовательского интерфейса

1. Откройте исходный файл `MarqueeBorder` в **редакторе кода**.

2. В определении класса `MarqueeBorder` объявите класс с именем `LightShapeEditor`, производный от <xref:System.Drawing.Design.UITypeEditor>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Объявите переменную экземпляра <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> с именем `editorService`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Переопределите метод <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> . Эта реализация возвращает <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, которая указывает среде разработки, как отобразить `LightShapeEditor`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Переопределите метод <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> . Эта реализация запрашивает в среде разработки объект <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>. В случае успеха создается `LightShapeSelectionControl`. Для запуска `LightShapeEditor`вызывается метод <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>. Возвращаемое значение этого вызова возвращается в среду разработки.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>Создание элемента управления View для пользовательского UITypeEditor

Свойство `MarqueeLightShape` поддерживает два типа простых фигур: `Square` и `Circle`. Вы создадите пользовательский элемент управления, используемый исключительно в целях графического отображения этих значений в окно свойств. Этот пользовательский элемент управления будет использоваться <xref:System.Drawing.Design.UITypeEditor> для взаимодействия с окно свойств.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Создание элемента управления представления для пользовательского редактора типов пользовательского интерфейса

1. Добавьте новый элемент <xref:System.Windows.Forms.UserControl> в проект `MarqueeControlLibrary`. Присвойте новому исходному файлу базовое имя **лигхтшапеселектионконтрол**.

2. Перетащите два элемента управления <xref:System.Windows.Forms.Panel> из **панели элементов** на `LightShapeSelectionControl`. Назовите их `squarePanel` и `circlePanel`. Расположите их параллельно. Задайте для свойства <xref:System.Windows.Forms.Control.Size%2A> обоих элементов управления <xref:System.Windows.Forms.Panel> значение **(60, 60)** . Задайте для свойства <xref:System.Windows.Forms.Control.Location%2A> элемента управления `squarePanel` значение **(8, 10)** . Задайте для свойства <xref:System.Windows.Forms.Control.Location%2A> элемента управления `circlePanel` значение **(80, 10)** . Наконец, задайте для свойства <xref:System.Windows.Forms.Control.Size%2A> `LightShapeSelectionControl` значение **(150, 80)** .

3. Откройте исходный файл `LightShapeSelectionControl` в **редакторе кода**. В верхней части файла импортируйте <xref:System.Windows.Forms.Design?displayProperty=nameWithType> пространство имен:

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. Реализуйте <xref:System.Windows.Forms.Control.Click> обработчики событий для элементов управления `squarePanel` и `circlePanel`. Эти методы вызывают <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> для завершения пользовательского сеанса редактирования <xref:System.Drawing.Design.UITypeEditor>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. Объявите переменную экземпляра <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> с именем `editorService`.

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. Объявите переменную экземпляра `MarqueeLightShape` с именем `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. В конструкторе `LightShapeSelectionControl` присоедините <xref:System.Windows.Forms.Control.Click> обработчики событий к событиям <xref:System.Windows.Forms.Control.Click> `squarePanel` и `circlePanel` элементов управления. Кроме того, определите перегрузку конструктора, которая назначает значение `MarqueeLightShape` из среды разработки полю `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. В методе <xref:System.ComponentModel.Component.Dispose%2A> отсоедините <xref:System.Windows.Forms.Control.Click> обработчики событий.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. В **обозревателе решений** нажмите кнопку **Показать все файлы**. Откройте файл LightShapeSelectionControl.Designer.cs или Лигхтшапеселектионконтрол. Designer. vb и удалите определение по умолчанию для метода <xref:System.ComponentModel.Component.Dispose%2A>.

10. Реализуйте свойство `LightShape`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. Переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A> . В этой реализации будет нарисован закрашенный квадрат и круг. Он также выделяет выбранное значение, рисуя границу вокруг одной или другой фигуры.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>Тестирование пользовательского элемента управления в конструкторе

На этом этапе можно создать проект `MarqueeControlLibrary`. Протестируйте реализацию, создав элемент управления, который наследует от класса `MarqueeControl` и использую его в форме.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Создание пользовательской реализации Маркуиконтрол

1. Откройте `DemoMarqueeControl` в конструкторе Windows Forms. Это создает экземпляр типа `DemoMarqueeControl` и отображает его в экземпляре типа `MarqueeControlRootDesigner`.

2. На **панели элементов**откройте вкладку **компоненты маркуиконтроллибрари** . Вы увидите элементы управления `MarqueeBorder` и `MarqueeText`, доступные для выбора.

3. Перетащите экземпляр элемента управления `MarqueeBorder` на область конструктора `DemoMarqueeControl`. Закрепите этот `MarqueeBorder` элемент управления в родительском элементе управления.

4. Перетащите экземпляр элемента управления `MarqueeText` на область конструктора `DemoMarqueeControl`.

5. Постройте решение.

6. Щелкните правой кнопкой мыши `DemoMarqueeControl` и в контекстном меню выберите пункт **запустить тест** , чтобы запустить анимацию. Нажмите кнопку " **Закрыть тест** ", чтобы прерывать анимацию.

7. Откройте форму **Form1** в конструкторе.

8. Поместите два элемента управления <xref:System.Windows.Forms.Button> в форму. Назовите их `startButton` и `stopButton`и измените значения свойств <xref:System.Windows.Forms.Control.Text%2A> на **Start** и **останавливаться**соответственно.

9. Реализуйте <xref:System.Windows.Forms.Control.Click> обработчики событий для <xref:System.Windows.Forms.Button>ных элементов управления.

10. На **панели элементов**откройте вкладку **компоненты маркуиконтролтест** . Вы увидите `DemoMarqueeControl` доступен для выбора.

11. Перетащите экземпляр `DemoMarqueeControl` на поверхность конструктора **Form1** .

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

13. Задайте проект `MarqueeControlTest` в качестве запускаемого проекта и запустите его. Вы увидите форму, отображающую `DemoMarqueeControl`. Нажмите кнопку **запустить** , чтобы запустить анимацию. Вы увидите, что текст мигает и индикаторы перемещаются вокруг границы.

## <a name="next-steps"></a>Следующие шаги

В `MarqueeControlLibrary` демонстрируется простая реализация пользовательских элементов управления и связанных с ними конструкторов. Сделать этот пример более сложным можно несколькими способами:

- Измените значения свойств для `DemoMarqueeControl` в конструкторе. Добавьте дополнительные элементы управления `MarqueBorder` и закрепите их в своих родительских экземплярах, чтобы создать вложенный результат. Экспериментируйте с различными параметрами для `UpdatePeriod` и свойств, связанных с источниками.

- Создайте собственные реализации `IMarqueeWidget`. Например, можно создать мигающий знак «Neon» или анимированный знак с несколькими изображениями.

- Дальнейшая настройка взаимодействия во время разработки. Можно попытаться затенить больше свойств, чем <xref:System.Windows.Forms.Control.Enabled%2A> и <xref:System.Windows.Forms.Control.Visible%2A>, и добавить новые свойства. Добавьте новые команды конструктора для упрощения распространенных задач, таких как закрепление дочерних элементов управления.

- Лицензирование `MarqueeControl`.

- Управление сериализацией элементов управления и созданием кода для них. Дополнительные сведения см. в разделе [Динамическое создание и компиляция исходного кода](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
