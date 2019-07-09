---
title: Обзор трехмерной графики
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D graphics [WPF]
- graphics [WPF], 3-D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: 48f14ff145ad35dae3ba960191d34360cbec6173
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664099"
---
# <a name="3-d-graphics-overview"></a>Обзор трехмерной графики
<a name="introduction"></a> Трехмерной функциональные возможности в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяет разработчикам рисовать, преобразовывать и анимировать трехмерную графику как в разметке и в процедурном коде. Разработчики могут сочетать двумерной и трехмерной графики для создания многофункциональных элементов управления, предоставления сложных визуальных представлений данных или повысить удобство работы пользователей из интерфейса приложения. Поддержка 3-D в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не предполагает предоставления полнофункциональной платформы разработки игр для. В этом разделе представлен обзор трехмерной функциональные возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] графической системе.  

<a name="threed_in_2d"></a>   
## <a name="3-d-in-a-2-d-container"></a>Трехмерное содержимое в двумерном контейнере  
 Трехмерное графическое содержимое в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] инкапсулировано в элементе, <xref:System.Windows.Controls.Viewport3D>, который может участвовать в структуре двумерного элемента. Графическая система рассматривает <xref:System.Windows.Controls.Viewport3D> как двумерный визуальный элемент, подобный многим другим в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.Viewport3D> функционирует как окно — окно просмотра — трехмерной сцены. Говоря точнее, это поверхность, на которую проецируется трехмерная сцена.  
  
 В стандартном приложении 2-D, использовать <xref:System.Windows.Controls.Viewport3D> как другой контейнерный элемент, например Grid или Canvas.  Несмотря на то, что можно использовать <xref:System.Windows.Controls.Viewport3D> относительно других двухмерных графических объектов в том же графе сцены, нельзя сочетать двумерных и трехмерных объектов в <xref:System.Windows.Controls.Viewport3D>.  В этом разделе основное внимание уделяется способ рисования трехмерной графики внутри <xref:System.Windows.Controls.Viewport3D>.  
  
<a name="coord_space"></a>   
## <a name="3-d-coordinate-space"></a>Координаты трехмерного пространства  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Систему координат для двумерной графики начинается в левом верхнем углу области отрисовки (обычно экрана). В двумерной системе положительные значения оси X откладываются вправо, а оси Y — сверху вниз.  В трехмерной системе координат тем не менее, начало располагается в центре отрисовываемой области, положительные значения оси x справа, но значения оси y — снизу вверх и значения оси z — из источника , наблюдателю.  
  
 ![Системы координат](./media/coordsystem-1.png "CoordSystem-1")  
Представления традиционных двумерных и трехмерных систем координат  
  
 Пространство, определяемое этими осями, является стационарной системой отсчета координат для трехмерных объектов в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. При построении моделей в этом пространстве и создании источников света и камер для их отображения необходимо отличать стационарную систему отсчета координат ("мировую систему координат") от локальной системы отсчета, которая создается для каждой модели при применении к ней преобразований. Помните, что в зависимости от освещения и настроек камеры объекты в мировой системе координат могут выглядеть различным образом или быть полностью невидимыми. При этом положение камеры не изменяет расположения объектов в мировой системе координат.  
  
<a name="cameras"></a>   
## <a name="cameras-and-projections"></a>Камеры и проекции  
 Разработчики, работающие в 2-D привыкли к размещению графических примитивов на двумерном экране. При создании трехмерной сцены, важно помнить, что фактически создается представление 2-D трехмерных объектов. Поскольку трехмерной сцены выглядит по-разному в зависимости от точки наблюдения, необходимо указать эту точку наблюдения. <xref:System.Windows.Media.Media3D.Camera> Класса позволяет указать эту точку наблюдения для трехмерной сцены.  
  
 Другой способ понять, как трехмерная сцена представляется на двумерную поверхность — описание сцены как проекции на поверхность просмотра. <xref:System.Windows.Media.Media3D.ProjectionCamera> Позволяет указать различные проекции и их свойства для изменения, как наблюдатель видит трехмерных моделей. Объект <xref:System.Windows.Media.Media3D.PerspectiveCamera> указывает проекцию сцены в перспективе.  Другими словами <xref:System.Windows.Media.Media3D.PerspectiveCamera> предоставляет точку схода перспективы.  Можно указать положение камеры в пространстве координат сцены, направление и поле зрения камеры и вектор, определяющий направление "вверх" в сцене. На следующей схеме показана <xref:System.Windows.Media.Media3D.PerspectiveCamera>в проекции.  
  
 <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> И <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> свойства <xref:System.Windows.Media.Media3D.ProjectionCamera> ограничивают диапазон проекции камеры. Поскольку камеры могут быть расположены в любом месте сцены, фактически можно расположить камеру внутри модели или очень близко от нее, что усложняет правильное распознавание объекта.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> позволяет указать минимальное расстояние от камеры, за которым объекты не будут нарисованы.  И наоборот <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> позволяет задать расстояние от камеры, за которым объекты не будут нарисованы, что гарантирует, что объекты слишком далеко, чтобы распознаваться не будут включены в сцене.  
  
 ![Настройка камеры](./media/coordsystem-6.png "CoordSystem 6")  
