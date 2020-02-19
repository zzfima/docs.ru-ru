---
title: Проверка попадания на визуальном уровне
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit testing functionality [WPF]
- visual layer [WPF], hit testing functionality
ms.assetid: b1a64b61-14be-4d75-b89a-5c67bebb2c7b
ms.openlocfilehash: 28ae983923c985050ac589166023e483721028d3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452621"
---
# <a name="hit-testing-in-the-visual-layer"></a>Проверка попадания на визуальном уровне
В этом разделе приведены общие сведения о функции проверки попадания, предоставляемой на визуальном уровне. Поддержка проверки попадания позволяет определить, попадает ли геометрическое значение или точка в отображаемое содержимое <xref:System.Windows.Media.Visual>, что позволяет реализовать поведение пользовательского интерфейса, например прямоугольник выделения, для выбора нескольких объектов.  

<a name="hit_testing_scenarios"></a>   
## <a name="hit-testing-scenarios"></a>Сценарии проверки попадания  
 Класс <xref:System.Windows.UIElement> предоставляет метод <xref:System.Windows.UIElement.InputHitTest%2A>, который позволяет выполнять проверку на элементе, используя заданное значение координаты. Во многих случаях метод <xref:System.Windows.UIElement.InputHitTest%2A> предоставляет требуемые функции для реализации проверки попадания элементов. Однако существует несколько сценариев, в которых может потребоваться реализация проверки попадания на визуальном уровне.  
  
- Проверка нажатия для объектов, не относящихся к<xref:System.Windows.UIElement>: это происходит при проверке попадания на объекты, не являющиеся<xref:System.Windows.UIElement>, например <xref:System.Windows.Media.DrawingVisual> или графические объекты.  
  
- Проверка попадания с использованием геометрического объекта: это применимо, если нужно проверить попадание с использованием геометрического объекта, а не значения координат точки.  
  
- Проверка попадания для нескольких объектов: это применимо, когда нужно проверить попадание для нескольких объектов, например перекрывающихся объектов. Можно получить результаты для всех визуальных объектов, пересекающих геометрический объект или точку, а не только для первого из них.  
  
- Пропуск политики проверки попадания <xref:System.Windows.UIElement>: это применимо, если необходимо пропустить политику проверки попадания <xref:System.Windows.UIElement>, которая учитывает такие факторы, как недоступность или невидимость элемента.  
  
> [!NOTE]
> Пример полного кода, иллюстрирующего проверку попадания на визуальном уровне, см. в разделе [Пример проверки попадания с помощью DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual) и [Пример взаимодействия проверки попадания с Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).  
  
<a name="hit_testing_support"></a>   
## <a name="hit-testing-support"></a>Поддержка проверки попадания  
 Назначение методов <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> в классе <xref:System.Windows.Media.VisualTreeHelper> заключается в том, чтобы определить, находится ли геометрический объект или координата точки в отображаемом содержимом данного объекта, например элемент управления или графический элемент. Например, можно использовать проверку попадания для определения, попадает ли щелчок мышью в ограничивающем прямоугольнике объекта в границы фигуры круга. Можно также переопределить реализацию проверки попадания по умолчанию для выполнения собственных вычислений по проверке попадания.  
  
 На следующем рисунке показана связь между областью не прямоугольного объекта и ограничивающим его прямоугольником.  
  
 ![Допустимая область проверки попадания](./media/wcpsdk-mmgraphics-visuals-hittest-1.png "wcpsdk_mmgraphics_visuals_hittest_1")  
Допустимая область проверки попадания  
  
<a name="hit_testing_and_z-order"></a>   
## <a name="hit-testing-and-z-order"></a>Проверка попадания и порядок по оси Z  
 Визуальный уровень [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] поддерживает проверку попадания для всех объектов, в которых находится точка или геометрическая фигура, а не только для самого верхнего. Результаты возвращаются в порядке по оси z. Однако визуальный объект, который передается в качестве параметра методу <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>, определяет, какая часть визуального дерева будет проверять нажатие. Можно проверять на попадание все визуальное дерево или любую его часть.  
  
 На следующем рисунке объект-круг расположен поверх объектов квадрат и треугольник. Если вы заинтересованы только в проверке нажатия визуального объекта, значение z-порядка которого является самым верхним, можно задать перечисление проверки попадания визуальных элементов, чтобы возвратить <xref:System.Windows.Media.HitTestResultBehavior.Stop> из <xref:System.Windows.Media.HitTestResultCallback>, чтобы предотвратить обход проверки попадания после первого элемента.  
  
 ![Порядок по оси Z для визуального дерева](./media/wcpsdk-mmgraphics-visuals-hittest-2.png "wcpsdk_mmgraphics_visuals_hittest_2")  
Z-порядок для визуального дерева  
  
 Если требуется перечислить все визуальные объекты в определенной точке или геометрии, возвращайте <xref:System.Windows.Media.HitTestResultBehavior.Continue> из <xref:System.Windows.Media.HitTestResultCallback>. Это означает, что можно выполнять проверку попадания для визуальных объектов, которые находятся под другими объектами, даже если они полностью не видны. Более подробные сведения см. в примере кода в разделе «Использование обратного вызова результатов проверки попадания».  
  
