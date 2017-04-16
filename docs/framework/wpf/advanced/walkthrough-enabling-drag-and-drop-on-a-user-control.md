---
title: "Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "перетаскивание [WPF], пошаговое руководство"
  - "пошаговое руководство [WPF], перетаскивание"
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления
В этом пошаговом руководстве демонстрируется создание пользовательского элемента управления, который участвует в передаче данных с помощью перетаскивания в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 В пошаговом руководстве создается пользовательский элемент управления WPF <xref:System.Windows.Controls.UserControl>, который представляет круг.  В этом элементе управления реализуется функциональность, поддерживающая передачу данных посредством перетаскивания.  Например, при перетаскивании из одного элемента управления Circle в другой данные цвета Fill копируются из исходного круга в целевой круг.  При перетаскивании из одного элемента управления Circle в элемент управления <xref:System.Windows.Controls.TextBox> данные цвета Fill копируются в элемент управления <xref:System.Windows.Controls.TextBox>.  Также будет создано небольшое приложение, которое содержит два элемента управления панели и элемент управления <xref:System.Windows.Controls.TextBox> для тестирования функции перетаскивания.  Будет написан код, который обеспечивает обработку перетаскиваемых данных круга панелями, что, в свою очередь, позволяет перемещать или копировать круги из дочерней коллекции одной панели в другую панель.  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   Создание пользовательского элемента управления.  
  
-   Настройка пользовательского элемента управления в качестве источника перетаскивания.  
  
-   Настройка пользовательского элемента управления в качестве объекта\-приемника.  
  
-   Настройка панели для получения данных, перетащенных из пользовательского элемента управления.  
  
## Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   Visual Studio 2010  
  
## Создание проекта приложения  
 В этом разделе создается инфраструктура приложения, которая включает главную страницу с двумя панелями и элементом управления <xref:System.Windows.Controls.TextBox>.  
  
### Создание проекта  
  
1.  Создайте новый проект приложения WPF на языке Visual Basic или Visual C\# с именем `DragDropExample`.  Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/ru-ru/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Откройте файл MainWindow.xaml.  
  
