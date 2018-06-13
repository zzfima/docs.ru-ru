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
ms.openlocfilehash: e4dba856b973f1210f2d088de3ed8ae5df2c6988
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549754"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления
В этом пошаговом руководстве демонстрируется создание настраиваемого пользовательского элемента управления, который может участвовать в переносе данных путем перетаскивания в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 В этом пошаговом руководстве вы создадите пользовательский элемент управления WPF <xref:System.Windows.Controls.UserControl> , представляющий круг. Вы реализуете в этом элементе управления функциональность, позволяющую переносить данные посредством перетаскивания. Например, при перетаскивании из одного элемента управления Circle в другой данные цвета заливки копируются из исходного круга в целевой. При перетаскивании элемента управления Circle для <xref:System.Windows.Controls.TextBox>, копируется строковое представление цвета заливки <xref:System.Windows.Controls.TextBox>. Также создается небольшое приложение, которое содержит два элемента панели управления и <xref:System.Windows.Controls.TextBox> тестирование функциональности перетаскивания и вставки. Вы напишете код, позволяющий панелям обрабатывать перемещенные перетаскиванием данные Circle, в результате чего элементы управления Circle можно будет перемещать или копировать из дочерней коллекции на одной панели в другую.  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   Создание настраиваемого пользовательского элемента управления.  
  
-   Включение пользовательского элемента управления в качестве источника перетаскивания.  
  
-   Включение пользовательского элемента управления в качестве целевого объекта перетаскивания.  
  
-   Включение панели для получения данных, перемещенных перетаскиванием из пользовательского элемента управления.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   Visual Studio 2010  
  
## <a name="creating-the-application-project"></a>Создание проекта приложения  
 В этом разделе вы создадите инфраструктуру приложения, которая включает главную страницу с двумя панелями и <xref:System.Windows.Controls.TextBox>.  
  
### <a name="to-create-the-project"></a>Создание проекта  
  
1.  Создайте проект приложения WPF на Visual Basic или Visual C# с именем `DragDropExample`. Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Откройте файл MainWindow.xaml.  
  
3.  Добавьте следующую разметку между открывающим и закрывающим <xref:System.Windows.Controls.Grid> тегов.  
  
     Эта разметка создает пользовательский интерфейс для тестового приложения.  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a>Добавление пользовательского элемента управления в проект  
 В этом разделе вы добавите в проект новый пользовательский элемент управления.  
  
### <a name="to-add-a-new-user-control"></a>Добавление пользовательского элемента управления  
  
1.  В меню "Проект" выберите пункт **Добавить пользовательский элемент управления**.  
  
2.  В диалоговом окне "Добавление нового элемента" измените имя на `Circle.xaml` и нажмите кнопку **Добавить**.  
  
     Circle.xaml и его код программной части добавляются в проект.  
  
3.  Откройте файл Circle.xaml.  
  
     Этот файл будет содержать элементы пользовательского интерфейса пользовательского элемента управления.  
  
4.  Добавьте следующую разметку в корневой каталог <xref:System.Windows.Controls.Grid> для создания простой пользовательский элемент управления, который имеет голубой круг в качестве своего пользовательского интерфейса.  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
6.  В C# добавьте следующий код после конструктора по умолчанию, чтобы создать конструктор копии. В Visual Basic добавьте следующий код, чтобы создать конструктор по умолчанию и конструктор копии.  
  
     Чтобы разрешить копирование пользовательского элемента управления, нужно добавить метод конструктора копии в файле кода программной части. В упрощенном пользовательском элементе управления Circle копируются только свойства Fill и размер пользовательского элемента управления.  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a>Добавление пользовательского элемента управления в главное окно  
  
1.  Откройте файл MainWindow.xaml.  
  
2.  Добавьте следующий код XAML в открывающий <xref:System.Windows.Window> тег для создания ссылки на пространство имен XML в текущем приложении.  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  В первом <xref:System.Windows.Controls.StackPanel>, добавьте следующий код XAML для создания двух экземпляров пользовательский элемент управления Circle первой панели.  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     Полный код XAML для панели выглядит следующим образом.  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a>Реализация событий источника перетаскивания в пользовательском элементе управления  
 В этом разделе будут переопределены <xref:System.Windows.UIElement.OnMouseMove%2A> метод и начать операцию перетаскивания и вставки.  
  
 Если запущен перетаскивания (кнопка мыши нажата и указатель мыши перемещается) поставляют данные будут передаваться в <xref:System.Windows.DataObject>. В данном случае элемент управления Circle упаковывает три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a>Запуск операции перетаскивания  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  Добавьте следующие <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.MouseMove> события.  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     Это <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение выполняет следующие задачи:  
  
    -   Проверяет, нажата ли левая кнопка мыши при перемещении мыши.  
  
    -   Упаковывает данные Circle в <xref:System.Windows.DataObject>. В данном случае элемент управления Circle упакует три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.  
  
    -   Вызывает статический <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> метод для инициализации операции перетаскивания и вставки. Передать следующие три параметра для <xref:System.Windows.DragDrop.DoDragDrop%2A> метод:  
  
        -   `dragSource` — ссылка на этот элемент управления.  
  
        -   `data` — <xref:System.Windows.DataObject> Создан в предыдущем примере кода.  
  
        -   `allowedEffects` Разрешенные операции перетаскивания и вставки, которые являются <xref:System.Windows.DragDropEffects.Copy> или <xref:System.Windows.DragDropEffects.Move>.  
  
