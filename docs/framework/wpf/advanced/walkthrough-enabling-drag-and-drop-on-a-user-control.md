---
title: Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 172e49c2c255db4d24d2180f919b1305326b5e82
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991798"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления

В этом пошаговом руководстве демонстрируется создание настраиваемого пользовательского элемента управления, который может участвовать в переносе данных путем перетаскивания в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].

В этом пошаговом руководстве вы создадите пользовательский элемент <xref:System.Windows.Controls.UserControl> WPF, представляющий круговую фигуру. Вы реализуете в этом элементе управления функциональность, позволяющую переносить данные посредством перетаскивания. Например, при перетаскивании из одного элемента управления Circle в другой данные цвета заливки копируются из исходного круга в целевой. При перетаскивании элемента управления Circle в объект <xref:System.Windows.Controls.TextBox>строковое представление цвета заливки копируется <xref:System.Windows.Controls.TextBox>в. Кроме того, будет создано небольшое приложение, содержащее два элемента управления Panel, <xref:System.Windows.Controls.TextBox> и для тестирования функции перетаскивания. Вы напишете код, позволяющий панелям обрабатывать перемещенные перетаскиванием данные Circle, в результате чего элементы управления Circle можно будет перемещать или копировать из дочерней коллекции на одной панели в другую.

В данном пошаговом руководстве рассмотрены следующие задачи:

- Создание настраиваемого пользовательского элемента управления.

- Включение пользовательского элемента управления в качестве источника перетаскивания.

- Включение пользовательского элемента управления в качестве целевого объекта перетаскивания.

- Включение панели для получения данных, перемещенных перетаскиванием из пользовательского элемента управления.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.

## <a name="create-the-application-project"></a>Создание проекта приложения
 В этом разделе мы создадим инфраструктуру приложений, которая включает главную страницу с двумя панелями и <xref:System.Windows.Controls.TextBox>.

1. Создайте проект приложения WPF на Visual Basic или Visual C# с именем `DragDropExample`. Дополнительные сведения см. в разделе [Пошаговое руководство: Мое первое приложение](../getting-started/walkthrough-my-first-wpf-desktop-application.md)WPF для настольных систем.

2. Откройте файл MainWindow.xaml.

3. Добавьте следующую разметку между открывающим и закрывающим <xref:System.Windows.Controls.Grid> тегами.

     Эта разметка создает пользовательский интерфейс для тестового приложения.

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a>Добавление нового пользовательского элемента управления в проект
 В этом разделе вы добавите в проект новый пользовательский элемент управления.

1. В меню "Проект" выберите пункт **Добавить пользовательский элемент управления**.

2. В диалоговом окне **Добавление нового элемента** измените имя на `Circle.xaml`и нажмите кнопку **Добавить**.

     Circle.xaml и его код программной части добавляются в проект.

3. Откройте файл Circle.xaml.

     Этот файл будет содержать элементы пользовательского интерфейса пользовательского элемента управления.

4. Добавьте следующую разметку в корень <xref:System.Windows.Controls.Grid> , чтобы создать простой пользовательский элемент управления с синим кругом в качестве пользовательского интерфейса.

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. Откройте файл Circle.xaml.cs или Circle.xaml.vb.

6. В C#добавьте следующий код после конструктора без параметров, чтобы создать конструктор копии. В Visual Basic добавьте следующий код, чтобы создать конструктор без параметров и конструктор копии.

     Чтобы разрешить копирование пользовательского элемента управления, нужно добавить метод конструктора копии в файле кода программной части. В упрощенном пользовательском элементе управления Circle копируются только свойства Fill и размер пользовательского элемента управления.

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a>Добавление пользовательского элемента управления в главное окно

1. Откройте файл MainWindow.xaml.