3.  Добавьте следующую разметку между открывающим и закрывающим тегами <xref:System.Windows.Controls.Grid>.  
  
     Данная разметка создает пользовательский интерфейс для тестового приложения.  
  
     [!code-xml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## Добавление нового пользовательского элемента управления в проект  
 В этом разделе в проект добавляется новый пользовательский элемент управления.  
  
### Добавление нового пользовательского элемента управления  
  
1.  В меню "Проект" выберите команду **Добавить пользовательский элемент управления**.  
  
2.  В диалоговом окне "Добавление нового элемента" измените имя на `Circle.xaml` и нажмите кнопку **Добавить**.  
  
     В проект добавляется файл Circle.xaml и его код программной части.  
  
3.  Откройте файл Circle.xaml.  
  
     Этот файл будет содержать элементы пользовательского интерфейса пользовательского элемента управления.  
  
4.  Добавьте следующую разметку в корневой элемент <xref:System.Windows.Controls.Grid>, чтобы создать простой пользовательский элемент управления, содержащий синий круг в качестве своего пользовательского интерфейса.  
  
     [!code-xml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
6.  В C\# добавьте следующий код после конструктора по умолчанию, чтобы создать конструктор копий.  В Visual Basic добавьте следующий код для создания конструктора по умолчанию и конструктора копий.  
  
     Чтобы обеспечить возможность копирования пользовательского элемента управления, метод конструктора копий добавляется в файл кода программной части.  В упрощенном пользовательском элементе управления Circle копируются только свойство Fill и размер пользовательского элемента управления.  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### Добавление пользовательского элемента управления в главное окно  
  
1.  Откройте файл MainWindow.xaml.  
  
2.  Добавьте следующий код XAML в открывающий тег <xref:System.Windows.Window>, чтобы создать ссылку на пространство имен XML для текущего приложения.  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  В первом элементе управления <xref:System.Windows.Controls.StackPanel> добавьте следующий код XAML, чтобы создать два экземпляра пользовательского элемента управления Circle в первую панель.  
  
     [!code-xml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     Полный код XAML для панели выглядит следующим образом.  
  
     [!code-xml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## Реализация событий источника перетаскивания в пользовательском элементе управления  
 В этом разделе переопределяется метод <xref:System.Windows.UIElement.OnMouseMove%2A> и инициируется операция перетаскивания.  
  
 В момент начала перетаскивания \(после нажатия кнопки мыши и перемещения мыши\) передаваемые данные упаковываются в объект <xref:System.Windows.DataObject>.  В этом случае элемент управления Circle упаковывает три элемента данных: строковое представление цвета Fill, представление своей высоты в виде числа двойной точности и копию себя самого.  
  
### Инициирование операции перетаскивания  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  Добавьте следующий переопределенный метод <xref:System.Windows.UIElement.OnMouseMove%2A>, чтобы обеспечить обработку событий <xref:System.Windows.UIElement.MouseMove> в классе.  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     Переопределенный метод <xref:System.Windows.UIElement.OnMouseMove%2A> выполняет следующие задачи.  
  
    -   Проверяет, нажата ли левая кнопка мыши при перемещении мыши.  
  
    -   Упаковывает данные Circle в объект <xref:System.Windows.DataObject>.  В этом случае элемент управления Circle упаковывает три элемента данных: строковое представление цвета Fill, представление своей высоты в виде числа двойной точности и копию себя самого.  
  
    -   Вызывает статический метод <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=fullName> для инициирования операции перетаскивания.  В метод <xref:System.Windows.DragDrop.DoDragDrop%2A> передаются следующие три параметра.  
  
        -   `dragSource`— ссылка на этот элемент управления.  
  
        -   `data` — объект <xref:System.Windows.DataObject>, созданный в предыдущем коде.  
  
        -   `allowedEffects` — разрешенные операции перетаскивания: <xref:System.Windows.DragDropEffects> и <xref:System.Windows.DragDropEffects>.  
  
3.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
4.  Щелкните один из элементов управления Circle и перетащите его над панелями, другим элементом управления Circle и элементом управления <xref:System.Windows.Controls.TextBox>.  При перетаскивании над элементом управления <xref:System.Windows.Controls.TextBox> курсор изменяется для обозначения перемещения.  
  
5.  При перетаскивании элемента управления Circle над элементом управления <xref:System.Windows.Controls.TextBox> нажмите клавишу CTRL.  Обратите внимание на изменение курсора, который теперь обозначает копирование.  
  
6.  Перетащите элемент управления Circle в элемент управления <xref:System.Windows.Controls.TextBox>.  К элементу управления <xref:System.Windows.Controls.TextBox> добавляется строковое представление цвета заливки элемента управления Circle.  
  
     ![Строковое представление цвета заливки круга](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop\_ColorString")  
  
 По умолчанию в ходе операции перетаскивания курсор изменяется для обозначения последствий перетаскивания данных.  Обработав событие <xref:System.Windows.UIElement.GiveFeedback> и задав другой курсор, можно настроить получаемую пользователем обратную связь.  
  
### Предоставление обратной связи пользователю  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  Добавьте следующий переопределенный метод <xref:System.Windows.UIElement.OnGiveFeedback%2A>, чтобы обеспечить обработку событий <xref:System.Windows.UIElement.GiveFeedback> в классе.  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     Переопределенный метод <xref:System.Windows.UIElement.OnGiveFeedback%2A> выполняет следующие задачи.  
  
    -   Проверяет значения свойства <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>, заданные в обработчике событий <xref:System.Windows.UIElement.DragOver> объекта\-приемника.  
  
    -   Задает пользовательский курсор на основе значения <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>.  Курсор предназначен для предоставления пользователю визуальной информации о последствиях, которые будет иметь перетаскивание данных.  
  
3.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
4.  Перетащите один из элементов управления Circle над панелями, другим элементом управления Circle и элементом управления <xref:System.Windows.Controls.TextBox>.  Обратите внимание, что теперь отображаются пользовательские курсоры, заданные в переопределенном методе <xref:System.Windows.UIElement.OnGiveFeedback%2A>.  
  
     ![Перетаскивание с пользовательскими курсорами](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop\_CustomCursor")  
  
5.  Выберите текст `green` в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
6.  Перетащите текст `green` в элемент управления Circle.  Обратите внимание, что отображаются курсоры по умолчанию, которые указывают на последствия операции перетаскивания.  Курсор обратной связи всегда задается источником перетаскивания.  
  
## Реализация событий объекта\-приемника в пользовательском элементе управления  
 В этом разделе указывается, что пользовательский элемент управления является объектом\-приемником, переопределяются методы, которые позволяют пользовательскому элементу управления функционировать в качестве объекта\-приемника, и обрабатываются перетащенные в объект\-приемник данные.  
  
### Настройка пользовательского элемента управления в качестве объекта\-приемника  
  
1.  Откройте файл Circle.xaml.  
  
2.  В открывающем теге <xref:System.Windows.Controls.UserControl> добавьте свойство <xref:System.Windows.UIElement.AllowDrop%2A> и задайте для него значение `true`.  
  
     [!code-xml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 Если для свойства <xref:System.Windows.UIElement.AllowDrop%2A> задано значение `true`, то при перетаскивании данных из источника перетаскивания в пользовательский элемент управления Circle вызывается метод <xref:System.Windows.UIElement.OnDrop%2A>.  В этом методе перетащенные данные обрабатываются и применяются к элементу управления Circle.  
  
### Обработка перетащенных данных  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  Добавьте следующий переопределенный метод <xref:System.Windows.UIElement.OnDrop%2A>, чтобы обеспечить обработку событий <xref:System.Windows.UIElement.Drop> в классе.  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     Переопределенный метод <xref:System.Windows.UIElement.OnDrop%2A> выполняет следующие задачи.  
  
    -   Проверяет, содержат ли перетащенные данные строковый объект, используя метод <xref:System.Windows.DataObject.GetDataPresent%2A>.  
  
    -   При наличии строковых данных извлекает их с помощью метода <xref:System.Windows.DataObject.GetData%2A>.  
  
    -   Пытается преобразовать строку в объект <xref:System.Windows.Media.Brush>, используя метод <xref:System.Windows.Media.BrushConverter>.  
  
    -   В случае успешного завершения преобразования применяет кисть к свойству <xref:System.Windows.Shapes.Shape.Fill%2A> объекта <xref:System.Windows.Shapes.Ellipse>, который предоставляет пользовательский интерфейс элемента управления Circle.  
  
    -   Помечает событие <xref:System.Windows.UIElement.Drop> как обработанное.  Событие сброса необходимо пометить как обработанное для оповещения других получающих это событие элементов, что оно уже обработано элементом управления Circle.  
  
3.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
4.  Выберите текст `green` в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
5.  Перетащите текст в элемент управления Circle и сбросьте его.  Цвет элемента управления Circle изменится с синего на зеленый.  
  
     ![Преобразование строки в кисть](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop\_DropGreenText")  
  
6.  Введите текст `green` в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
7.  Выберите текст `gre` в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
8.  Перетащите текст в элемент управления Circle и сбросьте его.  Обратите внимание, что курсор изменяется для обозначения допустимости перетаскивания, однако цвет элемента управления Circle не изменяется, поскольку `gre` не является допустимым цветом.  
  
9. Перетащите из зеленого элемента управления Circle в синий элемент управления Circle.  Цвет элемента управления Circle изменится с синего на зеленый.  Обратите внимание, что отображаемый курсор зависит от того, какой элемент управления является источником перетаскивания — <xref:System.Windows.Controls.TextBox> или Circle.  
  
 Чтобы сделать элемент объектом\-приемником, достаточно задать для его свойства <xref:System.Windows.UIElement.AllowDrop%2A> значение `true` и обработать перетащенные данные.  Однако для повышения удобства использования необходимо также обработать события <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave> и <xref:System.Windows.UIElement.DragOver>.  В этих событиях перед сбрасыванием данных можно выполнить проверки и предоставить пользователю дополнительную обратную связь.  
  
 Когда данные перетаскиваются над пользовательским элементом управления Circle, этот элемент управления должен уведомить источник перетаскивания, может ли он обработать перетаскиваемые данные.  Если элементу управления не известно, как обработать данные, он должен отклонить перетаскивание.  Для этого обрабатывается событие <xref:System.Windows.UIElement.DragOver> и задается свойство <xref:System.Windows.DragEventArgs.Effects%2A>.  
  
### Проверка допустимости перетаскивания данных  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  Добавьте следующий переопределенный метод <xref:System.Windows.UIElement.OnDragOver%2A>, чтобы обеспечить обработку событий <xref:System.Windows.UIElement.DragOver> в классе.  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     Переопределенный метод <xref:System.Windows.UIElement.OnDragOver%2A> выполняет следующие задачи.  
  
    -   Присваивает свойству <xref:System.Windows.DragEventArgs.Effects%2A> значение <xref:System.Windows.DragDropEffects>.  
  
    -   Выполняет те же проверки, которые выполнялись методом <xref:System.Windows.UIElement.OnDrop%2A>, чтобы определить, может ли пользовательский элемент управления Circle обработать перетащенные данные.  
  
    -   Если пользовательский элемент управления может обработать данные, свойству <xref:System.Windows.DragEventArgs.Effects%2A> задается значение <xref:System.Windows.DragDropEffects> или <xref:System.Windows.DragDropEffects>.  
  
3.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
4.  Выберите текст `gre` в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
5.  Перетащите текст в элемент управления Circle.  Обратите внимание, что теперь курсор изменяется для обозначения недопустимости перетаскивания, поскольку `gre` не является допустимым цветом.  
  
 Можно еще больше расширить взаимодействие с пользователем, применив предварительный просмотр к операции перетаскивания.  Для пользовательского элемента управления Circle будут переопределены методы <xref:System.Windows.UIElement.OnDragEnter%2A> и <xref:System.Windows.UIElement.OnDragLeave%2A>.  Когда данные перетаскиваются над элементом управления, текущий фон <xref:System.Windows.Shapes.Shape.Fill%2A> сохраняется в переменной\-заполнителе.  Затем строка преобразуется в кисть и применяется к объекту <xref:System.Windows.Shapes.Ellipse>, который предоставляет пользовательский интерфейс элемента управления Circle.  Если данные перетаскиваются за пределы элемента управления Circle без их сбрасывания, к элементу управления Circle вновь применяется исходное значение свойства <xref:System.Windows.Shapes.Shape.Fill%2A>.  
  
### Предварительный просмотр последствий операции перетаскивания  
  
1.  Откройте файл Circle.xaml.cs или Circle.xaml.vb.  
  
2.  В классе Circle объявите закрытую переменную <xref:System.Windows.Media.Brush> с именем `_previousFill` и инициализируйте ее значением `null`.  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  Добавьте следующий переопределенный метод <xref:System.Windows.UIElement.OnDragEnter%2A>, чтобы обеспечить обработку событий <xref:System.Windows.UIElement.DragEnter> в классе.  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     Переопределенный метод <xref:System.Windows.UIElement.OnDragEnter%2A> выполняет следующие задачи.  
  
    -   Сохраняет значение свойства <xref:System.Windows.Shapes.Shape.Fill%2A> объекта <xref:System.Windows.Shapes.Ellipse> в переменной `_previousFill`.  
  
    -   Выполняет те же проверки, которые выполнялись методом <xref:System.Windows.UIElement.OnDrop%2A>, чтобы определить, можно ли преобразовать данные в объект <xref:System.Windows.Media.Brush>.  
  
    -   Если данные преобразуются в допустимый объект <xref:System.Windows.Media.Brush>, этот объект применяется к свойству <xref:System.Windows.Shapes.Shape.Fill%2A> объекта <xref:System.Windows.Shapes.Ellipse>.  
  
4.  Добавьте следующий переопределенный метод <xref:System.Windows.UIElement.OnDragLeave%2A>, чтобы обеспечить обработку событий <xref:System.Windows.UIElement.DragLeave> в классе.  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     Переопределенный метод <xref:System.Windows.UIElement.OnDragLeave%2A> выполняет следующие задачи.  
  
    -   Применяет объект <xref:System.Windows.Media.Brush>, сохраненный в переменной `_previousFill`, к свойству <xref:System.Windows.Shapes.Shape.Fill%2A> объекта <xref:System.Windows.Shapes.Ellipse>, который предоставляет пользовательский интерфейс пользовательского элемента управления Circle.  
  
5.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
6.  Выберите текст `green` в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
7.  Перетащите текст над элементом управления Circle без его сбрасывания.  Цвет элемента управления Circle изменится с синего на зеленый.  
  
     ![Предварительный просмотр последствий операции перетаскивания](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop\_PreviewEffects")  
  
8.  Перетащите текст за границы элемента управления Circle.  Цвет элемента управления Circle изменится с зеленого обратно на синий.  
  
## Настройка панели для получения перетащенных данных  
 В этом разделе панели, в которых размещаются пользовательские элементы управления Circle, настраиваются для функционирования в качестве объектов\-приемников перетащенных данных Circle.  Будет реализован код, которые позволяет перемещать элемент управления Circle из одной панели в другую и создавать копию элемента управления Circle, удерживая клавишу CTRL во время перетаскивания Circle.  
  
### Настройка панели в качестве объекта\-приемника  
  
1.  Откройте файл MainWindow.xaml.  
  
2.  В каждом элементе управления <xref:System.Windows.Controls.StackPanel> добавьте обработчики событий <xref:System.Windows.UIElement.DragOver> и <xref:System.Windows.UIElement.Drop>, как показано в следующем коде XAML.  Присвойте обработчику событий <xref:System.Windows.UIElement.DragOver> имя `panel_DragOver`, а обработчику событий <xref:System.Windows.UIElement.Drop> имя `panel_Drop`.  
  
     [!code-xml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  Откройте файл MainWindows.xaml.cs или MainWindow.xaml.vb.  
  
4.  В обработчик события <xref:System.Windows.UIElement.DragOver> добавьте следующий код.  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     Обработчик событий <xref:System.Windows.UIElement.DragOver> выполняет следующие задачи.  
  
    -   Проверяет, действительно ли перетаскиваемые данные содержат данные "Object", которые были упакованы в объект <xref:system.Windows.DataObject> пользовательским элементом управления Circle и переданы в вызванный метод <xref:System.Windows.DragDrop.DoDragDrop%2A>.  
  
    -   При наличии данных "Object" проверяет, нажата ли клавиша CTRL.  
  
    -   Если клавиша CTRL нажата, задает свойству <xref:System.Windows.DragEventArgs.Effects%2A> значение <xref:System.Windows.DragDropEffects>.  В противном случае задает свойству <xref:System.Windows.DragEventArgs.Effects%2A> значение <xref:System.Windows.DragDropEffects>.  
  
5.  В обработчик события <xref:System.Windows.UIElement.Drop> добавьте следующий код.  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     Обработчик событий <xref:System.Windows.UIElement.Drop> выполняет следующие задачи.  
  
    -   Проверяет, обработано ли событие <xref:System.Windows.UIElement.Drop>.  Например, если элемент управления Circle перетащен на другой элемент управления Circle, который обрабатывает событие <xref:System.Windows.UIElement.Drop>, панели, содержащей этот элемент управления, не требуется повторно обрабатывать событие.  
  
    -   Если событие <xref:System.Windows.UIElement.Drop> не обработано, проверяет, нажата ли клавиша CTRL.  
  
    -   Если при возникновении события <xref:System.Windows.UIElement.Drop> клавиша CTRL нажата, обработчик создает копию элемента управления Circle и добавляет его в коллекцию <xref:System.Windows.Controls.Panel.Children%2A> элемента управления <xref:System.Windows.Controls.StackPanel>.  
  
    -   Если клавиша CTRL не нажата, обработчик перемещает элемент управления Circle из коллекции <xref:System.Windows.Controls.Panel.Children%2A> его родительской панели в коллекцию <xref:System.Windows.Controls.Panel.Children%2A> панели, в которую перетаскивается элемент управления.  
  
    -   Задает значение свойства <xref:System.Windows.DragEventArgs.Effects%2A>, чтобы уведомить метод <xref:System.Windows.DragDrop.DoDragDrop%2A>, какая операция была выполнена — копирование или перетаскивание.  
  
6.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
7.  Выберите текст `green` в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
8.  Перетащите текст над элементом управления Circle и сбросьте его.  
  
9. Перетащите элемент управления Circle из левой панели в правую панель.  Элемент управления Circle удаляется из коллекции <xref:System.Windows.Controls.Panel.Children%2A> левой панели и добавляется в коллекцию Children правой панели.  
  
10. Перетащите элемент управления Circle из панели, в которой он находится, в другую панель, удерживая клавишу CTRL.  Элемент управления Circle копируется, и его копия добавляется в коллекцию <xref:System.Windows.Controls.Panel.Children%2A> принимающей панели.  
  
     ![Перетаскивание круга при нажатой клавише CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop\_PanelDrop")  
  
## См. также  
 [Общие сведения о перетаскивании](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)