Позиция камеры  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> указывает ортогональную проекцию трехмерной модели в рабочую область visual 2-D. Подобно другим камерам, она указывает позицию, направление просмотра и направление "вверх". В отличие от <xref:System.Windows.Media.Media3D.PerspectiveCamera>, но при этом <xref:System.Windows.Media.Media3D.OrthographicCamera> описывает проекцию, которая не включает ракурс перспективы. Другими словами <xref:System.Windows.Media.Media3D.OrthographicCamera> описывает призму, стороны которой параллельны, вместо одной стороны которой сходятся в точке камеры. На следующем рисунке показана ту же модель, отображенная с использованием <xref:System.Windows.Media.Media3D.PerspectiveCamera> и <xref:System.Windows.Media.Media3D.OrthographicCamera>.  
  
 ![Ортогональная и перспективная проекции](./media/camera-projections4.png "Camera_projections4")  
Перспективная и ортогональная проекции  
  
 В следующем коде показано несколько обычных параметров камеры.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## <a name="model-and-mesh-primitives"></a>Примитивы модели и сетки  
  
 <xref:System.Windows.Media.Media3D.Model3D> — Это абстрактный базовый класс, представляющий универсальный трехмерного объекта. Для создания трехмерной сцены, необходимо, чтобы некоторые объекты для отображения и объекты, составляющие граф сцены, являются производными от <xref:System.Windows.Media.Media3D.Model3D>. В настоящее время [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает моделирование геометрических объектов с <xref:System.Windows.Media.Media3D.GeometryModel3D>. <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Свойства этой модели принимает примитив сетки.  
  
 Начните построение модели с создания примитива, или сетки. Примитив трехмерной является коллекцией из вершин, образующих одну сущность 3-D. Большинство трехмерных систем предоставляют примитивы, смоделированные на основе простейшей замкнутой фигуры: треугольника, определенного тремя вершинами.  Поскольку три точки треугольника лежат в одной плоскости, можно добавлять треугольники для моделирования более сложных фигур, называемых сетками.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Трехмерная система в настоящее время предоставляет <xref:System.Windows.Media.Media3D.MeshGeometry3D> класс, позволяющий определить любую геометрическую; он не поддерживает предопределенные поддержки трехмерной примитивов, как сферы или кубические формы. Приступить к созданию <xref:System.Windows.Media.Media3D.MeshGeometry3D> путем определения списка вершин треугольников в качестве его <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> свойство. Каждая вершина задается как <xref:System.Windows.Media.Media3D.Point3D>.  (В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] укажите это свойство в виде списка чисел, сгруппированных тройками и представляющих координаты каждой вершины.) В зависимости от геометрического объекта сетка может состоять из множества треугольников, некоторые из которых совместно используют общие углы (вершины). Чтобы нарисовать сетку правильно, приложению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] необходимы сведения о том, какие вершины треугольников являются общими. Эту информацию, указав список индексов треугольников с <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> свойство. Этот список определяет порядок, в котором точки, указанные в <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> будут определять треугольник.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 В приведенном выше примере <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> список задает восемь вершин для определения сетки кубической формы. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Свойство указывает список двенадцати групп по три индекса.  Каждое число в списке определяет смещение в <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> списка.  Например, первыми тремя вершинами, определяемое <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> списка являются вершин (1,1,0), (0,1,0) и (0,0,0). Первыми тремя индексами, определяемое <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> списка: 0, 2 и 1, который соответствует первому, в-третьих и второму пунктам в <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> списка. В результате первый треугольник, формирующий модель куба, будет составлен из вершин (1, 1, 0), (0, 1, 0) и (0, 0, 0), а оставшиеся одиннадцать треугольников будут определяться аналогичным образом.  
  
 Можно продолжить определение модели путем указания значений для <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> и <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> свойства.  Для отображения поверхности модели графической системе требуются данные о том, какое направление поверхности является лицевым для любого данного треугольника. Система использует эти сведения для вычислений освещения модели: поверхности, обращенные к источнику освещения, отображаются ярче, чем поверхности, расположенные под углом к освещению. Хотя приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может определить векторы нормали по умолчанию, используя координаты позиции, можно также задавать различные векторы нормали для аппроксимации вида кривых поверхностей.  
  
 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> Свойство указывает коллекцию <xref:System.Windows.Point>, сообщающую графической системе, как сопоставить координаты, определяющие, как текстура будет нарисован вершин сетки. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> указываются как значение от 0 до 1 включительно.  Как и в <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> свойство, графическая система может вычислить координаты текстуры по умолчанию, но вы можете установить различные координаты текстуры для управления отображением текстуры, содержащей часть повторяющегося узора, например. Дополнительные сведения о координатах текстуры можно найти в последующих разделах или в пакете Managed Direct3D SDK.  
  
 В следующем примере показано создание одной грани модели куба в процедурном коде. Обратите внимание, что можно нарисовать весь куб как один объект GeometryModel3D; в этом примере грань куба отображается как отдельная модель для того, чтобы далее применить отдельные текстуры для каждой грани.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## <a name="applying-materials-to-the-model"></a>Применение материалов к модели  
  
 Чтобы сетка выглядела как объект в трехмерном пространстве, к ней необходимо применить текстуру, которая покрывает поверхность, определенную ее вершинами и треугольниками. В этом случае можно осветить эту поверхность и создать ее проекцию с помощью камеры. В 2-D, используется <xref:System.Windows.Media.Brush> класс для применения цветов, шаблоны, градиентов или другого визуального содержимого к участкам экрана.  Внешний вид трехмерных объектов, однако является функцией модели освещения, а не только цвета или узора, к которым применено. Реальные объекты отражают свет неодинаково, в зависимости от качества поверхностей: гладкие и глянцевые поверхности выглядят иначе, чем неровные и матовые, также одни объекты поглощают свет, в то время как другие — отражают. Вы можно применить те же кисти к трехмерным объектам, которые можно применить к объектам 2-D, но не может применить их напрямую.  
  
 Для определения характеристик поверхности модели [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует <xref:System.Windows.Media.Media3D.Material> абстрактного класса. Конкретные подклассы класса Material определяют некоторые характеристики внешнего вида поверхности модели, и каждый из них предоставляет свойство Brush, которому можно передать значение SolidColorBrush, TileBrush или VisualBrush.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial> Указывает, что кисть будет применена к модели, так, будто была освещена рассеянным светом. Использование DiffuseMaterial всего напоминает применение кистей непосредственно в моделях 2-D. поверхности модели не отражают свет, как блестящие.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial> Указывает, что кисть будет применена к модели, как если бы, если поверхность модели была твердой или блестящей, способной отражать блики. Можно задать степень, в которую текстуры предложит гладкости или «глянца», указав значение для <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> свойство.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial> позволяет указать, что текстура будет применяться, как если бы, если модель излучала свет на цвет кисти. Это не делает модель светящейся; однако это иначе влияет на затенение, чем если бы текстура была создана с помощью класса DiffuseMaterial или SpecularMaterial.  
  
 Для повышения производительности противоположные поверхности объекта <xref:System.Windows.Media.Media3D.GeometryModel3D> (грани, которые невидимы, поскольку они находятся на противоположной стороне модели относительно камеры) удаляются из сцены.  Чтобы указать <xref:System.Windows.Media.Media3D.Material> для применения к противоположной поверхности модели, например плоскости, установите в качестве модели <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> свойство.  
  
 Для достижения некоторых свойств поверхности, таких как свечение или эффект отражения, можно последовательно применить к модели несколько различных кистей. Можно применять и повторно использовать несколько материалов с помощью <xref:System.Windows.Media.Media3D.MaterialGroup> класса. Дочерние элементы класса MaterialGroup применяются от первого к последнему в нескольких проходах отрисовки.  
  
 В следующих примерах кода показано применение сплошного цвета и рисования с помощью кистей к трехмерным моделям.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## <a name="illuminating-the-scene"></a>Освещение сцены  
 Сделать освещения в трехмерной графики сделать в реальном мире источники света: они делают поверхности видимыми. Более того, источники света определяют, какая часть сцены будет включена в проекцию. Объекты источников света в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создают различные эффекты света и тени. Они смоделированы на основе поведения различных реальных источников света. Сцена должна включать как минимум один источник света, иначе модели будут невидимыми.  
  
 Указанные ниже источники света являются производными от базового класса <xref:System.Windows.Media.Media3D.Light>:  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: Предоставляет рассеянное освещение, при котором все объекты одинаково, независимо от их расположения или ориентации.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: Создает освещение, аналогичное удаленному источнику света.  Направленные источники света имеют <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> указан как объект Vector3D, но без заданного местоположения.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: Создает освещение, аналогичное источника света. Источники света PointLights занимают определенное положение и испускают свет из этого положения. Объекты на сцене освещаются в зависимости от их положения и расстояния относительно источника света. <xref:System.Windows.Media.Media3D.PointLightBase> предоставляет <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> свойство, которое определяет расстояние, далее которого модели не будут освещены светом. Класс PointLight также предоставляет свойства затухания, определяющие интенсивность ослабления источника света в зависимости от расстояния. Можно указать константу, линейную или квадратичную интерполяцию затухания источника света.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: Наследует от <xref:System.Windows.Media.Media3D.PointLight>. Источники света Spotlight освещают сцену подобно источникам света и также имеют расположение и направление. Они проектируют свет в конусообразную область, задается <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> и <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> свойства, заданная в градусах.  
  
 За освещение отвечают <xref:System.Windows.Media.Media3D.Model3D> объектов, поэтому можно преобразовывать и анимировать свойства источников света, включая положение, цвет, направление и диапазон.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## <a name="transforming-models"></a>Преобразование моделей  
 При создании моделей в сцене им задается определенное местоположение. Для поворота моделей, изменения их размера или перемещения внутри сцены не следует изменять вершины, определяющие сами модели.  Вместо этого следует применять к моделям преобразования, как и в двумерных системах.  
  
 Каждый объект модели имеет <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> свойства с помощью которого можно перемещать, повторно разобраться с функциональностью или изменении размера модели.  При применении преобразования все точки модели фактически смещаются с помощью определенного вектора или значения, заданного преобразованием. Другими словами, выполняется преобразование координатного пространства, в котором определена модель ("пространство модели"), при этом значения, составляющие геометрию модели в системе координат всей сцены ("мировое пространство"), не изменяются.  
  
 Дополнительные сведения о преобразовании моделей см. в разделе [Общие сведения о трехмерных преобразованиях](3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## <a name="animating-models"></a>Анимация моделей  
 Трехмерная реализация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] участвует в той же системе анимации и времени, что и двумерная графика. Другими словами, для анимации трехмерной сцены необходимо анимировать свойства ее моделей. Можно непосредственно анимировать свойства примитивов, но обычно проще анимировать преобразования, изменяющие позицию или внешний вид моделей. Поскольку преобразования можно применить и к <xref:System.Windows.Media.Media3D.Model3DGroup> объекты, а также отдельным моделям, это возможно применение одного набора анимаций к дочернему элементу Model3DGroup, а другого набора — к группе дочерних объектов. Также можно добиться разнообразных визуальных эффектов, анимируя свойства элементов освещения сцены. Наконец, можно анимировать саму проекцию, изменяя положение камеры или поле зрения. Дополнительные сведения о системе времени и анимации в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделах [Общие сведения об эффектах анимации](animation-overview.md), [Общие сведения о Storyboard](storyboards-overview.md) и [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 Для анимации объекта в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создайте временную шкалу, определите анимацию (которая изменяет значение некоторого свойства во времени) и укажите свойство, к которому применяется анимация. Поскольку все объекты в трехмерной сцене являются дочерними элементами <xref:System.Windows.Controls.Viewport3D>, необходимо применить в сцену анимация свойств являются свойствами свойств Viewport3D.  
  
 Предположим, требуется создать качающуюся на месте модель. Вы можете применить <xref:System.Windows.Media.Media3D.RotateTransform3D> в модель и анимировать ее ось вращения от одного вектора к другому. В следующем примере кода демонстрируется применение Vector3DAnimation к свойству Axis преобразования элемента Rotation3D, при условии что RotateTransform3D будет одним из нескольких преобразований, применяемых к модели с TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## <a name="add-3-d-content-to-the-window"></a>Добавление трехмерного содержимого в окно  
 Для отображения сцены добавьте модели и источники света для <xref:System.Windows.Media.Media3D.Model3DGroup>, затем установите <xref:System.Windows.Media.Media3D.Model3DGroup> как <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> из <xref:System.Windows.Media.Media3D.ModelVisual3D>. Добавить <xref:System.Windows.Media.Media3D.ModelVisual3D> для <xref:System.Windows.Controls.Viewport3D.Children%2A> коллекцию <xref:System.Windows.Controls.Viewport3D>. Добавьте камеры к <xref:System.Windows.Controls.Viewport3D> , задав его <xref:System.Windows.Controls.Viewport3D.Camera%2A> свойство.  
  
 Наконец, добавьте <xref:System.Windows.Controls.Viewport3D> в окно. Когда <xref:System.Windows.Controls.Viewport3D> включен содержимого элемента макета, такого как Canvas, укажите размер объекта Viewport3D, задав его <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> свойства (наследуется от <xref:System.Windows.FrameworkElement>).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [Общие сведения о трехмерных преобразованиях](3-d-transformations-overview.md)
- [Достижение максимальной производительности WPF 3D](maximize-wpf-3d-performance.md)
- [Разделы практического руководства](3-d-graphics-how-to-topics.md)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
