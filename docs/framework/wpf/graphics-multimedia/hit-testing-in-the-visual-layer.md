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
ms.openlocfilehash: d4d304353e91147c57297dcc4525759ff1474b4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186406"
---
# <a name="hit-testing-in-the-visual-layer"></a>Проверка попадания на визуальном уровне
В этом разделе приведены общие сведения о функции проверки попадания, предоставляемой на визуальном уровне. Поддержка тестирования хита позволяет определить, подпадает ли геометрия или <xref:System.Windows.Media.Visual>значение точки в отображено содержимое, что позволяет реализовать поведение пользовательского интерфейса, такое как прямоугольник выбора для выбора нескольких объектов.  

<a name="hit_testing_scenarios"></a>
## <a name="hit-testing-scenarios"></a>Сценарии проверки попадания  
 Класс <xref:System.Windows.UIElement> предоставляет <xref:System.Windows.UIElement.InputHitTest%2A> метод, который позволяет поразить тест по элементу, используя заданное значение координат. Во многих случаях <xref:System.Windows.UIElement.InputHitTest%2A> метод обеспечивает нужную функциональность для реализации хит-тестирования элементов. Однако существует несколько сценариев, в которых может потребоваться реализация проверки попадания на визуальном уровне.  
  
- Хит-тестирование против<xref:System.Windows.UIElement> не-объектов: Это относится,<xref:System.Windows.UIElement> если вы <xref:System.Windows.Media.DrawingVisual> попали тестирования не-объектов, таких как или графических объектов.  
  
- Проверка попадания с использованием геометрического объекта: это применимо, если нужно проверить попадание с использованием геометрического объекта, а не значения координат точки.  
  
- Проверка попадания для нескольких объектов: это применимо, когда нужно проверить попадание для нескольких объектов, например перекрывающихся объектов. Можно получить результаты для всех визуальных объектов, пересекающих геометрический объект или точку, а не только для первого из них.  
  
- Игнорирование <xref:System.Windows.UIElement> политики тестирования хитов: Это <xref:System.Windows.UIElement> применяется, когда вам нужно игнорировать политику тестирования хита, которая учитывает такие факторы, как отключенный элемент или невидимый.  
  
> [!NOTE]
> Пример полного кода, иллюстрирующего проверку попадания на визуальном уровне, см. в разделе [Пример проверки попадания с помощью DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual) и [Пример взаимодействия проверки попадания с Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).  
  
<a name="hit_testing_support"></a>
## <a name="hit-testing-support"></a>Поддержка проверки попадания  
 Цель <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> методов в <xref:System.Windows.Media.VisualTreeHelper> классе состоит в том, чтобы определить, находится ли значение геометрии или точки координат в отрисованной содержимости данного объекта, например элемент управления или графический элемент. Например, можно использовать проверку попадания для определения, попадает ли щелчок мышью в ограничивающем прямоугольнике объекта в границы фигуры круга. Можно также переопределить реализацию проверки попадания по умолчанию для выполнения собственных вычислений по проверке попадания.  
  
 На следующем рисунке показана связь между областью не прямоугольного объекта и ограничивающим его прямоугольником.  
  
 ![Допустимая область проверки попадания](./media/wcpsdk-mmgraphics-visuals-hittest-1.png "wcpsdk_mmgraphics_visuals_hittest_1")  
Допустимая область проверки попадания  
  
<a name="hit_testing_and_z-order"></a>
## <a name="hit-testing-and-z-order"></a>Проверка попадания и порядок по оси Z  
 Визуальный уровень [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] поддерживает проверку попадания для всех объектов, в которых находится точка или геометрическая фигура, а не только для самого верхнего. Результаты возвращаются в порядке по оси z. Тем не менее, визуальный объект, <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> который вы передаете в качестве параметра метода определяет, какая часть визуального дерева, которая будет хит тест. Можно проверять на попадание все визуальное дерево или любую его часть.  
  
 На следующем рисунке объект-круг расположен поверх объектов квадрат и треугольник. Если вы заинтересованы только в тестировании визуального объекта, значение z-order является самым главным, вы <xref:System.Windows.Media.HitTestResultBehavior.Stop> можете <xref:System.Windows.Media.HitTestResultCallback> установить визуальный пересчет теста хита, чтобы вернуться из, чтобы остановить пройденный тест после первого элемента.  
  
 ![Порядок по оси Z для визуального дерева](./media/wcpsdk-mmgraphics-visuals-hittest-2.png "wcpsdk_mmgraphics_visuals_hittest_2")  
Z-порядок для визуального дерева  
  
 Если вы хотите перечислить все визуальные объекты под определенной точкой или геометрией, вернитесь <xref:System.Windows.Media.HitTestResultBehavior.Continue> из <xref:System.Windows.Media.HitTestResultCallback>. Это означает, что можно выполнять проверку попадания для визуальных объектов, которые находятся под другими объектами, даже если они полностью не видны. Более подробные сведения см. в примере кода в разделе «Использование обратного вызова результатов проверки попадания».  
  
