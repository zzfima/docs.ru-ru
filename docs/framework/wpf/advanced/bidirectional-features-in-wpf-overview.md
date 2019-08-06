---
title: Общие сведения о двусторонних возможностях в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: d2b35a50d9d09bffd69ae8b8217d6e778ce66ea0
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796400"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Общие сведения о двусторонних возможностях в WPF
В отличие от любой другой платформы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] разработки имеет множество функций, поддерживающих быструю разработку двунаправленного содержимого, например смешанные данные слева направо и справа налево в одном документе. В то же время [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создает прекрасную работу для пользователей, которым требуются двунаправленные функции, такие как арабский и иврит.  
  
 В следующих разделах описаны различные возможности двунаправленного письма с примерами, иллюстрирующими способы достижения наилучшего отображения двунаправленного содержимого на экране. В большинстве примеров используется [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], но вы можете легко применить основные понятия C# или Microsoft Visual Basicный код.  

<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 Базовое свойство, определяющее направление потока содержимого в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении, —. <xref:System.Windows.FrameworkElement.FlowDirection%2A> Этому свойству можно присвоить одно из двух значений <xref:System.Windows.FlowDirection.LeftToRight> перечисления или. <xref:System.Windows.FlowDirection.RightToLeft> Свойство доступно для всех [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов, которые наследуют от. <xref:System.Windows.FrameworkElement>  
  
 В следующих примерах задается направление <xref:System.Windows.Controls.TextBox> потока элемента.  
  
 **Направление потока слева направо**  
  
 [!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Направление потока справа налево**  
  
 [!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 На следующем рисунке показано, как работает указанный код.  
    
 ![Рисунок, иллюстрирующий различные направления потока.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)  
  
 Элемент в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] дереве будет <xref:System.Windows.FrameworkElement.FlowDirection%2A> наследовать от своего контейнера. В следующем примере объект <xref:System.Windows.Controls.TextBlock> находится внутри элемента <xref:System.Windows.Controls.Grid>, который находится в <xref:System.Windows.Window>. <xref:System.Windows.FrameworkElement.FlowDirection%2A> Установка <xref:System.Windows.Controls.TextBlock> для для параметра<xref:System.Windows.Controls.Grid> предполагает также установку для и. <xref:System.Windows.Window>  
  
 В следующем примере демонстрируется <xref:System.Windows.FrameworkElement.FlowDirection%2A>Настройка.  
  
 [!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 <xref:System.Windows.Window> Верхний уровень <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FrameworkElement.FlowDirection%2A>имеет, поэтому все элементы, содержащиеся в нем, также наследуют один и тот же. <xref:System.Windows.FlowDirection> Чтобы элемент переопределял заданный <xref:System.Windows.FrameworkElement.FlowDirection%2A> объект, необходимо добавить явное изменение направления, например второе <xref:System.Windows.Controls.TextBlock> в предыдущем примере, которое изменяется на <xref:System.Windows.FlowDirection.LeftToRight>. Если значение <xref:System.Windows.FrameworkElement.FlowDirection%2A> не определено, применяется <xref:System.Windows.FlowDirection.LeftToRight> значение по умолчанию.  
  
 На следующем рисунке показаны выходные данные предыдущего примера.

 ![Рисунок, иллюстрирующий явное изменение направления потока.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)  

<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Многие платформы разработки, такие как HTML [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] и Java, предоставляют специальную поддержку для разработки двунаправленного содержимого. Языки разметки, такие как HTML, предоставляют авторам содержимого необходимую разметку для вывода текста в любом требуемом направлении, например HTML 4,0, «dir», который принимает значения «RTL» или «LTR» в качестве значений. Этот тег аналогичен <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойству, <xref:System.Windows.FrameworkElement.FlowDirection%2A> но свойство работает более продвинутым способом для разметки текстового содержимого и может использоваться для содержимого, отличного от Text.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]службах [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] — это универсальный элемент, который может содержать сочетание текста, таблиц, изображений и других элементов. <xref:System.Windows.Documents.FlowDocument> Этот элемент используется в примерах, описанных ниже.  
  
 Добавление текста в <xref:System.Windows.Documents.FlowDocument> может выполняться несколькими способами. Простой способ сделать это — <xref:System.Windows.Documents.Paragraph> использовать элемент уровня блока, используемый для группировки содержимого, например текста. Чтобы добавить текст в элементы встроенного уровня, в примерах <xref:System.Windows.Documents.Span> используются <xref:System.Windows.Documents.Run>и. <xref:System.Windows.Documents.Span>— Это элемент содержимого потока встроенного уровня, используемый для группирования других встроенных элементов, а <xref:System.Windows.Documents.Run> — элемент содержимого потока встроенного уровня, предназначенный для хранения выполнения неформатированного текста. Может содержать несколько <xref:System.Windows.Documents.Run>элементов. <xref:System.Windows.Documents.Span>  
  
 В первом примере документа содержится документ с числом имен общих сетевых ресурсов. например `\\server1\folder\file.ext`,. Независимо от того на каком языке написан документ, в котором содержится эта сетевая ссылка, на арабском или английском, нам хотелось бы, чтобы он выглядел всегда одинаково. На следующем рисунке показано использование элемента Span и отображение ссылки в документе на арабском языке <xref:System.Windows.FlowDirection.RightToLeft> :

 ![Рисунок, демонстрирующий использование элемента Span.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")  
  
 Поскольку текст имеет значение <xref:System.Windows.FlowDirection.RightToLeft>, все специальные символы, такие как\\«», разделяют текст в порядке справа налево. Это приводит к отображению ссылки в правильном порядке, поэтому для устранения проблемы текст должен быть внедрен, чтобы сохранить отдельное <xref:System.Windows.Documents.Run> перетекание. <xref:System.Windows.FlowDirection.LeftToRight> Вместо того чтобы разделять <xref:System.Windows.Documents.Run> для каждого языка, лучшим способом решить эту проблему является внедрение менее часто используемого текста на английском языке в более крупный арабский. <xref:System.Windows.Documents.Span>  
  
 На следующем рисунке показано, как использовать элемент Run, внедренный в элемент span:

 ![Рисунок, иллюстрирующий элемент Run, внедренный в элемент span.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)  
  
 В следующем примере демонстрируется <xref:System.Windows.Documents.Run> использование <xref:System.Windows.Documents.Span> элементов и в документах.  
  
 [!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Элементы Span  
 <xref:System.Windows.Documents.Span> Элемент работает как разделитель границ между текстами с различными направлениями потока.  Даже <xref:System.Windows.Documents.Span> элементы с одинаковым направлением потока считаются разными двунаправленными областями, то есть <xref:System.Windows.Documents.Span> элементы <xref:System.Windows.FlowDirection>упорядочиваются в контейнере, а только в содержимом внутри <xref:System.Windows.Documents.Span> элемента. <xref:System.Windows.FlowDirection> следует<xref:System.Windows.Documents.Span>за.  
  
 На следующем рисунке показано направление потока для нескольких <xref:System.Windows.Controls.TextBlock> элементов.  
    
 ![Рисунок, иллюстрирующий текстовые блоки с различными направлениями потока.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)  
  
 В следующем примере показано, как использовать <xref:System.Windows.Documents.Span> элементы и <xref:System.Windows.Documents.Run> для получения результатов, показанных на предыдущем рисунке.  
  
 [!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection> <xref:System.Windows.Documents.Span> В элементах в образце <xref:System.Windows.Documents.Span> элементы размещаются в соответствии с их родительскими элементами, но текст внутри каждого элемента передается в соответствии с собственными значениями. <xref:System.Windows.Controls.TextBlock> Это применимо для латинского, арабского или любого другого языка.  
  
### <a name="adding-xmllang"></a>Добавление XML: lang  
 На следующем рисунке показан еще один пример, использующий числа и арифметические `"200.0+21.4=221.4"`выражения, такие как. Обратите внимание, <xref:System.Windows.FlowDirection> что задан только параметр.  
    
 ![График, отображающий числа только с помощью FlowDirection.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)  
  
 Пользователи этого приложения будут разочарованы выходными данными, <xref:System.Windows.FlowDirection> несмотря на то, что верные числа не образуют арабских цифр.  
  
 Элементы XAML могут включать [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] атрибут (`xml:lang`), определяющий язык каждого элемента. XAML также поддерживает [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] принцип языка, при `xml:lang` котором значения, применяемые к родительским элементам в дереве, используются дочерними элементами. В предыдущем примере, поскольку язык не был определен для <xref:System.Windows.Documents.Run> элемента или какого-либо из его элементов верхнего уровня, используется значение по умолчанию `xml:lang` , которое относится `en-US` к XAML. Внутренний алгоритм [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] формирования чисел выбирает числа на соответствующем языке — в данном случае это английский язык. Чтобы арабские цифры отображались правильно `xml:lang` , необходимо установить.  
  
 На следующем рисунке показан пример с `xml:lang` добавлением.  
    
 ![Рисунок, иллюстрирующий арабские цифры, которые передаются справа налево.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)  
  
 В следующем примере добавляется `xml:lang` в приложение.  
  
 [!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Имейте в виду, что многие языки `xml:lang` имеют различные значения в зависимости от целевого региона, например, `"ar-SA"` и `"ar-EG"` представляют два варианта арабского языка. В предыдущих примерах показано, что необходимо определить `xml:lang` и значения, и. <xref:System.Windows.FlowDirection>  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>Направление потока применительно к нетекстовым элементам  
 <xref:System.Windows.FlowDirection>определяет не только то, как поток текста в текстовом элементе, но также направление потока почти для каждого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] другого элемента. На следующем рисунке показан объект <xref:System.Windows.Controls.ToolBar> , который использует горизонтальный <xref:System.Windows.Media.LinearGradientBrush> цвет для рисования фона с градиентом слева направо.  

 ![Рисунок, на котором показана панель инструментов с градиентом слева направо.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)  
  
 После присвоения <xref:System.Windows.FlowDirection> свойству <xref:System.Windows.FlowDirection.RightToLeft>значения не только <xref:System.Windows.Controls.ToolBar> кнопки упорядочиваются справа налево, но даже <xref:System.Windows.Media.LinearGradientBrush> переравниваются по смещению от правого к левому.  
  
 На следующем рисунке показано перевыравнивание <xref:System.Windows.Media.LinearGradientBrush>.  
    
 ![Рисунок, на котором показана панель инструментов с градиентом справа налево.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)  
  
 В следующем примере рисуется <xref:System.Windows.FlowDirection.RightToLeft>. <xref:System.Windows.Controls.ToolBar> (Чтобы нарисовать его слева направо, удалите <xref:System.Windows.FlowDirection> атрибут <xref:System.Windows.Controls.ToolBar>в.  
  
 [!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>Исключения направления потока  
 Существует несколько случаев, где <xref:System.Windows.FlowDirection> поведение не работает должным образом. В этом разделе рассматриваются два таких исключения.  
  
 **Изображение**  
  
 <xref:System.Windows.Controls.Image> Представляет элемент управления, который отображает изображение. В [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] нем можно использовать <xref:System.Windows.Controls.Image.Source%2A> [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] свойство<xref:System.Windows.Controls.Image> , определяющее отображаемый объект.  
  
 В отличие от [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] других элементов, <xref:System.Windows.Controls.Image> класс не наследует <xref:System.Windows.FlowDirection> от контейнера. Однако если <xref:System.Windows.FlowDirection> задано <xref:System.Windows.FlowDirection.RightToLeft>явное значение, <xref:System.Windows.Controls.Image> то отображается зеркально по горизонтали. Это сделано для удобства разработчиков двунаправленного содержимого. В некоторых случаях горизонтальным отражением достигается требуемый эффект.  
  
 На следующем рисунке показана зеркальная <xref:System.Windows.Controls.Image>схема.  
    
 ![Рисунок, иллюстрирующий перевернутое изображение.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)  
  
 В следующем примере показано, что <xref:System.Windows.Controls.Image> объект не может наследовать объект <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.FlowDirection> из, который содержит его. **Примечание** . Необходимо иметь файл с именем **ms_logo. jpg** в файле C:\ диск для выполнения этого примера.  
  
 [!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Примечание** . В файлы для загрузки входит файл **ms_logo. jpg** . В коде предполагается, что JPG-файл находится не внутри проекта, а где-нибудь на диске C:\. Необходимо скопировать JPG-файл из файлов проекта на диск C:\ или изменить код так, чтобы выполнялся поиск файла внутри проекта. Для этого измените `Source="file://c:/ms_logo.jpg"` значение на `Source="ms_logo.jpg"`.  
  
 **Paths**  
  
 В дополнение к <xref:System.Windows.Controls.Image>, еще один интересный элемент — <xref:System.Windows.Shapes.Path>. Контур — это объект, который может нарисовать последовательность соединенных линий и кривых. Он ведет себя так же, как и <xref:System.Windows.Controls.Image> в <xref:System.Windows.FlowDirection>отношении. например <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> , он является горизонтальным зеркалом <xref:System.Windows.FlowDirection.LeftToRight> . Однако, в отличие от <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> наследует его <xref:System.Windows.FlowDirection> от контейнера, и он не должен явно указывать его.  
  
 В следующем примере рисуется простая стрелка, использующая три линии. Первая стрелка наследует <xref:System.Windows.FlowDirection.RightToLeft> направление потока от, <xref:System.Windows.Controls.StackPanel> так что ее начальная и конечная точки измеряются от корня в правой части. Вторая стрелка, которая имеет явное <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> значение, также начинается с правой стороны. Однако третья стрелка начинается от корня с левой стороны. Дополнительные сведения о рисовании см <xref:System.Windows.Media.LineGeometry> . <xref:System.Windows.Media.GeometryGroup>в разделе и.  
  
 [!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 На следующем рисунке показаны выходные данные предыдущего примера со стрелками, `Path` рисуемыми с помощью элемента:

 ![Рисунок, иллюстрирующий стрелки, рисуемые с помощью элемента Path.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)  
  
 И — это два примера использования .<xref:System.Windows.FlowDirection> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Image> <xref:System.Windows.Shapes.Path> При размещении [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов в определенном направлении в <xref:System.Windows.FlowDirection> контейнере можно использовать элементы, такие как <xref:System.Windows.Controls.InkPresenter> отрисовка рукописного ввода на поверхности, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>. Если вам требуется поведение справа налево для содержимого, которое имитирует поведение слева направо, или наоборот, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет эту возможность.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Подстановки чисел  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Исторически поддерживали подстановку чисел, разрешая представление различных культурных форм для одних и тех же цифр и сохраняя внутреннее хранение этих цифр в унифицированных между разными языками, например числа хранятся в их хорошо известные шестнадцатеричные значения, 0x40, 0x41 влево, но отображаемые в соответствии с выбранным языком.  
  
 Это позволяло приложениям обрабатывать числовые значения без необходимости преобразования их из одного языка в другой, например пользователь может открыть [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] электронную таблицу на локализованном арабском языке [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и увидеть цифры на арабском языке, но открыть ее в европейские версии [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и видят европейские представления одних и тех же чисел. Это также необходимо для других символов, например запятая или символ процента, так как они обычно сопровождают числа в одном документе.  
  
 Платформа [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] продолжает эту традицию и добавляет новые возможности, позволяющие пользователю более точно определять, когда и как должна применяться подстановка. Эта функция может использоваться со всеми языками, но особенно полезна она в обработке двунаправленного содержимого, когда представление чисел для разных региональных стандартов становится проблемой для разработчиков приложений, предназначенных для использования в разных странах.  
  
 Основным свойством, определяющим [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> , как работает подстановка чисел, является свойство зависимостей. <xref:System.Windows.Media.NumberSubstitution> Класс определяет, как должны отображаться числа в тексте. Он имеет три открытых свойства, определяющих его поведение. Ниже приведен краткий обзор каждого из свойств.  
  
 **CultureSource.**  
  
 Это свойство задает способ определения регионального стандарта для чисел. Он принимает одно из трех <xref:System.Windows.Media.NumberCultureSource> значений перечисления.  
  
- Крывают Число языка и региональных параметров <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> — это свойство.  
  
- Полнотекстовым Число языка и региональных параметров — это культура текста. В разметке это может `xml:lang`быть, или его `Language` свойство Alias<xref:System.Windows.FrameworkElement.Language%2A> ( <xref:System.Windows.FrameworkContentElement.Language%2A>или). Кроме того, это значение по умолчанию для классов, <xref:System.Windows.FrameworkContentElement>производных от. К таким классам <xref:System.Windows.Documents.Table?displayProperty=nameWithType>относятся <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, и т. д.  
  
- Пользователь: Номер языка и региональных параметров текущего потока. Это свойство является значением <xref:System.Windows.FrameworkElement> по умолчанию для всех подклассов, таких как <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> и.  
  
 **CultureOverride**.  
  
 Свойство используется только в том <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> случае, если свойство имеет значение <xref:System.Windows.Media.NumberCultureSource.Override> и не учитывается в противном случае. <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> Оно определяет региональный стандарт для чисел. Значение `null`, значение по умолчанию, интерпретируется как en-US.  
  
 **Substitution**.  
  
 Это свойство определяет выполняемый тип подстановки чисел. Он принимает одно из следующих <xref:System.Windows.Media.NumberSubstitutionMethod> значений перечисления:  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: Метод подстановки определяется на основе <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> свойства Number языка и региональных параметров. Это значение по умолчанию.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Если язык и региональные параметры имеют арабский или Персидский язык, он указывает, что цифры зависят от контекста.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: Числа всегда отображаются в виде европейских цифр.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Числа отображаются с использованием национальных цифр для языка и региональных параметров числа, как указано в языке и <xref:System.Globalization.CultureInfo.NumberFormat%2A>региональных параметрах.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Числа отображаются с использованием традиционных цифр для языка и региональных параметров числа. Для большинства языков и региональных параметров это то же <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>самое, что. Однако в некоторых языках и региональных параметрах для арабского языка выводятсяцифрылатинскогоалфавита,тогдакакэтозначениедаетарабскиецифрыдлявсехязыковирегиональныхпараметров.<xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>  
  
 О чем говорят эти значения разработчикам двунаправленного содержимого? В большинстве <xref:System.Windows.FlowDirection> случаев разработчику может потребоваться только определить и язык для каждого текстового [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элемента <xref:System.Windows.Media.NumberSubstitution> , например `Language="ar-SA"` , и логика позаботится о том, чтобы отобразить числа в соответствии с правильным [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]значением. В следующем примере демонстрируется использование арабских и английских чисел [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] в приложении, работающем в Арабской [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]версии.  
  
 [!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 На следующем рисунке показаны выходные данные предыдущего примера, если вы работаете в арабской версии Windows с арабскими и англоязычными номерами.

 ![Рисунок, в котором показаны арабские и английские цифры.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)  
  
 В <xref:System.Windows.FlowDirection> этом случае имелось важное значение, так <xref:System.Windows.FlowDirection> как <xref:System.Windows.FlowDirection.LeftToRight> вместо этого при присвоении параметру значения будут выдаваться европейские цифры. В следующих разделах рассматривается, как сделать одинаковое отображение цифр по всему документу. Если этот пример не выполняется на арабской версии Windows, все цифры отображаются на экране как европейские цифры.  
  
 **Определение правил подстановки**  
  
 В реальном приложении может возникнуть необходимость установить язык программным путем. Например, необходимо установить `xml:lang` атрибут так, чтобы он совпадал с используемым [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]системой, или изменить язык в зависимости от состояния приложения.  
  
 Если вы хотите внести изменения в зависимости от состояния приложения, используйте другие функции, предоставляемые [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Сначала задайте компонент `NumberSubstitution.CultureSource="Text"`приложения. Использование этого параметра гарантирует, что параметры не поступают из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для текстовых элементов, которые имеют значение по умолчанию "User", <xref:System.Windows.Controls.TextBlock>например.  
  
Например:  

```xaml  
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

В соответствующем C# коде задайте `Language` для свойства, например `"ar-SA"`значение.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Если необходимо задать `Language` для свойства язык пользовательского интерфейса текущего пользователя, используйте следующий код.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>представляет текущий язык и региональные параметры, используемые текущим потоком во время выполнения.  
  
 Окончательный [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] пример должен быть подобен приведенному ниже примеру.  
  
 [!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Окончательный C# пример должен выглядеть следующим образом.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 На следующем рисунке показано, как выглядит окно для любого языка программирования, отображая арабские цифры:
     
 ![Рисунок, отображающий арабские цифры.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)  
  
 **Использование свойства подстановки**  
  
 Способ подстановки [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] чисел зависит от языка текстового элемента и его свойства <xref:System.Windows.FlowDirection>. <xref:System.Windows.FlowDirection> Если слева направо, то выводятся европейские цифры. Однако если перед ним стоит текст на арабском языке или для языка задано значение AR, а <xref:System.Windows.FlowDirection> — <xref:System.Windows.FlowDirection.RightToLeft>, то вместо этого выводятся арабские цифры.  
  
 В некоторых случаях может потребоваться создание универсального приложения, например с европейскими цифрами для всех пользователей. Или арабские цифры <xref:System.Windows.Documents.Table> в ячейках с <xref:System.Windows.Style>конкретным. Одним из простых способов является использование <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> свойства.  
  
 В следующем примере для первого <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> свойства не задано свойство, поэтому алгоритм отображает арабские цифры, как ожидалось. Однако во втором <xref:System.Windows.Controls.TextBlock>случае подстановка устанавливается в Европейский, переопределяющий подстановку по умолчанию для арабских чисел, и выводятся европейские цифры.  
  
 [!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