2. Добавьте следующий код XAML в открывающий <xref:System.Windows.Window> тег, чтобы создать ссылку на пространство имен XML для текущего приложения.

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. В первом <xref:System.Windows.Controls.StackPanel>случае добавьте следующий код XAML, чтобы создать два экземпляра пользовательского элемента управления Circle на первой панели.

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     Полный код XAML для панели выглядит следующим образом.

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a>Реализация событий источника перетаскивания в пользовательском элементе управления
 В этом разделе будет переопределен <xref:System.Windows.UIElement.OnMouseMove%2A> метод и инициирована операция перетаскивания.

 Если перетаскивание начато (нажата кнопка мыши и мышь перемещается), будут упакованы данные, передаваемые в <xref:System.Windows.DataObject>. В данном случае элемент управления Circle упаковывает три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.

### <a name="to-initiate-a-drag-and-drop-operation"></a>Запуск операции перетаскивания

1. Откройте файл Circle.xaml.cs или Circle.xaml.vb.

2. Добавьте следующее <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.MouseMove> для события.

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     Это <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение выполняет следующие задачи:

    - Проверяет, нажата ли левая кнопка мыши при перемещении мыши.

    - Упаковывает данные круга в <xref:System.Windows.DataObject>. В данном случае элемент управления Circle упакует три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.

    - Вызывает статический <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> метод для инициации операции перетаскивания. В <xref:System.Windows.DragDrop.DoDragDrop%2A> метод передается следующие три параметра:

        - `dragSource` — ссылка на этот элемент управления.

        - `data`— Объект <xref:System.Windows.DataObject> , созданный в предыдущем коде.

        - `allowedEffects`— Разрешенные операции перетаскивания, которые являются <xref:System.Windows.DragDropEffects.Copy> или. <xref:System.Windows.DragDropEffects.Move>

3. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

4. Щелкните один из элементов управления Circle и перетащите его над панелями, другим кругом и <xref:System.Windows.Controls.TextBox>. При перетаскивании над <xref:System.Windows.Controls.TextBox>курсор изменяется, чтобы показать перемещение.

5. При перетаскивании окружности над <xref:System.Windows.Controls.TextBox>нажмите клавишу **CTRL** . Обратите внимание на то, как изменится курсор, обозначая копирование.

6. Перетащите окружность на <xref:System.Windows.Controls.TextBox>. Строковое представление цвета заливки круга добавляется к <xref:System.Windows.Controls.TextBox>.

     ![Строковое представление цвета заливки элемента управления Circle](./media/dragdrop-colorstring.png "DragDrop_ColorString")

По умолчанию курсор изменяется во время операции перетаскивания, чтобы указать, какой результат даст перетаскивание данных в ту или иную точку. Вы можете настроить отзыв, предоставленный пользователю, обрабатывая <xref:System.Windows.UIElement.GiveFeedback> событие и установив другой курсор.

## <a name="give-feedback-to-the-user"></a>Отправьте отзыв пользователю

1. Откройте файл Circle.xaml.cs или Circle.xaml.vb.

2. Добавьте следующее <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.GiveFeedback> для события.

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     Это <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение выполняет следующие задачи:

    - Проверяет значения, заданные в обработчике <xref:System.Windows.UIElement.DragOver> событий целевого объекта перетаскивания. <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>

    - Задает пользовательский курсор на основе <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> значения. Курсор предназначен для предоставления визуальной обратной связи пользователю о том, какой результат будет иметь перетаскивание данных.

3. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