> [!NOTE]
> Проверку попадания можно выполнять и для прозрачного визуального объекта.  
  
<a name="using_default_hit_testing"></a>
## <a name="using-default-hit-testing"></a>Проверка попадания по умолчанию  
 Можно определить, находится ли точка в геометрии визуального <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> объекта, используя метод для определения визуального объекта и значения точек координат для проверки. Параметр-визуальный объект определяет начальную точку в визуальном дереве для поиска при проверке попадания. Если визуальный объект находится в визуальном дереве, геометрия которого содержит координаты, он устанавливается в <xref:System.Windows.Media.HitTestResult.VisualHit%2A> свойство <xref:System.Windows.Media.HitTestResult> объекта. Затем <xref:System.Windows.Media.HitTestResult> возвращается из <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метода. Если точка не содержится с визуальной поддерево <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> вы `null`попали тестирования, возвращается .  
  
> [!NOTE]
> Проверка попадания по умолчанию всегда возвращает самый верхний объект по оси Z. Чтобы определить все визуальные объекты, даже те, которые могут быть частично или полностью перекрыты, используйте обратный вызов результатов проверки попадания.  
  
 Значение координат, которые <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> вы проходите по мере того, как параметр точки для метода должен быть относительно пространства координат визуального объекта, против которой вы попали. Например, при наличии вложенных визуальных объектов, определенных в точке (100, 100) пространства координат родительского элемента, проверка попадания дочернего визуального объекта в (0, 0) эквивалентно проверке попадания в точке (100, 100) в пространстве координат родительского элемента.  
  
 В следующем коде показано, как настроить <xref:System.Windows.UIElement> обработчики событий мыши для объекта, который используется для захвата событий, используемых для тестирования хитов.  
  
 [!code-csharp[HitTestingOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[HitTestingOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#100)]  
  
### <a name="how-the-visual-tree-affects-hit-testing"></a>Влияние визуального дерева на проверку попадания  
 Начальная точка в визуальном дереве определяет, какие объекты возвращаются во время перечисления объектов проверки попадания. Если есть несколько объектов, для которых нужно выполнить проверку попадания, визуальные объект, используемый в качестве начальной точки в визуальном дереве, должен быть общим предком всех интересующих объектов. Например если нужно выполнить проверку попадания и для элемента-кнопки и для визуального объекта на следующем рисунке, необходимо установить начальную точку в визуальном дереве на их общего предка. В этом случае элемент общим предком элемента-кнопки и визуального объекта является элемент canvas.  
  
 ![Иерархия визуального дерева](./media/wcpsdk-mmgraphics-visuals-overview-01.gif "wcpsdk_mmgraphics_visuals_overview_01")  
Иерархия визуального дерева  
  
> [!NOTE]
> Свойство <xref:System.Windows.UIElement.IsHitTestVisible%2A> получает или устанавливает значение, <xref:System.Windows.UIElement>которое декларирует, может ли объект, полученный из полученных, может быть возвращен в результате хит-теста из-за какой-то части его отобрасированного содержимого. Это позволяет выборочно изменять визуальное дерево, чтобы определить, какие визуальные объекты участвуют в проверке попадания.  
  
<a name="using_a_hit_test_result_callback"></a>
## <a name="using-a-hit-test-result-callback"></a>Использование обратного вызова результатов проверки попадания  
 Можно перечислить в визуальном дереве все визуальные объекты, геометрия которых содержит заданное значение координат. Это позволяет выделить все визуальные объекты, даже те, которые могут быть частично или полностью перекрыты другими визуальными объектами. Для перечисления визуальных объектов в <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> визуальном дереве используйте метод с функцией обратного вызова на удар. Функция обратного вызова проверки попадания вызывается системой, если указанное значение координат содержится в визуальном объекте.  
  
 Во время перечисления результатов проверки попадания не следует выполнять никакие операции по изменению визуального дерева. Добавление или удаление объектов визуального дерева во время его проверки может привести к непредсказуемому поведению. Вы можете безопасно изменить визуальное <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> дерево после возвращения метода. Возможно, необходимо предоставить структуру данных, такую как <xref:System.Collections.ArrayList>значение, для хранения значений во время перечисления результатов хит-теста.  
  
 [!code-csharp[HitTestingOverview#101](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[HitTestingOverview#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#101)]  
  
 Метод обратного вызова проверки попадания определяет действия, которые выполняются при определении проверки попадания для конкретного визуального объекта в визуальном дереве. После выполнения действий <xref:System.Windows.Media.HitTestResultBehavior> вы возвращаете значение, определяющее, продолжать ли перечисление любых других визуальных объектов или нет.  
  
 [!code-csharp[HitTestingOverview#102](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[HitTestingOverview#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#102)]  
  
> [!NOTE]
> Порядок перечисления визуальных объектов попадания соответствует их координатам по оси Z. Первым перечисляется визуальный объект с самой большой координатой по оси Z. Остальные визуальные объекты перечисляются по убыванию значения координаты по оси Z. Этот порядок перечисления соответствует порядку отрисовки визуальных объектов.  
  
 Вы можете остановить перечисление визуальных объектов в любое время <xref:System.Windows.Media.HitTestResultBehavior.Stop>в функции обратного вызова теста хит, вернув.  
  
 [!code-csharp[HitTestingOverview#103](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#103)]
 [!code-vb[HitTestingOverview#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#103)]  
  
<a name="using_a_hit_test_filter_callback"></a>
## <a name="using-a-hit-test-filter-callback"></a>Использование обратного вызова фильтра проверки попадания  
 Можно использовать необязательный фильтр проверки попадания для ограничения объектов, которые передаются в качестве результатов проверки попадания. Это позволяет пропустить части визуального дерева, которые не нужны для обработки в результатах проверки нажатия. Для реализации фильтра теста хит, вы определяете функцию обратного вызова фильтра хит-теста и передаете ее в качестве значения параметра при вызове метода. <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
  
 [!code-csharp[HitTestingOverview#104](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#104)]
 [!code-vb[HitTestingOverview#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#104)]  
  
 Если вы не хотите поставлять дополнительную функцию обратного `null` вызова фильтра <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> хит-теста, передайте значение в качестве параметра для метода.  
  
 [!code-csharp[HitTestingOverview#105](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#105)]
 [!code-vb[HitTestingOverview#105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#105)]  
  
 ![Сокращение визуального дерева с использованием фильтра проверки нажатия](./media/filteredvisualtree-01.png "FilteredVisualTree_01")  
Обрезка визуального дерева  
  
 Функция обратного вызова фильтра проверки попадания позволяет перечислить все визуальные объекты, отображаемое содержимое которых содержит указанные координаты. Однако, может понадобиться пропустить отдельные части визуального дерева в функции обратного вызова результатов проверки нажатия. Возвращаемое значение функции обратного вызова фильтра проверки нажатия определяет, какой тип действия должен выполняться при перечислении визуальных объектов. Например, если вы вернете значение, <xref:System.Windows.Media.HitTestFilterBehavior.ContinueSkipSelfAndChildren>можно удалить текущий визуальный объект и его детей из перечисления результатов хит-теста. Это означает, что функция обратного вызова результатов проверки попадания не увидит эти объекты в перечислении. Обрезка визуального дерева объектов позволяет уменьшить объем обработки во время перечисления результатов проверки попадания. В следующем примере кода фильтр пропускает метки и их потомков и проверяет все остальные объекты.  
  
 [!code-csharp[HitTestingOverview#106](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#106)]
 [!code-vb[HitTestingOverview#106](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#106)]  
  
> [!NOTE]
> Функция обратного вызова фильтра проверки попадания иногда вызывается в случаях, когда функция обратного вызова результатов проверки попадания не вызывается.  
  
<a name="overriding_default_hit_testing"></a>
## <a name="overriding-default-hit-testing"></a>Переопределение проверки попадания по умолчанию  
 Вы можете переопределить поддержку тестирования визуального объекта <xref:System.Windows.Media.Visual.HitTestCore%2A> по умолчанию, переопределив метод. Это означает, что при <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> вызове метода вызывается перезавереденная <xref:System.Windows.Media.Visual.HitTestCore%2A> реализация. Переопределенный метод вызывается при попадании в ограничивающий прямоугольник визуального объекта, даже если координата не попадает в отображаемое содержимое визуального объекта.  
  
 [!code-csharp[HitTestingOverview#107](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#107)]
 [!code-vb[HitTestingOverview#107](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#107)]  
  
 Иногда может понадобиться проверка попадания как для ограничивающего прямоугольника, так и для отображаемого содержимого визуального объекта. Используя значение `PointHitTestParameters` параметра в <xref:System.Windows.Media.Visual.HitTestCore%2A> переизданном методе <xref:System.Windows.Media.Visual.HitTestCore%2A>в качестве параметра базового метода, можно выполнить действия, основанные на ударе ограничивающего прямоугольника визуального объекта, а затем выполнить второй тест удара против отрисованном содержимого визуального объекта.  
  
 [!code-csharp[HitTestingOverview#108](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#108)]
 [!code-vb[HitTestingOverview#108](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#108)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- <xref:System.Windows.Media.HitTestResult>
- <xref:System.Windows.Media.HitTestResultCallback>
- <xref:System.Windows.Media.HitTestFilterCallback>
- <xref:System.Windows.UIElement.IsHitTestVisible%2A>
- [Пример проверки попадания с использованием DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)
- [Проверка нажатия с помощью примера взаимодействия Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [Проверка попадания геометрического объекта в визуальный объект](how-to-hit-test-geometry-in-a-visual.md)
- [Проверка попадания с использованием контейнера узла Win32](how-to-hit-test-using-a-win32-host-container.md)