3.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
4.  Выберите один из элементов управления Circle и перетащите его над панелями, другим элементом и <xref:System.Windows.Controls.TextBox>. При перетаскивании <xref:System.Windows.Controls.TextBox>, курсор изменяется для обозначения перемещения.  
  
5.  При перетаскивании круг <xref:System.Windows.Controls.TextBox>, нажмите клавишу CTRL. Обратите внимание на то, как изменится курсор, обозначая копирование.  
  
6.  Перетаскивание круга на <xref:System.Windows.Controls.TextBox>. Строковое представление цвета заливки круга добавляется к <xref:System.Windows.Controls.TextBox>.  
  
     ![Строковое представление цвета заливки элемента управления Circle](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")  
  
 По умолчанию курсор изменяется во время операции перетаскивания, чтобы указать, какой результат даст перетаскивание данных в ту или иную точку. Можно настроить получаемую пользователю путем обработки <xref:System.Windows.UIElement.GiveFeedback> событий и задав другой курсор.  
  
### <a name="to-give-feedback-to-the-user"></a>Обратная связь с пользователем  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  Добавьте следующие <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.GiveFeedback> события.  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     Это <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение выполняет следующие задачи:  
  
    -   Проверяет <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> значения, заданные в место вставки <xref:System.Windows.UIElement.DragOver> обработчика событий.  
  
    -   Задает пользовательский курсор на основе <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> значение. Курсор предназначен для предоставления визуальной обратной связи пользователю о том, какой результат будет иметь перетаскивание данных.  
  
3.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
4.  Перетащите одно круга контроль над панелями, другим элементом, и <xref:System.Windows.Controls.TextBox>. Обратите внимание, что курсоры теперь пользовательские курсоры, которые указаны в <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределения.  
  
     ![Перетаскивание с использованием пользовательских курсоров](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")  
  
5.  Выделите текст, `green` из <xref:System.Windows.Controls.TextBox>.  
  
6.  Перетащите текст `green` в элемент управления Circle. Обратите внимание, что отображаются курсоры по умолчанию: они указывают на результаты операции перетаскивания. Курсор обратной связи всегда задается источником перетаскивания.  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a>Реализация событий целевого объекта перетаскивания в пользовательском элементе управления  
 Изучая этот раздел, вы укажете, что пользовательский элемент управления является целевым объектом перетаскивания, переопределите методы, позволяющие пользовательскому элементу управления функционировать в качестве целевого объекта перетаскивания, и обработаете перемещенные в него данные.  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>Чтобы включить пользовательский элемент управления в качестве целевого объекта перетаскивания, выполните следующие действия.  
  
1.  Откройте файл Circle.xaml.  
  
2.  В открывающем <xref:System.Windows.Controls.UserControl> , добавьте <xref:System.Windows.UIElement.AllowDrop%2A> свойство и присвойте ему значение `true`.  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <xref:System.Windows.UIElement.OnDrop%2A> Метод вызывается, когда <xref:System.Windows.UIElement.AllowDrop%2A> свойству `true` и удалении данных из источника перетаскивания в пользовательский элемент управления Circle. В этом методе вы обработаете перемещенные данные и примените их к элементу управления Circle.  
  
### <a name="to-process-the-dropped-data"></a>Обработка вставляемых данных  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  Добавьте следующие <xref:System.Windows.UIElement.OnDrop%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.Drop> события.  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     Это <xref:System.Windows.UIElement.OnDrop%2A> переопределение выполняет следующие задачи:  
  
    -   Использует <xref:System.Windows.DataObject.GetDataPresent%2A> метод для проверки, если перетаскиваемые данные содержат строковый объект.  
  
    -   Использует <xref:System.Windows.DataObject.GetData%2A> метод для извлечения строковых данных, если он имеется.  
  
    -   Использует <xref:System.Windows.Media.BrushConverter> пытается преобразовать строку, <xref:System.Windows.Media.Brush>.  
  
    -   Если преобразование прошло успешно, применяет кисть к <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse> , предоставляет пользовательский Интерфейс элемента управления Circle.  
  
    -   Метки <xref:System.Windows.UIElement.Drop> событие как обработанное. Событие сброса необходимо пометить как обработанное, чтобы другие элементы, которые получают это событие, знали, что событие было обработано пользовательским элементом управления Circle.  
  
3.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
4.  Выделите текст, `green` в <xref:System.Windows.Controls.TextBox>.  
  
5.  Перетащите текст в элемент управления Circle. Элемент управления Circle поменяет цвет с синего на зеленый.  
  
     ![Преобразование строки в кисть](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")  
  
6.  Введите текст `green` в <xref:System.Windows.Controls.TextBox>.  
  
7.  Выделите текст, `gre` в <xref:System.Windows.Controls.TextBox>.  
  
8.  Перетащите его в элемент управления Circle. Обратите внимание, что курсор изменяется, чтобы указать, что перенос разрешен, но цвет элемента управления Circle не меняется, потому что `gre` — недопустимый цвет.  
  
9. Выполните перетаскивание с зеленого элемента управления Circle на синий. Элемент управления Circle поменяет цвет с синего на зеленый. Обратите внимание, что показано какие курсора зависит от того <xref:System.Windows.Controls.TextBox> или круга является источником перетаскивания.  
  
 Установка <xref:System.Windows.UIElement.AllowDrop%2A> свойства `true` и обработки перетаскиваемых данных — все, что необходимо для включения элемент как конечного расположения сброса. Однако для повышения удобства работы пользователя, необходимо также обрабатывать <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, и <xref:System.Windows.UIElement.DragOver> события. В этих событиях можно выполнять проверки и предоставлять дополнительную обратную связь пользователю до сброса данных.  
  
 При перетаскивании данных над пользовательским элементом управления Circle элемент управления должен уведомить источник перетаскивания, может ли он обработать переносимые данные. Если элемент управления не знает, как обрабатывать данные, он должен отклонить перетаскивание. Чтобы сделать это, обрабатывающий <xref:System.Windows.UIElement.DragOver> событий и набор <xref:System.Windows.DragEventArgs.Effects%2A> свойство.  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a>Проверка допустимости сброса данных  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  Добавьте следующие <xref:System.Windows.UIElement.OnDragOver%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.DragOver> события.  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     Это <xref:System.Windows.UIElement.OnDragOver%2A> переопределение выполняет следующие задачи:  
  
    -   Задает для свойства <xref:System.Windows.DragEventArgs.Effects%2A> значение <xref:System.Windows.DragDropEffects.None>.  
  
    -   Выполняет те же проверки, которые выполняются в <xref:System.Windows.UIElement.OnDrop%2A> метод, чтобы определить, может ли пользовательский элемент управления Circle обработать перетаскиваемые данные.  
  
    -   Если пользовательский элемент управления может обрабатывать данные, задает <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Copy> или <xref:System.Windows.DragDropEffects.Move>.  
  
3.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
4.  Выделите текст, `gre` в <xref:System.Windows.Controls.TextBox>.  
  
5.  Перетащите текст в элемент управления Circle. Обратите внимание, что курсор изменяется, чтобы указать, что перетаскивание не разрешено, потому что `gre` не является допустимым цветом.  
  
 Использование предварительного просмотра при перетаскивании повышает удобство работы пользователей. Пользовательский элемент управления Circle будут переопределены <xref:System.Windows.UIElement.OnDragEnter%2A> и <xref:System.Windows.UIElement.OnDragLeave%2A> методы. При перетаскивании данных над элементом управления, текущий фон <xref:System.Windows.Shapes.Shape.Fill%2A> сохраняется в переменной заполнителя. Затем строка преобразуется в кисть и применены к <xref:System.Windows.Shapes.Ellipse> , предоставляющий круга пользовательского интерфейса. Если перетаскиваемые данные вне круга без отпускания исходного <xref:System.Windows.Shapes.Shape.Fill%2A> повторно применяется значение круга.  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>Предварительный просмотр результатов операции перетаскивания  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  В классе Circle объявить закрытый <xref:System.Windows.Media.Brush> переменную с именем `_previousFill` и инициализируйте его, чтобы `null`.  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  Добавьте следующие <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.DragEnter> события.  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     Это <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение выполняет следующие задачи:  
  
    -   Сохраняет <xref:System.Windows.Shapes.Shape.Fill%2A> свойство <xref:System.Windows.Shapes.Ellipse> в `_previousFill` переменной.  
  
    -   Выполняет те же проверки, которые выполняются в <xref:System.Windows.UIElement.OnDrop%2A> метод, чтобы определить, будут ли данные могут преобразовываться в <xref:System.Windows.Media.Brush>.  
  
    -   Если данные преобразуются в допустимый <xref:System.Windows.Media.Brush>, применяется к <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse>.  
  
4.  Добавьте следующие <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.DragLeave> события.  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     Это <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение выполняет следующие задачи:  
  
    -   Применяет <xref:System.Windows.Media.Brush> сохраняется в `_previousFill` переменной <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse> , предоставляет пользовательский Интерфейс пользовательского элемента управления Circle.  
  
5.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
6.  Выделите текст, `green` в <xref:System.Windows.Controls.TextBox>.  
  
7.  Перетащите текст над элементом управления Circle, не сбрасывая его. Элемент управления Circle поменяет цвет с синего на зеленый.  
  
     ![Предварительный просмотр результатов операции перетаскивания](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")  
  
8.  Перетащите текст от элемента управления Circle. Элемент управления Circle изменится с зеленого на синий.  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a>Настройка панели для получения перемещенных данных  
 В этом разделе вы включите использование панелей, на которых размещены пользовательские элементы управления Circle, в качестве целевых объектов перетаскивания для перемещенных данных Circle. Будет реализован код, который позволяет переместить элемент Circle с одной панели на другую или копировать этот элемент, удерживая нажатой клавишу CTRL при перетаскивании элемента Circle.  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a>Включение панели в качестве целевого объекта перетаскивания  
  
1.  Откройте файл MainWindow.xaml.  
  
2.  Как показано в следующем XAML, в каждом из <xref:System.Windows.Controls.StackPanel> элементы управления, добавьте обработчики для <xref:System.Windows.UIElement.DragOver> и <xref:System.Windows.UIElement.Drop> события. Имя <xref:System.Windows.UIElement.DragOver> обработчик событий `panel_DragOver`и назовите <xref:System.Windows.UIElement.Drop> обработчик событий `panel_Drop`.  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  Откройте файл MainWindows.xaml.cs или MainWindow.xaml.vb.  
  
4.  Добавьте следующий код для <xref:System.Windows.UIElement.DragOver> обработчика событий.  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     Это <xref:System.Windows.UIElement.DragOver> обработчик событий выполняет следующие задачи:  
  
    -   Проверяет переносимых данных, который содержит данные «Объект», которая была упакована в <xref:System.Windows.DataObject> , пользовательский элемент управления Circle и передается в вызове <xref:System.Windows.DragDrop.DoDragDrop%2A>.  
  
    -   Если данные типа "Объект" присутствуют, обработчик проверяет нажата ли клавиша CTRL.  
  
    -   Если нажата клавиша CTRL, задает <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Copy>. В противном случае <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Move>.  
  
5.  Добавьте следующий код для <xref:System.Windows.UIElement.Drop> обработчика событий.  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     Это <xref:System.Windows.UIElement.Drop> обработчик событий выполняет следующие задачи:  
  
    -   Проверяет, является ли <xref:System.Windows.UIElement.Drop> уже обработано событие. Например, при удалении круг на другом Circle которой дескрипторы <xref:System.Windows.UIElement.Drop> событий, нужно панели, содержащей круг обрабатывать.  
  
    -   Если <xref:System.Windows.UIElement.Drop> событие не обрабатывается, проверяет ли нажата клавиша CTRL.  
  
    -   Если нажата клавиша CTRL при <xref:System.Windows.UIElement.Drop> происходит делает копию круга, управления и добавьте его к <xref:System.Windows.Controls.Panel.Children%2A> коллекцию <xref:System.Windows.Controls.StackPanel>.  
  
    -   Если не нажата клавиша CTRL, перемещает элемент управления Circle из <xref:System.Windows.Controls.Panel.Children%2A> коллекцию его родительской панели <xref:System.Windows.Controls.Panel.Children%2A> коллекцию на панели, который он был удален.  
  
    -   Наборы <xref:System.Windows.DragEventArgs.Effects%2A> свойство известить <xref:System.Windows.DragDrop.DoDragDrop%2A> метод выполнение операции перемещения или копирования.  
  
6.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
7.  Выделите текст, `green` из <xref:System.Windows.Controls.TextBox>.  
  
8.  Перетащите текст над элементом управления Circle и опустите его на элемент.  
  
9. Перетащите элемент управления Circle из левой панели в правую панель и опустите его. Круг удаляется из <xref:System.Windows.Controls.Panel.Children%2A> коллекцию левой панели и добавляется в коллекцию Children правой панели.  
  
10. Перетащите элемент управления Circle с панели, на которой он находится, на другую панель и опустите, не отпуская клавишу CTRL. Круг копируется и добавляется копия <xref:System.Windows.Controls.Panel.Children%2A> коллекции, принимающей панели.  
  
     ![Перетаскивание элемента управления Circle с нажатой клавишей CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о перетаскивании](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
