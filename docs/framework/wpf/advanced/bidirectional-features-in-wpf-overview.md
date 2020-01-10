---
title: Общие сведения о двусторонних возможностях в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 19fb15a6310eba19792d7bd0744c2ae87f47c6fa
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740422"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Общие сведения о двусторонних возможностях в WPF

В отличие от любой другой платформы разработки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеет множество функций, поддерживающих быструю разработку двунаправленного содержимого, например, смешанные данные слева направо и справа налево в одном документе. В то же время [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создает отличное взаимодействие с пользователями, которым требуются двунаправленные функции, такие как арабский и иврит.

В следующих разделах описаны различные возможности двунаправленного письма с примерами, иллюстрирующими способы достижения наилучшего отображения двунаправленного содержимого на экране. В большинстве примеров используется XAML, но вы можете легко применить основные понятия C# или Microsoft Visual Basicный код.

<a name="FlowDirection"></a>

## <a name="flowdirection"></a>FlowDirection

Базовое свойство, определяющее направление потока содержимого в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении, — <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Этому свойству можно присвоить одно из двух значений перечисления: <xref:System.Windows.FlowDirection.LeftToRight> или <xref:System.Windows.FlowDirection.RightToLeft>. Свойство доступно для всех [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов, которые наследуют от <xref:System.Windows.FrameworkElement>.

В следующих примерах задается направление потока элемента <xref:System.Windows.Controls.TextBox>.

**Направление потока слева направо**

[!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]

**Направление потока справа налево**

[!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]

На следующем рисунке показано, как работает указанный код.

![Рисунок, иллюстрирующий различные направления потока.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)

Элемент в дереве [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] будет наследовать <xref:System.Windows.FrameworkElement.FlowDirection%2A> из своего контейнера. В следующем примере <xref:System.Windows.Controls.TextBlock> находится внутри <xref:System.Windows.Controls.Grid>, который находится в <xref:System.Windows.Window>. Установка <xref:System.Windows.FrameworkElement.FlowDirection%2A> для <xref:System.Windows.Window> подразумевает также его настройку для <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.TextBlock>.

В следующем примере демонстрируется настройка <xref:System.Windows.FrameworkElement.FlowDirection%2A>.

[!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]

<xref:System.Windows.Window> верхнего уровня имеет <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection>, поэтому все элементы, содержащиеся в нем, также наследуют тот же <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Чтобы элемент переопределял заданный <xref:System.Windows.FrameworkElement.FlowDirection%2A>, он должен добавить явное изменение направления, такое как второй <xref:System.Windows.Controls.TextBlock> в предыдущем примере, который изменяется на <xref:System.Windows.FlowDirection.LeftToRight>. Если <xref:System.Windows.FrameworkElement.FlowDirection%2A> не определено, применяется <xref:System.Windows.FlowDirection.LeftToRight> по умолчанию.

На следующем рисунке показаны выходные данные предыдущего примера.

![Рисунок, иллюстрирующий явное изменение направления потока.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)

<a name="FlowDocument"></a>

## <a name="flowdocument"></a>FlowDocument

Многие платформы разработки, такие как HTML, Win32 и Java, предоставляют специальную поддержку для разработки двунаправленного содержимого. Языки разметки, такие как HTML, предоставляют авторам содержимого необходимую разметку для вывода текста в любом требуемом направлении, например HTML 4,0, «dir», который принимает значения «RTL» или «LTR» в качестве значений. Этот тег похож на свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A>, но свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> работает более продвинутым способом разметки текстового содержимого и может использоваться для содержимого, отличного от Text.

В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Documents.FlowDocument> является универсальным элементом [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который может содержать сочетание текста, таблиц, изображений и других элементов. Этот элемент используется в примерах, описанных ниже.

Добавление текста в <xref:System.Windows.Documents.FlowDocument> может выполняться несколькими способами. Проще всего это сделать с помощью <xref:System.Windows.Documents.Paragraph>, который является элементом уровня блока, используемым для группировки содержимого, например текста. Чтобы добавить текст в элементы встроенного уровня, примеры используют <xref:System.Windows.Documents.Span> и <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span> — это элемент содержимого потока встроенного уровня, используемый для группирования других встроенных элементов, а <xref:System.Windows.Documents.Run> — элемент содержимого потока встроенного уровня, предназначенный для хранения выполнения неформатированного текста. <xref:System.Windows.Documents.Span> может содержать несколько элементов <xref:System.Windows.Documents.Run>.

В первом примере документа содержится документ с числом имен общих сетевых ресурсов. например `\\server1\folder\file.ext`. Независимо от того на каком языке написан документ, в котором содержится эта сетевая ссылка, на арабском или английском, нам хотелось бы, чтобы он выглядел всегда одинаково. На следующем рисунке показано использование элемента Span и отображение ссылки в документе на арабском <xref:System.Windows.FlowDirection.RightToLeft>:

![Рисунок, демонстрирующий использование элемента Span.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")

Поскольку текст <xref:System.Windows.FlowDirection.RightToLeft>, все специальные символы, такие как «\\», разделяют текст в порядке справа налево. Это приводит к отображению ссылки в правильном порядке, поэтому для устранения проблемы необходимо внедрить текст, чтобы сохранить отдельные <xref:System.Windows.Documents.Run> <xref:System.Windows.FlowDirection.LeftToRight>. Вместо того чтобы использовать отдельный <xref:System.Windows.Documents.Run> для каждого языка, лучшим способом решить эту проблему является встраивание редко используемого текста на английском языке в более крупные арабские <xref:System.Windows.Documents.Span>.

На следующем рисунке показано, как использовать элемент Run, внедренный в элемент span:

![Рисунок, иллюстрирующий элемент Run, внедренный в элемент span.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)

В следующем примере демонстрируется использование <xref:System.Windows.Documents.Run> и <xref:System.Windows.Documents.Span> элементов в документах.

[!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]

<a name="SpanElements"></a>

## <a name="span-elements"></a>Элементы Span

Элемент <xref:System.Windows.Documents.Span> работает как разделитель границ между текстами с различными направлениями потока.  Даже <xref:System.Windows.Documents.Span> элементы с одинаковым направлением потока считаются разными двунаправленными областями, то есть элементы <xref:System.Windows.Documents.Span> упорядочиваются в <xref:System.Windows.FlowDirection>контейнера, а только содержимое внутри элемента <xref:System.Windows.Documents.Span> соответствует <xref:System.Windows.FlowDirection> <xref:System.Windows.Documents.Span>.

На следующем рисунке показано направление потока для нескольких <xref:System.Windows.Controls.TextBlock> элементов.

![Рисунок, иллюстрирующий текстовые блоки с различными направлениями потока.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)

В следующем примере показано, как использовать элементы <xref:System.Windows.Documents.Span> и <xref:System.Windows.Documents.Run> для получения результатов, показанных на предыдущем рисунке.

[!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]

В элементах <xref:System.Windows.Controls.TextBlock> в примере элементы <xref:System.Windows.Documents.Span> размещаются в соответствии с <xref:System.Windows.FlowDirection> их родителей, но текст внутри каждого элемента <xref:System.Windows.Documents.Span> проходит в соответствии с их собственными <xref:System.Windows.FlowDirection>. Это применимо для латинского, арабского или любого другого языка.

### <a name="adding-xmllang"></a>Добавление XML: lang

На следующем рисунке показан еще один пример, использующий числа и арифметические выражения, например `"200.0+21.4=221.4"`. Обратите внимание, что заданы только <xref:System.Windows.FlowDirection>.

![График, отображающий числа только с помощью FlowDirection.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)

Пользователи этого приложения будут разочарованы выходными данными, несмотря на то, что <xref:System.Windows.FlowDirection> верными числами не являются арабскими цифрами.

Элементы XAML могут включать атрибут XML (`xml:lang`), определяющий язык каждого элемента. XAML также поддерживает принцип языка XML, в котором `xml:lang` значения, применяемые к родительским элементам в дереве, используются дочерними элементами. В предыдущем примере, поскольку язык не был определен для элемента <xref:System.Windows.Documents.Run> или какого-либо из его элементов верхнего уровня, использовался `xml:lang` по умолчанию, который `en-US` для XAML. Внутренний алгоритм формирования чисел [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] выбирает числа на соответствующем языке — в данном случае это английский язык. Чтобы арабские числа отображались правильно `xml:lang` необходимо установить.

На следующем рисунке показан пример с добавленным `xml:lang`.

![Рисунок, иллюстрирующий арабские цифры, которые передаются справа налево.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)

В следующем примере в приложение добавляется `xml:lang`.

[!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]

Имейте в виду, что многие языки имеют разные `xml:lang` значения в зависимости от целевого региона, например `"ar-SA"` и `"ar-EG"` представляют два варианта арабского языка. В предыдущих примерах показано, что необходимо определить значения `xml:lang` и <xref:System.Windows.FlowDirection>.

<a name="FlowDirectionNontext"></a>

## <a name="flowdirection-with-non-text-elements"></a>Направление потока применительно к нетекстовым элементам

<xref:System.Windows.FlowDirection> определяет не только то, как поток текста в текстовом элементе, но также направление потока почти для каждого элемента [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. На следующем рисунке показана <xref:System.Windows.Controls.ToolBar>, использующая горизонтальную <xref:System.Windows.Media.LinearGradientBrush> для рисования фона с градиентом слева направо.

![Рисунок, на котором показана панель инструментов с градиентом слева направо.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)

После установки <xref:System.Windows.FlowDirection> для <xref:System.Windows.FlowDirection.RightToLeft>не только кнопки <xref:System.Windows.Controls.ToolBar> упорядочены справа налево, но даже <xref:System.Windows.Media.LinearGradientBrush> переупорядочивает свои смещения для передачи справа налево.

На следующем рисунке показано перевыравнивание <xref:System.Windows.Media.LinearGradientBrush>.

![Рисунок, на котором показана панель инструментов с градиентом справа налево.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)

В следующем примере рисуется <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.Controls.ToolBar>. (Чтобы нарисовать его слева направо, удалите атрибут <xref:System.Windows.FlowDirection> в <xref:System.Windows.Controls.ToolBar>.

[!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]

<a name="FlowDirectionExceptions"></a>

### <a name="flowdirection-exceptions"></a>Исключения направления потока

Существует несколько случаев, когда <xref:System.Windows.FlowDirection> не работает должным образом. В этом разделе рассматриваются два таких исключения.

**Изображение**

<xref:System.Windows.Controls.Image> представляет элемент управления, который отображает изображение. В XAML его можно использовать со свойством <xref:System.Windows.Controls.Image.Source%2A>, определяющим универсальный код ресурса (URI) отображаемого <xref:System.Windows.Controls.Image>.

В отличие от других элементов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], <xref:System.Windows.Controls.Image> не наследует <xref:System.Windows.FlowDirection> из контейнера. Однако если для <xref:System.Windows.FlowDirection> задано явное значение <xref:System.Windows.FlowDirection.RightToLeft>, <xref:System.Windows.Controls.Image> отображается горизонтально. Это сделано для удобства разработчиков двунаправленного содержимого. В некоторых случаях горизонтальным отражением достигается требуемый эффект.

На следующем рисунке показана перевернутая <xref:System.Windows.Controls.Image>.

![Рисунок, иллюстрирующий перевернутое изображение.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)

В следующем примере показано, что <xref:System.Windows.Controls.Image> не может наследовать <xref:System.Windows.FlowDirection> из <xref:System.Windows.Controls.StackPanel>, содержащего его.

> [!NOTE]
> Необходимо иметь файл с именем **ms_logo. jpg** в файле C:\ диск для выполнения этого примера.

[!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]

> [!NOTE]
> В файлы для загрузки включен файл **ms_logo JPG** . В коде предполагается, что JPG-файл находится не внутри проекта, а где-нибудь на диске C:\. Необходимо скопировать JPG-файл из файлов проекта на диск C:\ или изменить код так, чтобы выполнялся поиск файла внутри проекта. Для этого измените `Source="file://c:/ms_logo.jpg"` на `Source="ms_logo.jpg"`.

**Paths**

В дополнение к <xref:System.Windows.Controls.Image>другой интересный элемент <xref:System.Windows.Shapes.Path>. Контур — это объект, который может нарисовать последовательность соединенных линий и кривых. Он ведет себя так же, как <xref:System.Windows.Controls.Image> относительно <xref:System.Windows.FlowDirection>; Например, его <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection> является горизонтальным зеркалом <xref:System.Windows.FlowDirection.LeftToRight> его. Однако, в отличие от <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> наследует <xref:System.Windows.FlowDirection> от контейнера, и ему не нужно явно указывать его.

В следующем примере рисуется простая стрелка, использующая три линии. Первая стрелка наследует <xref:System.Windows.FlowDirection.RightToLeft> направление потока от <xref:System.Windows.Controls.StackPanel>, чтобы ее начальная и конечная точки измерялись от корня справа. Вторая стрелка, которая имеет явное <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection>, также начинается с правой стороны. Однако третья стрелка начинается от корня с левой стороны. Дополнительные сведения о рисовании см. в разделе <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.GeometryGroup>.

[!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]

На следующем рисунке показаны выходные данные предыдущего примера со стрелками, рисуемыми с помощью элемента `Path`:

![Рисунок, иллюстрирующий стрелки, рисуемые с помощью элемента Path.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)

<xref:System.Windows.Controls.Image> и <xref:System.Windows.Shapes.Path> являются двумя примерами того, как [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] использует <xref:System.Windows.FlowDirection>. При разметке [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов в определенном направлении в контейнере <xref:System.Windows.FlowDirection> можно использовать с такими элементами, как <xref:System.Windows.Controls.InkPresenter>, который визуализирует рукописный ввод на поверхности, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>. Каждый раз, когда требуется поведение справа налево для содержимого, которое имитирует поведение слева направо или наоборот, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет эту возможность.

<a name="NumberSubstitution"></a>

## <a name="number-substitution"></a>Подстановки чисел

Исторически система Windows поддерживала подстановку чисел, разрешая представление различных культурных форм для одних и тех же цифр и сохраняя внутреннее хранение этих цифр в унифицированных пределах разных национальных настроек, например числа хранятся в их хорошо известные шестнадцатеричные значения, 0x40, 0x41 влево, но отображаемые в соответствии с выбранным языком.

Это позволяло приложениям обрабатывать числовые значения без необходимости преобразования их из одного языка в другой, например, пользователь может открыть электронную таблицу Microsoft Excel в локализованных арабских окнах и увидеть цифры на арабском языке, но открыть в Европейская версия Windows, а также европейские представления одних и тех же чисел. Это также необходимо для других символов, например запятая или символ процента, так как они обычно сопровождают числа в одном документе.

Платформа [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] продолжает эту традицию и добавляет новые возможности, позволяющие пользователю более точно определять, когда и как должна применяться подстановка. Эта функция может использоваться со всеми языками, но особенно полезна она в обработке двунаправленного содержимого, когда представление чисел для разных региональных стандартов становится проблемой для разработчиков приложений, предназначенных для использования в разных странах.

Основное свойство, контролирующее, как работает подстановка чисел в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] — это <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> свойство зависимостей. Класс <xref:System.Windows.Media.NumberSubstitution> указывает, как должны отображаться числа в тексте. Он имеет три открытых свойства, определяющих его поведение. Ниже приведена сводка по каждому из свойств.

**CultureSource.**

Это свойство задает способ определения регионального стандарта для чисел. Он принимает одно из трех значений перечисления <xref:System.Windows.Media.NumberCultureSource>.

- Переопределение: число языка и региональных параметров <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> свойства.

- Text (текст). Региональный стандарт для чисел определяется по региональному стандарту фрагмента текста. В разметке это будет `xml:lang`или его псевдоним `Language` свойство (<xref:System.Windows.FrameworkElement.Language%2A> или <xref:System.Windows.FrameworkContentElement.Language%2A>). Кроме того, это значение по умолчанию для классов, производных от <xref:System.Windows.FrameworkContentElement>. К таким классам относятся <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> и т. д.

- User (пользователь). Региональный стандарт для чисел определяется по региональному стандарту текущего потока. Это свойство является значением по умолчанию для всех подклассов <xref:System.Windows.FrameworkElement>, таких как <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> и <xref:System.Windows.Controls.TextBlock>.

**CultureOverride**.

Свойство <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> используется только в том случае, если свойство <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> имеет значение <xref:System.Windows.Media.NumberCultureSource.Override> и не учитывается в противном случае. Оно определяет региональный стандарт для чисел. Значение `null`, значение по умолчанию, интерпретируется как en-US.

**Substitution**.

Это свойство определяет выполняемый тип подстановки чисел. Он принимает одно из следующих <xref:System.Windows.Media.NumberSubstitutionMethod> значений перечисления:

- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: метод Substitution определяется на основе свойства <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> для языка и региональных параметров. Это значение по умолчанию.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>. Если язык и региональные параметры числа являются арабскими или Персидский, они указывают, что цифры зависят от контекста.

- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: числа всегда отображаются в виде европейских цифр.

- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: числа отображаются с использованием национальных цифр для языка и региональных параметров числа, как указано в <xref:System.Globalization.CultureInfo.NumberFormat%2A>ах языка и региональных параметров.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: числа отображаются с использованием традиционных цифр для языка и региональных параметров числа. Для большинства языков и региональных параметров это то же самое, что <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Однако <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> выдает в качестве знаков латинского алфавита арабские цифры, в то время как это значение приводит к арабским цифрам для всех языков и региональных параметров арабского языка.

О чем говорят эти значения разработчикам двунаправленного содержимого? В большинстве случаев разработчику может потребоваться только определить <xref:System.Windows.FlowDirection> и язык для каждого текстового [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элемента, например `Language="ar-SA"` и логика <xref:System.Windows.Media.NumberSubstitution> позаботится об отображении чисел в соответствии с правильным [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. В следующем примере демонстрируется использование арабских и английских чисел в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложении, работающем в арабской версии Windows.

[!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]

На следующем рисунке показаны выходные данные предыдущего примера, если вы работаете в арабской версии Windows с арабскими и англоязычными номерами.

![Рисунок, в котором показаны арабские и английские цифры.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)

В этом случае важно <xref:System.Windows.FlowDirection>, так как при настройке <xref:System.Windows.FlowDirection> на <xref:System.Windows.FlowDirection.LeftToRight> вместо этого будут выдаваться европейские цифры. В следующих разделах рассматривается, как сделать одинаковое отображение цифр по всему документу. Если этот пример не выполняется на арабской версии Windows, все цифры отображаются на экране как европейские цифры.

**Определение правил подстановки**

В реальном приложении может возникнуть необходимость установить язык программным путем. Например, необходимо установить атрибут `xml:lang` так, чтобы он совпадал с именем, используемым [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]системы, или, возможно, изменить язык в зависимости от состояния приложения.

Если вы хотите внести изменения в зависимости от состояния приложения, используйте другие функции, предоставляемые [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].

Сначала задайте `NumberSubstitution.CultureSource="Text"`компонента приложения. Использование этого параметра гарантирует, что параметры не поступают из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для текстовых элементов, которые по умолчанию имеют значение "User", например <xref:System.Windows.Controls.TextBlock>.

Например:

```xaml
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

В соответствующем C# коде задайте для свойства `Language`, например значение `"ar-SA"`.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Если необходимо задать для свойства `Language` язык пользовательского интерфейса текущего пользователя, используйте следующий код.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> представляет текущий язык и региональные параметры, используемые текущим потоком во время выполнения.

Окончательный пример кода XAML должен быть подобен приведенному ниже примеру.

[!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]

Окончательный C# пример должен выглядеть следующим образом.

[!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]

На следующем рисунке показано, как выглядит окно для любого языка программирования, отображая арабские цифры:

![Рисунок, отображающий арабские цифры.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)

**Использование свойства подстановки**

Способ подстановки чисел работает в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] зависит как от языка текстового элемента, так и от его <xref:System.Windows.FlowDirection>. Если <xref:System.Windows.FlowDirection> слева направо, то выводятся европейские цифры. Однако если перед ним стоит текст на арабском языке или для языка задано значение AR, а <xref:System.Windows.FlowDirection> имеет <xref:System.Windows.FlowDirection.RightToLeft>, вместо этого выводятся арабские цифры.

В некоторых случаях может потребоваться создание универсального приложения, например с европейскими цифрами для всех пользователей. Или арабские цифры в <xref:System.Windows.Documents.Table>ных ячейках с конкретным <xref:System.Windows.Style>. Одним из простых способов является использование свойства <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>.

В следующем примере в первом <xref:System.Windows.Controls.TextBlock> не задано свойство <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>, поэтому алгоритм отображает арабские цифры, как ожидалось. Однако во второй <xref:System.Windows.Controls.TextBlock>подстановка устанавливается в Европейский, переопределяющий подстановку по умолчанию для арабских чисел, и выводятся европейские цифры.

[!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
