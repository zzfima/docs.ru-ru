---
title: "Общие сведения о двусторонних возможностях в WPF | Microsoft Docs"
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
  - "возможности двунаправленного письма"
  - "FlowDirection - cвойство"
  - "FlowDocument - cвойство"
  - "Span - элементы"
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Общие сведения о двусторонних возможностях в WPF
В отличие от любых других платформ разработки, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеет множество возможностей, поддерживающих быструю разработку двунаправленного содержимого, например, данных, смешанных слева направо и справа налево, в одном и том же документе.  В то же время [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] дает отличный опыт пользователям, которым необходимы двунаправленные возможности, например, пользователям, говорящим на иврите и арабском языке.  
  
 В следующих разделах объясняются многие двунаправленные возможности, приводятся примеры, иллюстрирующие способы достижения наилучшего отображения на экране двунаправленного содержимого.  Большинство образцов использует [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], хотя принцип можно легко применить к коду [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] или [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)].  
  
   
  
<a name="FlowDirection"></a>   
## FlowDirection  
 Основным свойством, определяющим направление потока содержимого в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], является <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  Этому свойству может быть присвоено одно из двух значений перечисления, <xref:System.Windows.FlowDirection> или <xref:System.Windows.FlowDirection>.  Свойство доступно для всех элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые наследуют из <xref:System.Windows.FrameworkElement>.  
  
 В следующих примерах задается направление потока элемента <xref:System.Windows.Controls.TextBox>.  
  
 **Направление потока слева направо**  
  
 [!code-xml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Направление потока справа налево**  
  
 [!code-xml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 Приведенный ниже рисунок показывает как предыдущий код визуализирует.  
  
 **Пример FlowDirection**  
  
 ![Выравнивание TextBlock](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.png "LefttoRightRighttoLeft")  
  
 Элемент в дереве [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] будут наследовать <xref:System.Windows.FrameworkElement.FlowDirection%2A> из контейнера.  В следующем примере <xref:System.Windows.Controls.TextBlock> находится внутри <xref:System.Windows.Controls.Grid>, который постоянно хранится в <xref:System.Windows.Window>.  Задание <xref:System.Windows.FrameworkElement.FlowDirection%2A> для <xref:System.Windows.Window> подразумевает его задание как для <xref:System.Windows.Controls.Grid>, так и для <xref:System.Windows.Controls.TextBlock>.  
  
 Следующий пример демонстрирует установку <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 [!code-xml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 Верхний уровень <xref:System.Windows.Window> имеет <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection>, поэтому все элементы, содержащиеся в нем, наследуют то же <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  Чтобы переопределить заданное <xref:System.Windows.FrameworkElement.FlowDirection%2A>, к элементу необходимо добавить явное изменение направления, такое как второй <xref:System.Windows.Controls.TextBlock> в предыдущем примере, который изменяется на <xref:System.Windows.FlowDirection>.  Когда не определен <xref:System.Windows.FrameworkElement.FlowDirection%2A>, применяется значение по умолчанию <xref:System.Windows.FlowDirection>.  
  
 На следующем рисунке показаны выходные данные предыдущего примера.  
  
 **Пример явно заданного FlowDirection**  
  
 ![Иллюстрация направления потока](../../../../docs/framework/wpf/advanced/media/flowdir.png "FlowDir")  
  
<a name="FlowDocument"></a>   
## FlowDocument  
 Многие платформы разработки, такие как [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] и Java, обеспечивают специальную поддержку развития двунаправленного содержимого.  Языки разметки, такие как [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], предоставляют редакторы записи необходимой разметки для отображения на экране текста в любом требуемом направлении, например тег 4.0 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], "dir", который принимает значения "rtl" или "ltr".  Этот тег аналогичен свойству <xref:System.Windows.FrameworkElement.FlowDirection%2A>, но свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> предоставляет более прогрессивный способ доступа к текстовому содержимому макета и может быть использовано для иного чем текст содержимого.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент <xref:System.Windows.Documents.FlowDocument> является универсальным элементом [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который может размещать сочетания текста, таблиц, изображений и других элементов.  В следующих разделах примеры используют этот элемент.  
  
 Добавление текста к <xref:System.Windows.Documents.FlowDocument> можно быть осуществлено несколькими способами.  Простой способ добавить текст — сделать это через <xref:System.Windows.Documents.Paragraph>, который является элементом блочного уровня, используемого для группировки такого содержимого, как текст.  Чтобы добавить текст в элементы встроенного уровня, в примерах используются элементы <xref:System.Windows.Documents.Span> и <xref:System.Windows.Documents.Run>.  <xref:System.Windows.Documents.Span> является элементом поточного содержимого встроенного уровня, который используется для группировки других встроенных элементов, а <xref:System.Windows.Documents.Run> является элементом поточного содержимого встроенного уровня, который предназначен для содержания цепочки неформатированного текста.  <xref:System.Windows.Documents.Span> может содержать несколько элементов <xref:System.Windows.Documents.Run>.  
  
 Первый пример документа содержит документ, имеющий несколько сетевых совместно используемых имен; например `\\server1\folder\file.ext`.  Независимо от того, есть ли эта сетевая ссылка в арабском или английском документе, она потребуется для того, чтобы появиться на том же пути.  Приведенный ниже рисунок показывает ссылку в арабском документе <xref:System.Windows.FlowDirection>.  
  
 **Пример использования элемента Span**  
  
 ![Документы с направлением потока справа&#45;налево](../../../../docs/framework/wpf/advanced/media/flowdocument.png "FlowDocument")  
  
 Поскольку текст является <xref:System.Windows.FlowDirection>, все специальные символы, такие как "\\", разделяют текст справа налево.  Эти результаты в ссылке показаны в неверном порядке, поэтому, чтобы решить проблему, текст должен быть встраиваемым, сохранить в результате, текст должен быть внедрен, чтобы сохранить отдельное <xref:System.Windows.Documents.Run>, протекающего <xref:System.Windows.FlowDirection>.  Вместо того, чтобы иметь отдельные <xref:System.Windows.Documents.Run> для каждого языка, лучшим способом решить проблему является внедрение наименее часто используемого английского текста в больший по размерам арабский <xref:System.Windows.Documents.Span>.  
  
 Это проиллюстрировано на следующем рисунке.  
  
 **Пример использования элемента Run, встроенного в элемент Span**  
  
 ![Снимок экрана XamlPad](../../../../docs/framework/wpf/advanced/media/runspan.png "RunSpan")  
  
 Следующий пример демонстрирует использование в документах элементов <xref:System.Windows.Documents.Run> и <xref:System.Windows.Documents.Span>.  
  
 [!code-xml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## Элементы Span  
 Элемент <xref:System.Windows.Documents.Span> работает как разделительный граничный знак между текстами с разными направлениями потоков.  Даже элементы <xref:System.Windows.Documents.Span> с одинаковым направлением полагаются элементами, имеющими различные двунаправленные области, что означает, что элементы <xref:System.Windows.Documents.Span> упорядочены в <xref:System.Windows.FlowDirection> контейнера, только содержимое в элементе <xref:System.Windows.Documents.Span> следует <xref:System.Windows.FlowDirection> элемента <xref:System.Windows.Documents.Span>.  
  
 Приведенный ниже рисунок показывает направление потока нескольких элементов <xref:System.Windows.Controls.TextBlock>.  
  
 **Пример FlowDirection в нескольких элементах TextBlock**  
  
 ![Текстовые блоки с различными направлениями потоков](../../../../docs/framework/wpf/advanced/media/span.png "Span")  
  
 В следующем примере показано использование элементов <xref:System.Windows.Documents.Span> и <xref:System.Windows.Documents.Run> для получения результатов, представленных на предыдущем рисунке.  
  
 [!code-xml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 В элементах <xref:System.Windows.Controls.TextBlock> примера, элементы <xref:System.Windows.Documents.Span> раскладываются согласно <xref:System.Windows.FlowDirection> их родительских элементов, но текст внутри каждого элемента <xref:System.Windows.Documents.Span> располагается согласно своему собственному <xref:System.Windows.FlowDirection>.  Это применимо для латинского, арабского или любого другого языка.  
  
### Добавление xml:lang  
 Приведенный ниже рисунок показывает другой пример, использующий номера и арифметические выражения, такие как `"200.0+21.4=221.4"`.  Обратите внимание, что установлено только <xref:System.Windows.FlowDirection>.  
  
 **Пример чисел, использующих только FlowDirection**  
  
 ![Числа с направлением потока справа&#45;налево](../../../../docs/framework/wpf/advanced/media/langattribute.png "LangAttribute")  
  
 Пользователи данного приложения будут разочарованы выходными данными, даже если <xref:System.Windows.FlowDirection> является правильным, числа не становятся арабскими, хотя должны были стать.  
  
 Элементы XAML могут включать атрибут [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] \(`xml:lang`\), определяющий язык каждого элемента.  XAML также поддерживает принцип языка [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] — значения `xml:lang`, примененные к родительским элементам в дереве, используются для дочерних элементов.  В предыдущем примере, так как не был определен язык для элемента <xref:System.Windows.Documents.Run> или для любого из элементов выше него, использовался язык по умолчанию `xml:lang``en-US` для XAML.  Внутренний алгоритм вида чисел [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] выбирает числа в соответствующем языке, в данном случае — английском.  Для того чтобы правильно отображались арабские цифры необходимо, чтобы был задан элемент `xml:lang`.  
  
 На следующем рисунке показан пример, где добавлен элемент `xml:lang`.  
  
 **Пример использования атрибута xml:lang**  
  
 ![Арабские числа с направлением потока справа&#45;налево](../../../../docs/framework/wpf/advanced/media/langattribute2.png "LangAttribute2")  
  
 В следующем примере в приложение добавляется элемент `xml:lang`.  
  
 [!code-xml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Необходимо помнить, что многие языки имеют различные значения `xml:lang` в зависимости от целевого региона, например `"ar-SA"` и `"ar-EG"` представляют собой два диалекта арабского языка.  В предыдущих примерах показано, что необходимо определить как значение `xml:lang`, так и <xref:System.Windows.FlowDirection>.  
  
<a name="FlowDirectionNontext"></a>   
## FlowDirection с нетекстовыми элементами  
 <xref:System.Windows.FlowDirection> определяет не только перетекание текста в текстовом элементе, но также направление потока практически любого другого элемента [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Приведенный ниже рисунок показывает <xref:System.Windows.Controls.ToolBar>, использующую горизонтальную <xref:System.Windows.Media.LinearGradientBrush> для отрисовки фона.  
  
 **Пример ToolBar с градиентом слева направо**  
  
 ![Снимок экрана градиента](../../../../docs/framework/wpf/advanced/media/gradient.png "Gradient")  
  
 После установки <xref:System.Windows.FlowDirection> на <xref:System.Windows.FlowDirection>, не только кнопки <xref:System.Windows.Controls.ToolBar> располагаются справа налево, но даже <xref:System.Windows.Media.LinearGradientBrush> перестраивает свои смещения для перетекания справа налево.  
  
 Приведенный ниже рисунок показывает перестройку <xref:System.Windows.Media.LinearGradientBrush>.  
  
 **Пример ToolBar с градиентом справа налево**  
  
 ![Градиент с направлением изменения цвета справа&#45;налево](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.png "Gradient2\_WPF")  
  
 В следующем примере отрисовывается <xref:System.Windows.FlowDirection> <xref:System.Windows.Controls.ToolBar>.  \(Чтобы нарисовать его слева направо, удалите атрибут <xref:System.Windows.FlowDirection> в <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### Исключения FlowDirection  
 Существует несколько вариантов, когда <xref:System.Windows.FlowDirection> ведет себя не так, как ожидалось.  В этом разделе рассматриваются два из этих исключений.  
  
 **Изображение**  
  
 <xref:System.Windows.Controls.Image> представляет элемент управления, который выводит на экран изображение.  В [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] его можно использовать со свойством <xref:System.Windows.Controls.Image.Source%2A>, определяющим [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] <xref:System.Windows.Controls.Image> для вывода на экран.  
  
 В отличие от других элементов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], <xref:System.Windows.Controls.Image> не наследует <xref:System.Windows.FlowDirection> из контейнера.  Однако, если <xref:System.Windows.FlowDirection> явно задано, равным <xref:System.Windows.FlowDirection>, то <xref:System.Windows.Controls.Image> выводится на экран зеркально отображенным относительно горизонтали.  Это реализуется как удобное средство для разработчиков двунаправленного содержимого; так как в некоторых случаях зеркальное горизонтальное отражение создает требуемый эффект.  
  
 Приведенный ниже рисунок показывает зеркально отраженное <xref:System.Windows.Controls.Image>.  
  
 **Пример зеркально отображенного изображения**  
  
 ![Снимок экрана XamlPad](../../../../docs/framework/wpf/advanced/media/image.png "Image")  
  
 В следующем примере показано, что <xref:System.Windows.Controls.Image> не наследует <xref:System.Windows.FlowDirection> из <xref:System.Windows.Controls.StackPanel>, содержащей его.  **Примечание** Чтобы запустить этот пример необходимо, чтобы на диске C:\\ находился файл с именем **ms\_logo.jpg**.  
  
 [!code-xml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Примечание** В загрузку включен файл **ms\_logo.jpg**.  В коде предполагается, что JPG\-файл находится не внутри проекта, а в некотором другом месте на диске C:\\.  Необходимо скопировать JPG\-файл из файлов проекта на диск C:\\ или изменить код для поиска файла внутри проекта.  Чтобы это сделать, измените `Source="file://c:/ms_logo.jpg"` на `Source="ms_logo.jpg"`.  
  
 **Пути**  
  
 В дополнение к <xref:System.Windows.Controls.Image>, другим интересным элементом является <xref:System.Windows.Shapes.Path>.  Объект Path является объектом, который может рисовать последовательности соединенных прямых и кривых.  Он ведет себя аналогичным образом что и <xref:System.Windows.Controls.Image> относительно своего <xref:System.Windows.FlowDirection>; например его <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection> является отражением относительно горизонтали его же <xref:System.Windows.FlowDirection>.  Однако, в отличие от <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> наследует свое <xref:System.Windows.FlowDirection> из контейнера и не нуждается в его явном указании.  
  
 В следующем примере рисуется простая стрелка, использующая три строки.  Первая стрелка наследует направление потока <xref:System.Windows.FlowDirection> из <xref:System.Windows.Controls.StackPanel>, таким образом, точки начала и конца отсчитываются из корня на правой стороне.  Вторая стрелка, имеющая явно заданное <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection>, также начинается на правой стороне.  Однако, третья стрелка начинается из корня на левой стороне.  Дополнительные сведения по рисовании содержатся в <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 На следующем рисунке показаны выходные данные предыдущего примера.  
  
 **Пример рисования стрелок с помощью элемента Path**  
  
 ![Пути](../../../../docs/framework/wpf/advanced/media/paths.png "Paths")  
  
 <xref:System.Windows.Controls.Image> и <xref:System.Windows.Shapes.Path> являются двумя примерами того, как [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] использует <xref:System.Windows.FlowDirection>.  По сравнению с трассировкой элементов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в конкретном направлении внутри контейнера, <xref:System.Windows.FlowDirection> может использоваться с такими элементами, как <xref:System.Windows.Controls.InkPresenter>, который отображает рукописные данные на поверхности, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>.  Всякий раз, когда для содержимого требуется поведение справа налево, имитирующее поведение слева направо, или наоборот, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет эту возможность.  
  
<a name="NumberSubstitution"></a>   
## Подстановка чисел  
 Исторически [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] поддерживало замену чисел посредством возможности представления различных культурных фигур для одних цифр во время сохранения внутреннего хранения этих цифр, объединенных среди различных местных специфик, например, числа хранятся в хорошо известном шестнадцатеричном формате, 0x40, 0x41, но отображаются на экране согласно выбранному языку.  
  
 Это позволяет приложениям вырабатывать цифровые величины без необходимости их конвертации из одного языка в другой, например пользователь может открыть электронную таблицу [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] на местном арабском языке [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и видеть числа, принявшие арабскую форму, однако откройте их в европейской версии [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и увидите европейское исполнение тех же чисел.  Это также необходимо для других символов, таких как разделительные запятые и символ процента, так как они обычно сопровождают числа в одном документе.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] продолжает ту же традицию и добавляет последующую поддержку для этого средства, позволяющего пользовательскому элементу управления контролировать когда и как используется замена.  Пока эта возможность сконструирована для любого языка, она особенно полезна в двунаправленном содержимом, в котором вид цифр для специфического языка обычно представляет проблему для разработчиков приложений, потому что приложение может натолкнуться на различные языки и региональные параметры.  
  
 Основным свойством, контролирующем число работающих замен в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], является свойство зависимости <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>.  Класс <xref:System.Windows.Media.NumberSubstitution> определяет как отображаются на экране числа в тексте.  Он имеет три общих свойств, определяющих его поведение.  Ниже приведен краткий обзор каждого из свойств.  
  
 **CultureSource:**  
  
 Данное свойство задает, как определяется язык и региональные параметры для чисел.  Оно принимает одно из трех значений перечисления <xref:System.Windows.Media.NumberCultureSource>.  
  
-   Переопределение номера языка и региональных параметров является свойство <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A>.  
  
-   Текст номера языка и региональных параметров — это язык и региональные параметры выполнения текста.  В разметке это может быть `xml:lang` или его псевдоним — свойство `Language` \(<xref:System.Windows.FrameworkElement.Language%2A> или <xref:System.Windows.FrameworkContentElement.Language%2A>\).  Кроме того, он используется по умолчанию для классов, производных от <xref:System.Windows.FrameworkContentElement>.  Такие классы содержат <xref:System.Windows.Documents.Paragraph?displayProperty=fullName>, <xref:System.Windows.Documents.Table?displayProperty=fullName>, <xref:System.Windows.Documents.TableCell?displayProperty=fullName> и так далее.  
  
-   Номер языка и региональных параметров пользователя — это язык и региональные параметры текущего потока.  Это свойство используется по умолчанию для всех подклассов <xref:System.Windows.FrameworkElement>, таких как <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> и <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**:  
  
 Свойство <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> используется только если свойство <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> задано равным <xref:System.Windows.Media.NumberCultureSource>, а в противном случае игнорируется.  Оно определяет язык и региональные параметры числа.  Значение `null`, значение по умолчанию интерпретируются как en\-US.  
  
 **Substitution**:  
  
 Это свойство задает тип замены числа на выполнение.  Оно принимает одно из следующих значений перечисления <xref:System.Windows.Media.NumberSubstitutionMethod>.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>. Метод замены определяется на основе свойства <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=fullName> языка и региональных параметров числа.  Это значение по умолчанию.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>. Если язык и региональные параметры числа являются арабскими или персидскими, они указывают, что цифры зависят от контекста.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>. Числа всегда отображаются как европейские цифры.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>. Числа отображаются с использованием национальных цифр языка и региональных параметров числа, как задано свойством <xref:System.Globalization.CultureInfo.NumberFormat%2A> языка и региональных параметров.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>. Числа отображаются с использованием традиционных цифр для языка и региональных параметров числа.  Для большинства языков и региональных параметров это то же самое, что <xref:System.Windows.Media.NumberSubstitutionMethod>.  Однако для некоторых арабских языков и региональных параметров значение <xref:System.Windows.Media.NumberSubstitutionMethod> дает результат в виде латинских цифр, тогда как значение Traditional дает результат в арабских цифрах для всех арабских языков и региональных параметров.  
  
 Что означают эти значения для разработчика двунаправленного содержимого?  В большинстве случаев разработчикам может потребоваться определить только <xref:System.Windows.FlowDirection> и язык каждого текстового элемента, включенного в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], например `Language="ar-SA"`, и тогда логика <xref:System.Windows.Media.NumberSubstitution> будет отвечать за отображение чисел на экране, как того требует [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  В следующем примере демонстрируется использование арабских и английских чисел в приложении [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], выполняющемся в арабской версии [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-xml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 На следующем рисунке показан результат предыдущего примера при выполнении в арабской версии [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 **Пример отображения на экране арабских и английских чисел**  
  
 ![Снимок экрана XamlPad с числами](../../../../docs/framework/wpf/advanced/media/numbers.png "Numbers")  
  
 <xref:System.Windows.FlowDirection> был важен в этом случае, так как если вместо него задать <xref:System.Windows.FlowDirection> как <xref:System.Windows.FlowDirection>, то будут появляться европейские цифры.  В следующих разделах обсуждаются способы получения единого отображения цифр на экране для всего документа.  Если этот пример не выполняется на арабской Windows, все цифры отображаться на экране как европейские цифры.  
  
 **Определение правил замены**  
  
 В реальном приложении может потребоваться установить язык программными средствами.  Например, требуется задать атрибут `xml:lang` так, чтобы он совпадал с атрибутом, который использует системный [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], или, возможно, требуется изменять язык в зависимости от состояния приложения.  
  
 Если требуется внести изменения на основании состояния приложения, проверьте использование других возможностей, предоставляемых [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Сначала установите `NumberSubstitution.CultureSource="Text"` компонента приложения.  Использование этого параметра гарантирует, что источником параметров для элементов текста, имеющих значение "User" по умолчанию, таких как <xref:System.Windows.Controls.TextBlock>, будет не [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Примеры.  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 В соответствующем коде [!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)] присвойте свойству `Language`, например, значение `"ar-SA"`.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 Если необходимо задать для свойства `Language` язык, который имеет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] текущего пользователя, используйте следующий код.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> предоставляет текущие язык и региональные параметры, используемые текущим потоком во время выполнения.  
  
 Окончательный пример [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] должен быть подобен нижеследующему примеру.  
  
 [!code-xml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Окончательный пример [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] должен быть подобен нижеследующему примеру.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 На следующем рисунке показано как выглядит окно для любого языка программирования.  
  
 **Пример отображения на экране арабских чисел**  
  
 ![Арабские числа](../../../../docs/framework/wpf/advanced/media/numbers2.png "Numbers2")  
  
 **Использование свойства замены**  
  
 Способ работы замены числа в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] зависит и от языка элемента текста и от его <xref:System.Windows.FlowDirection>.  Если <xref:System.Windows.FlowDirection> установлено слева направо, то отображаются европейские цифры.  Однако, если ему предшествует арабский текст, или задан язык "ar" и <xref:System.Windows.FlowDirection> имеет значение <xref:System.Windows.FlowDirection>, отображаются арабские цифры.  
  
 Тем не менее, в некоторых случаях может потребоваться создание единого приложения, например европейских цифр для всех пользователей.  Или арабские цифры в ячейках <xref:System.Windows.Documents.Table> с определенным <xref:System.Windows.Style>.  Просто способ добиться этого заключается в использовании свойства <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>.  
  
 В следующем примере, первый <xref:System.Windows.Controls.TextBlock> не имеет установленного свойства <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>, поэтому, как и ожидается, алгоритм отображает на экране арабские цифры.  Однако, во второй <xref:System.Windows.Controls.TextBlock>, замена задана как европейская, что переопределяет замену по умолчанию для арабских чисел, и на экране отображаются европейские цифры.  
  
 [!code-xml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]