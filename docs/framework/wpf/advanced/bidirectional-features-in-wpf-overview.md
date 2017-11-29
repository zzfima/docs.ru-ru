---
title: "Общие сведения о двусторонних возможностях в WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 716774efdf62356c2e3253c588dabb51de74470c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="bidirectional-features-in-wpf-overview"></a>Общие сведения о двусторонних возможностях в WPF
В отличие от любых других платформ разработки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеет множество функций, поддерживающих быструю разработку двунаправленного содержимого, например, смешанных слева направо и справа оставить данные в одном документе. В то же время [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отличный опыт, для пользователей, которым необходимы двунаправленные возможности, например арабский или иврит произношения пользователей.  
  
 В следующих разделах описаны различные возможности двунаправленного письма с примерами, иллюстрирующими способы достижения наилучшего отображения двунаправленного содержимого на экране. В большинстве примеров используется [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], хотя можно легко применить концепции [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] или [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] кода.  
  

  
<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 Основные свойство, которое определяет направление потока содержимого в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Это свойство может быть присвоено одно из двух значений перечисления, <xref:System.Windows.FlowDirection.LeftToRight> или <xref:System.Windows.FlowDirection.RightToLeft>. Это свойство доступно для всех [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы, которые наследуют от <xref:System.Windows.FrameworkElement>.  
  
 В следующем примере задается направление потока <xref:System.Windows.Controls.TextBox> элемента.  
  
 **Направление потока слева направо**  
  
 [!code-xaml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Направление потока справа налево**  
  
 [!code-xaml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 На следующем рисунке показано, как работает указанный код.  
  
 **Рисунок, иллюстрирующий направление потока**  
  
 ![Выравнивание блока текста](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.PNG "Слева направо Справа налево")  
  
 Элемент в пределах [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] дерева будут наследовать <xref:System.Windows.FrameworkElement.FlowDirection%2A> из контейнера. В следующем примере <xref:System.Windows.Controls.TextBlock> находится внутри <xref:System.Windows.Controls.Grid>, который находится в <xref:System.Windows.Window>. Установка <xref:System.Windows.FrameworkElement.FlowDirection%2A> для <xref:System.Windows.Window> подразумевает его для задание <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.TextBlock> также.  
  
 В следующем примере показано задание <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 [!code-xaml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 Верхний уровень <xref:System.Windows.Window> имеет <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>, поэтому все элементы, содержащиеся в нем, наследуют то же <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Для элемента переопределить заданное <xref:System.Windows.FrameworkElement.FlowDirection%2A> его необходимо добавить явное изменение направления например второй <xref:System.Windows.Controls.TextBlock> в предыдущем примере, который изменяется на <xref:System.Windows.FlowDirection.LeftToRight>. Если аргумент <xref:System.Windows.FrameworkElement.FlowDirection%2A> определена, значение по умолчанию <xref:System.Windows.FlowDirection.LeftToRight> применяется.  
  
 На следующем рисунке показан результат выполнения предыдущего примера.  
  
 **Рисунок, иллюстрирующий явное определение направления потока**  
  
 ![Иллюстрация направления потока](../../../../docs/framework/wpf/advanced/media/flowdir.PNG "Направление потока")  
  
<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Многие платформы разработки, такие как [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] и Java, обеспечивают специальную поддержку развития двунаправленного содержимого. Языки разметки, таких как [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] предоставляют редакторы записи необходимой разметки для отображения текста в любом требуемом направлении, например [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0 тег, «dir», которая принимает в качестве значения «rtl» или «ltr». Этот тег аналогичен <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойства, но <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойство работает более сложные, к текстовому содержимому макета и может использоваться для содержимого, отличное от текста.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Documents.FlowDocument> является универсальным [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элемент, который может содержать сочетание текста, таблицы, изображения и другие элементы. Этот элемент используется в примерах, описанных ниже.  
  
 Добавление текста к <xref:System.Windows.Documents.FlowDocument> можно сделать более таким образом один. Простой способ сделать это — через <xref:System.Windows.Documents.Paragraph> которого является элемент уровня блока, используемый для группировки содержимого, такие как текст. Добавление текста в элементы встроенного уровня, примеры используют <xref:System.Windows.Documents.Span> и <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span>Представляет элемент содержимого потока встроенного уровня, используемые для группировки других встроенных элементов, пока <xref:System.Windows.Documents.Run> — элемент предназначен для содержания цепочки неформатированного текста содержимого потока встроенного уровня. Объект <xref:System.Windows.Documents.Span> может содержать несколько <xref:System.Windows.Documents.Run> элементов.  
  
 Первый пример документа содержит документ, который имеет несколько сетевых совместно используемых имен; например `\\server1\folder\file.ext`. Независимо от того на каком языке написан документ, в котором содержится эта сетевая ссылка, на арабском или английском, нам хотелось бы, чтобы он выглядел всегда одинаково. Приведенный ниже рисунок показывает ссылку в арабском <xref:System.Windows.FlowDirection.RightToLeft> документа.  
  
 **Рисунок, иллюстрирующий использование элемента Span**  
  
 ![Документ с направлением потока справа налево](../../../../docs/framework/wpf/advanced/media/flowdocument.PNG "FlowDocument")  
  
 Поскольку текст <xref:System.Windows.FlowDirection.RightToLeft>, все специальные знаки, такие как «\\», разделяют текст справа налево. Приводит ссылки не отображаются в правильном порядке, таким образом устранить неполадки, текст должен быть включен для сохранения отдельного <xref:System.Windows.Documents.Run> передачи <xref:System.Windows.FlowDirection.LeftToRight>. Вместо того, отдельные <xref:System.Windows.Documents.Run> для каждого языка, более эффективный способ устранить неполадки является внедрение менее часто используемый текст на английском языке в больших арабский <xref:System.Windows.Documents.Span>.  
  
 Следующий рисунок иллюстрирует это.  
  
 **Пример использования элемента Run, внедренного в элемент Span**  
  
 ![Снимок экрана XamlPad](../../../../docs/framework/wpf/advanced/media/runspan.PNG "RunSpan")  
  
 В следующем примере показано использование <xref:System.Windows.Documents.Run> и <xref:System.Windows.Documents.Span> элементов в документах.  
  
 [!code-xaml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Элементы Span  
 <xref:System.Windows.Documents.Span> Элемент работает как разделитель границ между тексты с различными направлениями потоков.  Даже <xref:System.Windows.Documents.Span> элементы с тем же направлением потока, рассматриваются как имеющие различные двунаправленные области, т. е., <xref:System.Windows.Documents.Span> упорядочены элементы в контейнере <xref:System.Windows.FlowDirection>, только содержимое в <xref:System.Windows.Documents.Span> элемент соответствует <xref:System.Windows.FlowDirection> из <xref:System.Windows.Documents.Span>.  
  
 Приведенный ниже рисунок показывает направление потока нескольких <xref:System.Windows.Controls.TextBlock> элементов.  
  
 **Рисунок, иллюстрирующий направление потока в нескольких элементах TextBlock**  
  
 ![Текстовые блоки с различными направлениями потоков](../../../../docs/framework/wpf/advanced/media/span.PNG "Span")  
  
 В следующем примере показано, как использовать <xref:System.Windows.Documents.Span> и <xref:System.Windows.Documents.Run> элементы для получения результатов, показанный на предыдущем рисунке.  
  
 [!code-xaml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 В <xref:System.Windows.Controls.TextBlock> элементы в образце <xref:System.Windows.Documents.Span> элементы располагаются в соответствии с <xref:System.Windows.FlowDirection> их родительских объектов, но текст внутри каждого <xref:System.Windows.Documents.Span> элемент располагается согласно своему собственному <xref:System.Windows.FlowDirection>. Это применимо для латинского, арабского или любого другого языка.  
  
### <a name="adding-xmllang"></a>Добавление XML: lang  
 На следующем рисунке показан другой пример, использующий номера и арифметические выражения, такие как `"200.0+21.4=221.4"`. Обратите внимание, что только <xref:System.Windows.FlowDirection> имеет значение.  
  
 **Рисунок, иллюстрирующий отображение чисел только в направлении FlowDirection**  
  
 ![Числа с направлением потока справа налево](../../../../docs/framework/wpf/advanced/media/langattribute.PNG "LangAttribute")  
  
 Пользователи данного приложения будут разочарованы выходных данных, даже если <xref:System.Windows.FlowDirection> правильно числа не становятся арабскими цифрами должно иметь форму.  
  
 Элементы XAML могут включать [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] атрибут (`xml:lang`), определяющий язык каждого элемента. XAML также поддерживает [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] принцип языка при котором `xml:lang` дочерними элементами используются значения, примененные к родительским элементам в дереве. В предыдущем примере поскольку язык не был определен для <xref:System.Windows.Documents.Run> элементов, значение по умолчанию уровня элемента или любого из его верхней `xml:lang` использовался, являющийся `en-US` для XAML. Внутренний номер алгоритм из [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] выбирает числа в соответствующем языке, в данном случае английский. Делать арабские цифры отрисовки правильно `xml:lang` должно быть задано.  
  
 На следующем рисунке показан пример с `xml:lang` добавлен.  
  
 **Рисунок, иллюстрирующий использование атрибута xml:lang**  
  
 ![Арабские числа с направлением потока справа налево](../../../../docs/framework/wpf/advanced/media/langattribute2.PNG "LangAttribute2")  
  
 В следующем примере добавляется `xml:lang` в приложение.  
  
 [!code-xaml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Имейте в виду, что многие языки имеют различные `xml:lang` значения в зависимости от целевого региона, например, `"ar-SA"` и `"ar-EG"` представляют собой два диалекта арабского языка. В предыдущих примерах показано, что необходимо определить оба `xml:lang` и <xref:System.Windows.FlowDirection> значения.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>Направление потока применительно к нетекстовым элементам  
 <xref:System.Windows.FlowDirection>Определяет не только как текст проходит в текстовом элементе, но также направление потока практически любого другого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элемента. Показано на следующем рисунке <xref:System.Windows.Controls.ToolBar> , использующий горизонтальной <xref:System.Windows.Media.LinearGradientBrush> для рисования фона его.  
  
 **Рисунок, показывающий элемент ToolBar с градиентом слева направо**  
  
 ![Снимок экрана градиента](../../../../docs/framework/wpf/advanced/media/gradient.PNG "Gradient")  
  
 После установки параметра <xref:System.Windows.FlowDirection> для <xref:System.Windows.FlowDirection.RightToLeft>, не только <xref:System.Windows.Controls.ToolBar> кнопок, расположенных справа налево, но даже <xref:System.Windows.Media.LinearGradientBrush> перестраивает свои смещения для потока справа налево.  
  
 На следующем рисунке показан перестройку <xref:System.Windows.Media.LinearGradientBrush>.  
  
 **Рисунок, показывающий элемент ToolBar с градиентом справа налево**  
  
 ![Градиент с направлением справа налево](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.PNG "Gradient2_WPF")  
  
 В следующем примере рисуется <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>. (Он расположен слева направо, удалите <xref:System.Windows.FlowDirection> атрибут <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>Исключения направления потока  
 Существует несколько вариантов где <xref:System.Windows.FlowDirection> вести себя неожиданным образом. В этом разделе рассматриваются два таких исключения.  
  
 **Изображение**  
  
 <xref:System.Windows.Controls.Image> Представляет элемент управления, отображающий изображение. В [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] может использоваться с <xref:System.Windows.Controls.Image.Source%2A> свойство, определяющее [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] из <xref:System.Windows.Controls.Image> для отображения.  
  
 В отличие от других [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов, <xref:System.Windows.Controls.Image> не наследует <xref:System.Windows.FlowDirection> из контейнера. Однако если <xref:System.Windows.FlowDirection> явно присвоено значение <xref:System.Windows.FlowDirection.RightToLeft>, <xref:System.Windows.Controls.Image> отображается зеркально по горизонтали. Это сделано для удобства разработчиков двунаправленного содержимого. В некоторых случаях горизонтальным отражением достигается требуемый эффект.  
  
 На следующем рисунке показан отраженных <xref:System.Windows.Controls.Image>.  
  
 **Рисунок, иллюстрирующий перевернутое изображение**  
  
 ![Снимок экрана XamlPad](../../../../docs/framework/wpf/advanced/media/image.PNG "Image")  
  
 В следующем примере показано, что <xref:System.Windows.Controls.Image> не удается наследовать <xref:System.Windows.FlowDirection> из <xref:System.Windows.Controls.StackPanel> , которая его содержит. **Примечание** необходимо иметь файл с именем **ms_logo.jpg** на диске C:\ для запуска этого примера.  
  
 [!code-xaml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Примечание** включенные в состав загружаемых файлов является **ms_logo.jpg** файла. В коде предполагается, что JPG-файл находится не внутри проекта, а где-нибудь на диске C:\. Необходимо скопировать JPG-файл из файлов проекта на диск C:\ или изменить код так, чтобы выполнялся поиск файла внутри проекта. Для этого перейдите `Source="file://c:/ms_logo.jpg"` для `Source="ms_logo.jpg"`.  
  
 **Paths**  
  
 В дополнение к <xref:System.Windows.Controls.Image>, другим интересным элементом является <xref:System.Windows.Shapes.Path>. Контур — это объект, который может нарисовать последовательность соединенных линий и кривых. Он ведет себя так же, как <xref:System.Windows.Controls.Image> относительно его <xref:System.Windows.FlowDirection>, например его <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> является отражением относительно горизонтали его <xref:System.Windows.FlowDirection.LeftToRight> одно. Однако в отличие от <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> наследует его <xref:System.Windows.FlowDirection> из контейнера и не требуется указывать явно.  
  
 В следующем примере рисуется простая стрелка, использующая три линии. Первая стрелка наследует <xref:System.Windows.FlowDirection.RightToLeft> направление из потока <xref:System.Windows.Controls.StackPanel> , чтобы его начальную и конечную точки отсчитываются от корня справа от оператора. Вторая стрелка, имеющая явно <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> также запускается с правой стороны. Однако третья стрелка начинается от корня с левой стороны. Дополнительные сведения о рисовании содержатся <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xaml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 На следующем рисунке показан результат выполнения предыдущего примера.  
  
 **Рисунок, иллюстрирующий стрелки, нарисованные с помощью элемента Path**  
  
 ![Paths](../../../../docs/framework/wpf/advanced/media/paths.PNG "Paths")  
  
 <xref:System.Windows.Controls.Image> И <xref:System.Windows.Shapes.Path> представлены два примера того, как [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] использует <xref:System.Windows.FlowDirection>. Рядом с макетом [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов в определенном направлении внутри контейнера, <xref:System.Windows.FlowDirection> можно использовать с элементами, такие как <xref:System.Windows.Controls.InkPresenter> отображаемое штриха на поверхности, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>. Каждый раз, когда требуется поведение справа налево для содержимого, которая имитирует поведение слева направо, или наоборот, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет эту возможность.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Подстановки чисел  
 Исторически [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] поддерживало замену чисел посредством возможности представления различных культурных фигур для одних цифр во время сохранения внутреннего хранения этих цифр, объединенных среди различных языковых стандартах, например, числа хранятся в их хорошо известных шестнадцатеричных значений, 0x40, 0x41, но отображаются в зависимости от выбранного языка.  
  
 Это позволяет приложениям для обработки числовых значений, без необходимости преобразовывать их с одного языка на другой, например пользователь может открыть [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] электронной таблицы в локализованных арабский [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] просмотра номеров, которые были сформированы на арабском языке и откройте его в Европейской версии [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и просмотреть европейских представление и те же номера. Это также необходимо для других символов, например запятая или символ процента, так как они обычно сопровождают числа в одном документе.  
  
 Платформа [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] продолжает эту традицию и добавляет новые возможности, позволяющие пользователю более точно определять, когда и как должна применяться подстановка. Эта функция может использоваться со всеми языками, но особенно полезна она в обработке двунаправленного содержимого, когда представление чисел для разных региональных стандартов становится проблемой для разработчиков приложений, предназначенных для использования в разных странах.  
  
 Свойство core, управляющее подстановки как чисел работает в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] — <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> свойства зависимостей. <xref:System.Windows.Media.NumberSubstitution> Класс указывает, как должны отображаться числа в тексте. Он имеет три открытых свойства, определяющих его поведение. Ниже приведен краткий обзор каждого из свойств.  
  
 **CultureSource.**  
  
 Это свойство задает способ определения регионального стандарта для чисел. Оно принимает одно из трех <xref:System.Windows.Media.NumberCultureSource> значений перечисления.  
  
-   Переопределение: Номер языка и региональных параметров, представляет <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> свойство.  
  
-   Text (текст). Региональный стандарт для чисел определяется по региональному стандарту фрагмента текста. В разметке, это будет `xml:lang`, или ее псевдоним `Language` свойство (<xref:System.Windows.FrameworkElement.Language%2A> или <xref:System.Windows.FrameworkContentElement.Language%2A>). Кроме того, это значение по умолчанию для классов, производных от <xref:System.Windows.FrameworkContentElement>. Такие классы содержат <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> и т. д.  
  
-   User (пользователь). Региональный стандарт для чисел определяется по региональному стандарту текущего потока. Это свойство имеет значение по умолчанию для всех подклассов <xref:System.Windows.FrameworkElement> например <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> и <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**.  
  
 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> Свойство используется только в том случае, если <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> свойству <xref:System.Windows.Media.NumberCultureSource.Override> , а в противном случае значение игнорируется. Оно определяет региональный стандарт для чисел. Значение `null`, значение по умолчанию, интерпретируется как en US.  
  
 **Substitution**.  
  
 Это свойство определяет выполняемый тип подстановки чисел. Оно принимает одно из следующих <xref:System.Windows.Media.NumberSubstitutionMethod> значений перечисления.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: Метод подстановки определяется на основе номеров культуры <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> свойство. Это значение по умолчанию.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Если номера языка и региональных параметров, арабского или персидский языка и региональных параметров, он указывает, что цифры зависят от контекста.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.European>: Числа всегда отображаются как европейские цифры.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Числа отображаются с использованием национальных цифр номера языка и региональных параметров в соответствии с языком и региональными параметрами <xref:System.Globalization.CultureInfo.NumberFormat%2A>.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Числа отображаются с использованием традиционных цифр номера языком и региональными параметрами. Для большинства языков и региональных параметров, то же самое происходит <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Однако <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> приводит к цифры для некоторых арабского языка и региональных параметров, а это значение приводит к арабские цифры арабского языка и региональных параметров.  
  
 О чем говорят эти значения разработчикам двунаправленного содержимого? В большинстве случаев разработчик может потребоваться определить только <xref:System.Windows.FlowDirection> и язык каждое текстовое [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элемент, например `Language="ar-SA"` и <xref:System.Windows.Media.NumberSubstitution> логику отвечает за отображение номера в соответствии с правильного [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. В следующем примере показано использование английского и арабского чисел в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложение, работающее в арабском версии [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-xaml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 На следующем рисунке показан результат предыдущего примера при выполнении в арабском версии [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 **Рисунок, иллюстрирующий отображение арабских и английских чисел**  
  
 ![Снимок экрана XamlPad с числами](../../../../docs/framework/wpf/advanced/media/numbers.PNG "Numbers")  
  
 <xref:System.Windows.FlowDirection> Был важные в этом случае, так как задание <xref:System.Windows.FlowDirection> для <xref:System.Windows.FlowDirection.LeftToRight> вместо этого будет появляться европейские цифры. В следующих разделах рассматривается, как сделать одинаковое отображение цифр по всему документу. Если этот пример не выполняется на арабской версии Windows, все цифры отображаются на экране как европейские цифры.  
  
 **Определение правил подстановки**  
  
 В реальном приложении может возникнуть необходимость установить язык программным путем. Например, вы хотите установить `xml:lang` атрибут, который будет таким же, как используемое в системе [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], или возможно требуется изменить язык в зависимости от состояния приложения.  
  
 Если вы хотите внести изменения на основании состояния приложения, убедитесь, использование других возможностей, предоставляемых [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Во-первых, следует установить компонент приложения `NumberSubstitution.CultureSource="Text"`. Использование этого параметра гарантирует, что параметры не исходят из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для текстовых элементов, содержащих «User» по умолчанию, таких как <xref:System.Windows.Controls.TextBlock>.  
  
 Пример:  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 В соответствующем [!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)] кода, задайте `Language` свойство так, чтобы `"ar-SA"`.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 Если необходимо задать `Language` свойство текущему пользователю [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] языка с помощью следующего кода.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A>представляет текущий язык и региональные параметры, используемые текущим потоком во время выполнения.  
  
 Окончательный [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] примере должен выглядеть следующим образом.  
  
 [!code-xaml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Окончательный [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] пример должен быть подобен следующему.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 На следующем рисунке показано, как выглядит окно для каждого языка программирования.  
  
 **Рисунок, иллюстрирующий арабские числа**  
  
 ![Арабские числа](../../../../docs/framework/wpf/advanced/media/numbers2.PNG "Numbers2")  
  
 **Использование свойства подстановки**  
  
 Способ работы замены числа [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] зависит от языка текста элемента и его <xref:System.Windows.FlowDirection>. Если <xref:System.Windows.FlowDirection> слева направо, то отображаются европейские цифры. Однако если ему предшествует арабский текст или задан язык «ar» и <xref:System.Windows.FlowDirection> — <xref:System.Windows.FlowDirection.RightToLeft>, отображаются арабские цифры.  
  
 В некоторых случаях может потребоваться создание универсального приложения, например с европейскими цифрами для всех пользователей. Или арабские цифры в <xref:System.Windows.Documents.Table> ячеек с определенным <xref:System.Windows.Style>. Один простой способ выполнения которой используется <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> свойство.  
  
 В следующем примере первый <xref:System.Windows.Controls.TextBlock> не имеет <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> свойство задано, поэтому алгоритм будет отображаться арабские цифры должным образом. Однако во втором <xref:System.Windows.Controls.TextBlock>, подстановка задана как европейская переопределяет замену по умолчанию для арабских цифр и отображаются европейские цифры.  
  
 [!code-xaml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