> [!NOTE]
> Проверку попадания можно выполнять и для прозрачного визуального объекта.  
  
<a name="using_default_hit_testing"></a>   
## <a name="using-default-hit-testing"></a>Проверка попадания по умолчанию  
 Можно определить, находится ли точка в пределах геометрии визуального объекта, используя метод <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>, чтобы указать визуальный объект и значение координаты точки для проверки. Параметр-визуальный объект определяет начальную точку в визуальном дереве для поиска при проверке попадания. Если визуальный объект находится в визуальном дереве, геометрический элемент которого содержит координаты, то для него задается свойство <xref:System.Windows.Media.HitTestResult.VisualHit%2A> объекта <xref:System.Windows.Media.HitTestResult>. Затем <xref:System.Windows.Media.HitTestResult> возвращается из метода <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>. Если точка не содержится в визуальном поддереве, для которого выполняется проверка попадания, <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> возвращает `null`.  
  
> [!NOTE]
> Проверка попадания по умолчанию всегда возвращает самый верхний объект по оси Z. Чтобы определить все визуальные объекты, даже те, которые могут быть частично или полностью перекрыты, используйте обратный вызов результатов проверки попадания.  
  
 Значение координаты, передаваемое в качестве параметра точки для метода <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>, должно быть относительно пространства координат визуального объекта, для которого выполняется проверка попадания. Например, при наличии вложенных визуальных объектов, определенных в точке (100, 100) пространства координат родительского элемента, проверка попадания дочернего визуального объекта в (0, 0) эквивалентно проверке попадания в точке (100, 100) в пространстве координат родительского элемента.  
  
 В следующем коде показано, как настроить обработчики событий мыши для объекта <xref:System.Windows.UIElement>, который используется для записи событий, используемых для проверки попадания.  
  
 [!code-csharp[HitTestingOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[HitTestingOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#100)]  
  
### <a name="how-the-visual-tree-affects-hit-testing"></a>Влияние визуального дерева на проверку попадания  
 Начальная точка в визуальном дереве определяет, какие объекты возвращаются во время перечисления объектов проверки попадания. Если есть несколько объектов, для которых нужно выполнить проверку попадания, визуальные объект, используемый в качестве начальной точки в визуальном дереве, должен быть общим предком всех интересующих объектов. Например если нужно выполнить проверку попадания и для элемента-кнопки и для визуального объекта на следующем рисунке, необходимо установить начальную точку в визуальном дереве на их общего предка. В этом случае элемент общим предком элемента-кнопки и визуального объекта является элемент canvas.  
  
 ![Иерархия визуального дерева](./media/wcpsdk-mmgraphics-visuals-overview-01.gif "wcpsdk_mmgraphics_visuals_overview_01")  
Иерархия визуального дерева  
  
> [!NOTE]
> Свойство <xref:System.Windows.UIElement.IsHitTestVisible%2A> Возвращает или задает значение, которое определяет, может ли объект, производный от <xref:System.Windows.UIElement>, быть возвращен как результат проверки нажатия в какой-либо части его отображаемого содержимого. Это позволяет выборочно изменять визуальное дерево, чтобы определить, какие визуальные объекты участвуют в проверке попадания.  
  
<a name="using_a_hit_test_result_callback"></a>   
## <a name="using-a-hit-test-result-callback"></a>Использование обратного вызова результатов проверки попадания  
 Можно перечислить в визуальном дереве все визуальные объекты, геометрия которых содержит заданное значение координат. Это позволяет выделить все визуальные объекты, даже те, которые могут быть частично или полностью перекрыты другими визуальными объектами. Чтобы перечислить визуальные объекты в визуальном дереве, используйте метод <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> с функцией обратного вызова проверки попадания. Функция обратного вызова проверки попадания вызывается системой, если указанное значение координат содержится в визуальном объекте.  
  
 Во время перечисления результатов проверки попадания не следует выполнять никакие операции по изменению визуального дерева. Добавление или удаление объектов визуального дерева во время его проверки может привести к непредсказуемому поведению. Можно безопасно изменить визуальное дерево после того, как метод <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> возвращает. Для хранения значений во время перечисления результатов проверки попадания может потребоваться предоставить структуру данных, например <xref:System.Collections.ArrayList>.  
  
 [!code-csharp[HitTestingOverview#101](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[HitTestingOverview#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#101)]  
  
 Метод обратного вызова проверки попадания определяет действия, которые выполняются при определении проверки попадания для конкретного визуального объекта в визуальном дереве. После выполнения действий возвращается значение <xref:System.Windows.Media.HitTestResultBehavior>, определяющее, следует ли продолжать перечисление любых других визуальных объектов.  
  
 [!code-csharp[HitTestingOverview#102](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[HitTestingOverview#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#102)]  
  
> [!NOTE]
> Порядок перечисления визуальных объектов попадания соответствует их координатам по оси Z. Первым перечисляется визуальный объект с самой большой координатой по оси Z. Остальные визуальные объекты перечисляются по убыванию значения координаты по оси Z. Этот порядок перечисления соответствует порядку отрисовки визуальных объектов.  
  
 Перечисление визуальных объектов можно в любое время в функции обратного вызова проверки попадания, возвращая <xref:System.Windows.Media.HitTestResultBehavior.Stop>.  
  
 [!code-csharp[HitTestingOverview#103](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#103)]
 [!code-vb[HitTestingOverview#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#103)]  
  
<a name="using_a_hit_test_filter_callback"></a>   
## <a name="using-a-hit-test-filter-callback"></a>Использование обратного вызова фильтра проверки попадания  
 Можно использовать необязательный фильтр проверки попадания для ограничения объектов, которые передаются в качестве результатов проверки попадания. Это позволяет пропустить части визуального дерева, которые не нужны для обработки в результатах проверки нажатия. Чтобы реализовать фильтр проверки попадания, необходимо определить функцию обратного вызова фильтра проверки попадания и передать ее в качестве значения параметра при вызове метода <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  
  
 [!code-csharp[HitTestingOverview#104](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#104)]
 [!code-vb[HitTestingOverview#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#104)]  
  
 Если вы не хотите указывать функцию обратного вызова фильтра проверки попадания, передайте `null` значение в качестве параметра для метода <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  
  
 [!code-csharp[HitTestingOverview#105](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#105)]
 [!code-vb[HitTestingOverview#105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#105)]  
  
 ![Обрезка визуального дерева с помощью фильтра проверки попадания](./media/filteredvisualtree-01.png "FilteredVisualTree_01")  
Обрезка визуального дерева  
  
 Функция обратного вызова фильтра проверки попадания позволяет перечислить все визуальные объекты, отображаемое содержимое которых содержит указанные координаты. Однако, может понадобиться пропустить отдельные части визуального дерева в функции обратного вызова результатов проверки нажатия. Возвращаемое значение функции обратного вызова фильтра проверки нажатия определяет, какой тип действия должен выполняться при перечислении визуальных объектов. Например, при возврате значения <xref:System.Windows.Media.HitTestFilterBehavior.ContinueSkipSelfAndChildren>можно удалить текущий визуальный объект и его дочерние объекты из перечисления результатов проверки попадания. Это означает, что функция обратного вызова результатов проверки попадания не увидит эти объекты в перечислении. Обрезка визуального дерева объектов позволяет уменьшить объем обработки во время перечисления результатов проверки попадания. В следующем примере кода фильтр пропускает метки и их потомков и проверяет все остальные объекты.  
  
 [!code-csharp[HitTestingOverview#106](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#106)]
 [!code-vb[HitTestingOverview#106](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#106)]  
  
> [!NOTE]
> Функция обратного вызова фильтра проверки попадания иногда вызывается в случаях, когда функция обратного вызова результатов проверки попадания не вызывается.  
  
<a name="overriding_default_hit_testing"></a>   
## <a name="overriding-default-hit-testing"></a>Переопределение проверки попадания по умолчанию  
 Можно переопределить поддержку проверки попадания по умолчанию визуального объекта, переопределив метод <xref:System.Windows.Media.Visual.HitTestCore%2A>. Это означает, что при вызове метода <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> вызывается переопределенная реализация <xref:System.Windows.Media.Visual.HitTestCore%2A>. Переопределенный метод вызывается при попадании в ограничивающий прямоугольник визуального объекта, даже если координата не попадает в отображаемое содержимое визуального объекта.  
  
 [!code-csharp[HitTestingOverview#107](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#107)]
 [!code-vb[HitTestingOverview#107](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#107)]  
  
 Иногда может понадобиться проверка попадания как для ограничивающего прямоугольника, так и для отображаемого содержимого визуального объекта. Используя значение параметра `PointHitTestParameters` в переопределенном методе <xref:System.Windows.Media.Visual.HitTestCore%2A> в качестве параметра для <xref:System.Windows.Media.Visual.HitTestCore%2A>базового метода, можно выполнять действия в зависимости от попадания ограничивающего прямоугольника визуального объекта, а затем выполнять вторую проверку попадания для визуализированного содержимого визуального объекта.  
  
 [!code-csharp[HitTestingOverview#108](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#108)]
 [!code-vb[HitTestingOverview#108](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#108)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- <xref:System.Windows.Media.HitTestResult>
- <xref:System.Windows.Media.HitTestResultCallback>
- <xref:System.Windows.Media.HitTestFilterCallback>
- <xref:System.Windows.UIElement.IsHitTestVisible%2A>
- [Проверка нажатия с помощью примера DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)
- [Проверка нажатия с помощью примера взаимодействия Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [Проверка попадания геометрического объекта в визуальный объект](how-to-hit-test-geometry-in-a-visual.md)
- [Проверка попадания с использованием контейнера узла Win32](how-to-hit-test-using-a-win32-host-container.md)