4. Перетащите один из элементов управления Circle над панелями, другой окружностью и <xref:System.Windows.Controls.TextBox>. Обратите внимание, что курсоры теперь являются пользовательскими курсорами, указанными в <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределении.

     ![Перетаскивание с использованием пользовательских курсоров](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")

5. Выберите текст `green` <xref:System.Windows.Controls.TextBox>из.

6. Перетащите текст `green` в элемент управления Circle. Обратите внимание, что отображаются курсоры по умолчанию: они указывают на результаты операции перетаскивания. Курсор обратной связи всегда задается источником перетаскивания.

## <a name="implement-drop-target-events-in-the-user-control"></a>Реализуйте события назначения перетаскивания в пользовательском элементе управления
 Изучая этот раздел, вы укажете, что пользовательский элемент управления является целевым объектом перетаскивания, переопределите методы, позволяющие пользовательскому элементу управления функционировать в качестве целевого объекта перетаскивания, и обработаете перемещенные в него данные.

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>Чтобы включить пользовательский элемент управления в качестве целевого объекта перетаскивания, выполните следующие действия.

1. Откройте файл Circle.xaml.

2. В открывающем <xref:System.Windows.Controls.UserControl> теге <xref:System.Windows.UIElement.AllowDrop%2A> добавьте `true`свойство и присвойте ему значение.

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

Метод вызывается, <xref:System.Windows.UIElement.AllowDrop%2A> когда свойство имеет значение `true` , а данные из источника перетаскивания удаляются в пользовательском элементе управления Circle. <xref:System.Windows.UIElement.OnDrop%2A> В этом методе вы обработаете перемещенные данные и примените их к элементу управления Circle.

### <a name="to-process-the-dropped-data"></a>Обработка вставляемых данных

1. Откройте файл Circle.xaml.cs или Circle.xaml.vb.

2. Добавьте следующее <xref:System.Windows.UIElement.OnDrop%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.Drop> для события.

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     Это <xref:System.Windows.UIElement.OnDrop%2A> переопределение выполняет следующие задачи:

    - <xref:System.Windows.DataObject.GetDataPresent%2A> Использует метод, чтобы проверить, содержит ли перетаскиваемые данные строковый объект.

    - <xref:System.Windows.DataObject.GetData%2A> Использует метод для извлечения строковых данных, если они есть.

    - Использует, <xref:System.Windows.Media.BrushConverter> чтобы попытаться преобразовать строку <xref:System.Windows.Media.Brush>в.

    - Если преобразование выполнено успешно, применяет кисть к <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> элементу, который предоставляет пользовательский интерфейс элемента управления Circle.

    - <xref:System.Windows.UIElement.Drop> Помечает событие как обработанное. Событие сброса необходимо пометить как обработанное, чтобы другие элементы, которые получают это событие, знали, что событие было обработано пользовательским элементом управления Circle.

3. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

4. Выберите текст `green` в поле <xref:System.Windows.Controls.TextBox>.

5. Перетащите текст в элемент управления Circle. Элемент управления Circle поменяет цвет с синего на зеленый.

     ![Преобразование строки в кисть](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")

6. Введите текст `green` в поле <xref:System.Windows.Controls.TextBox>.

7. Выберите текст `gre` в поле <xref:System.Windows.Controls.TextBox>.

8. Перетащите его в элемент управления Circle. Обратите внимание, что курсор изменяется, чтобы указать, что перенос разрешен, но цвет элемента управления Circle не меняется, потому что `gre` — недопустимый цвет.

9. Выполните перетаскивание с зеленого элемента управления Circle на синий. Элемент управления Circle поменяет цвет с синего на зеленый. Обратите внимание, что отображаемый курсор зависит от <xref:System.Windows.Controls.TextBox> того, является ли объект или окружность источником перетаскивания.

Установка свойства в `true` и обработка удаленных данных — это все, что необходимо для того, чтобы элемент можно было использовать в качестве цели перетаскивания. <xref:System.Windows.UIElement.AllowDrop%2A> Однако, чтобы обеспечить более эффективное взаимодействие с пользователем, необходимо также выполнить обработку <xref:System.Windows.UIElement.DragEnter>событий <xref:System.Windows.UIElement.DragLeave>, и <xref:System.Windows.UIElement.DragOver> . В этих событиях можно выполнять проверки и предоставлять дополнительную обратную связь пользователю до сброса данных.

При перетаскивании данных над пользовательским элементом управления Circle элемент управления должен уведомить источник перетаскивания, может ли он обработать переносимые данные. Если элемент управления не знает, как обрабатывать данные, он должен отклонить перетаскивание. Для этого необходимо будет выполнить обработку <xref:System.Windows.UIElement.DragOver> события и <xref:System.Windows.DragEventArgs.Effects%2A> задать свойство.

### <a name="to-verify-that-the-data-drop-is-allowed"></a>Проверка допустимости сброса данных

1. Откройте файл Circle.xaml.cs или Circle.xaml.vb.

2. Добавьте следующее <xref:System.Windows.UIElement.OnDragOver%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.DragOver> для события.

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     Это <xref:System.Windows.UIElement.OnDragOver%2A> переопределение выполняет следующие задачи:

    - Задает для свойства <xref:System.Windows.DragEventArgs.Effects%2A> значение <xref:System.Windows.DragDropEffects.None>.

    - Выполняет те же проверки, которые выполняются в <xref:System.Windows.UIElement.OnDrop%2A> методе, чтобы определить, может ли пользовательский элемент управления Circle обрабатывать перетаскиваемые данные.

    - Если пользовательский элемент управления может обработать данные, присваивает <xref:System.Windows.DragEventArgs.Effects%2A> <xref:System.Windows.DragDropEffects.Copy> свойству значение или <xref:System.Windows.DragDropEffects.Move>.

3. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

4. Выберите текст `gre` в поле <xref:System.Windows.Controls.TextBox>.

5. Перетащите текст в элемент управления Circle. Обратите внимание, что курсор изменяется, чтобы указать, что перетаскивание не разрешено, потому что `gre` не является допустимым цветом.

 Использование предварительного просмотра при перетаскивании повышает удобство работы пользователей. Для пользовательского элемента управления Circle будут переопределены <xref:System.Windows.UIElement.OnDragEnter%2A> методы и. <xref:System.Windows.UIElement.OnDragLeave%2A> При перетаскивании данных над элементом управления текущий фон <xref:System.Windows.Shapes.Shape.Fill%2A> сохраняется в переменной-заполнителе. Затем строка преобразуется в кисть и применяется к <xref:System.Windows.Shapes.Ellipse> , которая предоставляет пользовательский интерфейс Circle. Если данные перетаскиваются из круга без удаления, исходное <xref:System.Windows.Shapes.Shape.Fill%2A> значение повторно применяется к окружности.

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>Предварительный просмотр результатов операции перетаскивания

1. Откройте файл Circle.xaml.cs или Circle.xaml.vb.

2. В классе Circle объявите закрытую <xref:System.Windows.Media.Brush> переменную с именем `_previousFill` и инициализируйте `null`ее в.

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. Добавьте следующее <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.DragEnter> для события.

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     Это <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение выполняет следующие задачи:

    - <xref:System.Windows.Shapes.Shape.Fill%2A> Сохраняет свойство<xref:System.Windows.Shapes.Ellipse> объекта в`_previousFill` переменной.

    - Выполняет те же проверки, которые выполняются в <xref:System.Windows.UIElement.OnDrop%2A> методе, чтобы определить, можно ли преобразовать данные <xref:System.Windows.Media.Brush>в.

    - Если данные преобразуются в допустимый <xref:System.Windows.Media.Brush>объект, применяет <xref:System.Windows.Shapes.Shape.Fill%2A> их к <xref:System.Windows.Shapes.Ellipse>параметру.

4. Добавьте следующее <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.DragLeave> для события.

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     Это <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение выполняет следующие задачи:

    - Применяет `_previousFill` <xref:System.Windows.Shapes.Shape.Fill%2A> сохраненную в<xref:System.Windows.Shapes.Ellipse> переменной переменную к, которая предоставляет пользовательский интерфейс пользовательского элемента управления Circle. <xref:System.Windows.Media.Brush>

5. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

6. Выберите текст `green` в поле <xref:System.Windows.Controls.TextBox>.

7. Перетащите текст над элементом управления Circle, не сбрасывая его. Элемент управления Circle поменяет цвет с синего на зеленый.

     ![Предварительный просмотр результатов операции перетаскивания](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")

8. Перетащите текст от элемента управления Circle. Элемент управления Circle изменится с зеленого на синий.

## <a name="enable-a-panel-to-receive-dropped-data"></a>Включение панели для получения потерянных данных

В этом разделе вы включите панели, в которых размещаются пользовательские элементы управления Circle, чтобы они выступали в качестве целей перетаскивания для перетаскиваемых данных круга. Будет реализован код, позволяющий перемещать круг с одной панели на другую или создавать копию элемента управления Circle, удерживая нажатой клавишу **CTRL** при перетаскивании и перетаскивании окружности.

1. Откройте файл MainWindow.xaml.

2. Как показано в следующем коде XAML, в каждом <xref:System.Windows.Controls.StackPanel> элементе управления добавьте обработчики <xref:System.Windows.UIElement.DragOver> для событий и <xref:System.Windows.UIElement.Drop> . Назовите обработчик событий, <xref:System.Windows.UIElement.Drop> и`panel_Drop`присвойтеемуимя. `panel_DragOver` <xref:System.Windows.UIElement.DragOver>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. Откройте файл MainWindows.xaml.cs или MainWindow.xaml.vb.

4. Добавьте следующий код для <xref:System.Windows.UIElement.DragOver> обработчика событий.

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     Этот <xref:System.Windows.UIElement.DragOver> обработчик событий выполняет следующие задачи:

    - Проверяет, что перетаскиваемые данные содержат данные "Object", которые были упакованы в <xref:System.Windows.DataObject> с помощью пользовательского элемента управления Circle и передаются в <xref:System.Windows.DragDrop.DoDragDrop%2A>вызов.

    - Если имеются данные объекта, проверяет, нажата ли клавиша **CTRL** .

    - Если нажата клавиша **CTRL** , присваивает <xref:System.Windows.DragEventArgs.Effects%2A> свойству <xref:System.Windows.DragDropEffects.Copy>значение. В противном случае <xref:System.Windows.DragEventArgs.Effects%2A> присвойте <xref:System.Windows.DragDropEffects.Move>свойству значение.

5. Добавьте следующий код для <xref:System.Windows.UIElement.Drop> обработчика событий.

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     Этот <xref:System.Windows.UIElement.Drop> обработчик событий выполняет следующие задачи:

    - Проверяет, <xref:System.Windows.UIElement.Drop> было ли событие уже обработано. Например, если окружность отбрасывается на другой круг, который обрабатывает <xref:System.Windows.UIElement.Drop> событие, то панель, содержащая окружность, также не должна обрабатываться.

    - Если событие не обрабатывается, проверяет, нажата ли клавиша **CTRL.** <xref:System.Windows.UIElement.Drop>

    - Если нажата клавиша **CTRL** , когда <xref:System.Windows.UIElement.Drop> происходит, создает копию элемента управления Circle и <xref:System.Windows.Controls.Panel.Children%2A> добавляет ее в коллекцию <xref:System.Windows.Controls.StackPanel>.

    - Если клавиша **CTRL** не нажата, перемещает окружность из <xref:System.Windows.Controls.Panel.Children%2A> коллекции <xref:System.Windows.Controls.Panel.Children%2A> родительской панели в коллекцию панели, в которой она была удалена.

    - Задает свойство для <xref:System.Windows.DragDrop.DoDragDrop%2A> уведомления метода о том, была ли выполнена операция перемещения или копирования. <xref:System.Windows.DragEventArgs.Effects%2A>

6. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

7. Выберите текст `green` <xref:System.Windows.Controls.TextBox>из.

8. Перетащите текст над элементом управления Circle и опустите его на элемент.

9. Перетащите элемент управления Circle из левой панели в правую панель и опустите его. Окружность удаляется из <xref:System.Windows.Controls.Panel.Children%2A> коллекции левой панели и добавляется в коллекцию Children правой панели.

10. Перетащите элемент управления Circle с панели на другую панель и поместите его, удерживая нажатой клавишу **CTRL** . Окружность копируется, а копия добавляется в <xref:System.Windows.Controls.Panel.Children%2A> коллекцию принимающей панели.

     ![Перетаскивание элемента управления Circle с нажатой клавишей CTRL](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")

## <a name="see-also"></a>См. также

- [Общие сведения о перетаскивании](drag-and-drop-overview.md)
