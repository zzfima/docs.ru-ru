---
title: 3D Графика Обзор
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D graphics [WPF]
- graphics [WPF], 3D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: b8a3876030c533dd37eca0b00ebd50bccf309e53
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112392"
---
# <a name="3d-graphics-overview"></a>3D Графика Обзор
<a name="introduction"></a>Функциональность 3D [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяет разработчикам рисовать, трансформировать и анимировать 3D-графику как в разметке, так и в процедурном коде. Разработчики могут комбинировать 2D и 3D-графики для создания богатых элементов управления, предоставлять сложные иллюстрации данных или улучшать пользовательский опыт интерфейса приложения. 3D-поддержка [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не предназначена для обеспечения полнофункциональных игр-платформы развития. Эта тема содержит обзор 3D функциональности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в графической системе.  

<a name="threed_in_2d"></a>
## <a name="3d-in-a-2d-container"></a>3D в 2D контейнере  
 3D графический [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] контент в инкапсулируется в элементе, <xref:System.Windows.Controls.Viewport3D>который может участвовать в двухмерной структуре элемента. Графическая система <xref:System.Windows.Controls.Viewport3D> рассматривает как двумерный визуальный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]элемент, как и многие другие в . <xref:System.Windows.Controls.Viewport3D>функционирует как окно-вид порт в трехмерную сцену. Точнее, это поверхность, на которой проецируется 3D-сцена.  
  
 В обычном 2D-приложении используйте <xref:System.Windows.Controls.Viewport3D> другой элемент контейнера, такой как Grid или Canvas.  Хотя вы <xref:System.Windows.Controls.Viewport3D> можете использовать с другими 2D-объектами рисования в том же <xref:System.Windows.Controls.Viewport3D>графике сцены, вы не можете пересекать 2D и 3D объекты в пределах .  Эта тема будет сосредоточена на том, <xref:System.Windows.Controls.Viewport3D>как нарисовать 3D графики внутри .  
  
<a name="coord_space"></a>
## <a name="3d-coordinate-space"></a>3D Координация пространства  
 Система [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] координат для 2D графики находит происхождение в верхнем левом углу области рендеринга (обычно экран). В 2D-системе положительные значения x-оси идут вправо, а положительные значения y-оси продолжаются вниз.  В системе 3D-координат, однако, происхождение находится в центре области рендеринга, с положительными значениями x-оси, протекающими вправо, но положительные значения y-оси, протекающими вверх, и положительными значениями z-оси, исходящими наружу от происхождения, к зрителю.  
  
 ![Системы координат](./media/coordsystem-1.png "CoordSystem-1")  
Обычные 2D и 3D-координатные представления системы  
  
 Пространство, определяемое этими осями, является [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]стационарной рамкой отсчета для 3D-объектов в . При построении моделей в этом пространстве и создании источников света и камер для их отображения необходимо отличать стационарную систему отсчета координат ("мировую систему координат") от локальной системы отсчета, которая создается для каждой модели при применении к ней преобразований. Помните, что в зависимости от освещения и настроек камеры объекты в мировой системе координат могут выглядеть различным образом или быть полностью невидимыми. При этом положение камеры не изменяет расположения объектов в мировой системе координат.  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>Камеры и проекции  
 Разработчики, которые работают в 2D, привыкли позиционировать рисование примитивов на двумерном экране. При создании 3D-сцены важно помнить, что вы действительно создаете 2D-представление 3D-объектов. Поскольку 3D-сцена выглядит по-разному в зависимости от точки зрения зрителя, необходимо указать эту точку зрения. Класс <xref:System.Windows.Media.Media3D.Camera> позволяет указать эту точку зрения для 3D-сцены.  
  
 Другой способ понять, как 3D-сцена представлена на 2D-поверхности, описывая сцену как проекцию на поверхность обзора. Позволяет <xref:System.Windows.Media.Media3D.ProjectionCamera> указать различные проекции и их свойства, чтобы изменить, как он видит 3D-модели. Оговаривается <xref:System.Windows.Media.Media3D.PerspectiveCamera> проекция, которая предчеркает сцену.  Другими словами, <xref:System.Windows.Media.Media3D.PerspectiveCamera> обеспечивает перспективу исчезающей точки.  Можно указать положение камеры в пространстве координат сцены, направление и поле зрения камеры и вектор, определяющий направление "вверх" в сцене. Следующая диаграмма иллюстрирует <xref:System.Windows.Media.Media3D.PerspectiveCamera>проекцию 's.  
  
 Свойства <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> и <xref:System.Windows.Media.Media3D.ProjectionCamera> свойства ограничивают диапазон проекции камеры. Поскольку камеры могут быть расположены в любом месте сцены, фактически можно расположить камеру внутри модели или очень близко от нее, что усложняет правильное распознавание объекта.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>позволяет указать минимальное расстояние от камеры, за пределами которой объекты не будут нарисованы.  И наоборот, позволяет указать расстояние от камеры, за пределами которой объекты не будут нарисованы, что гарантирует, <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> что объекты слишком далеко, чтобы быть узнаваемыми не будут включены в сцену.  
  
 ![Настройка камеры](./media/coordsystem-6.png "CoordSystem-6")  
Позиция камеры  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>определяет ортогональную проекцию 3D-модели на 2D-поверхность. Подобно другим камерам, она указывает позицию, направление просмотра и направление "вверх". В <xref:System.Windows.Media.Media3D.PerspectiveCamera>отличие <xref:System.Windows.Media.Media3D.OrthographicCamera> от , однако, описывает проекцию, которая не включает в себя перспективу foreshortening. Другими словами, описывается смотровая коробка, <xref:System.Windows.Media.Media3D.OrthographicCamera> стороны которой параллельны, а не та, стороны которой встречаются в точке на камеру. Следующее изображение показывает ту же <xref:System.Windows.Media.Media3D.PerspectiveCamera> <xref:System.Windows.Media.Media3D.OrthographicCamera>модель, что и просмотрение с помощью и .  
  
 ![Ортогональная и перспективная проекции](./media/camera-projections4.png "Camera_projections4")  
Перспективная и ортогональная проекции  
  
 В следующем коде показано несколько обычных параметров камеры.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>Примитивы модели и сетки  
  
 <xref:System.Windows.Media.Media3D.Model3D>— это абстрактный базовый класс, представляющий общий 3D-объект. Чтобы создать 3D-сцену, необходимо просмотреть некоторые объекты, а объекты, которые составляют график сцены, вытекают из. <xref:System.Windows.Media.Media3D.Model3D> В настоящее время поддерживает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Media.Media3D.GeometryModel3D>моделирование геометрии с . Свойство <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> этой модели принимает примитивную сетку.  
  
 Начните построение модели с создания примитива, или сетки. Трехмерный примитив — это коллекция вершин, которые формируют одну трехмерную фигуру. Большинство 3D-систем предоставляют примитивы по образцу простейшой закрытой фигуры: треугольник, определяемый тремя вершинами.  Поскольку три точки треугольника лежат в одной плоскости, можно добавлять треугольники для моделирования более сложных фигур, называемых сетками.  
  
 3D-система [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в <xref:System.Windows.Media.Media3D.MeshGeometry3D> настоящее время предоставляет класс, что позволяет указать любую геометрию; в настоящее время он не поддерживает предопределенные 3D примитивы, такие как сферы и кубические формы. Начните <xref:System.Windows.Media.Media3D.MeshGeometry3D> создавать, указав список треугольников <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> vertices в качестве своего свойства. Каждая вершина указана как <xref:System.Windows.Media.Media3D.Point3D>.  (В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], указать это свойство как список чисел, сгруппированных в тройки, которые представляют координаты каждой вершины.) В зависимости от геометрии, ваша сетка может состоять из множества треугольников, некоторые из которых имеют одни и те же углы (вертики). Чтобы нарисовать сетку правильно, приложению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] необходимы сведения о том, какие вершины треугольников являются общими. Вы предоставляете эту информацию, указав список <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> индексов треугольника с свойством. В этом списке определяется порядок, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> в котором точки, указанные в списке, будут определять треугольник.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 В предыдущем примере <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> список определяет восемь вершин для определения сетки в форме куба. Свойство <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> определяет список из двенадцати групп по три индекса.  Каждое число в списке относится к смещению в список. <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>  Например, первые три вершины, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> указанные в списке, являются (1,1,0), (0,1,0) и (0,0,0). Первые три индекса, указанные в списке, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 0, 2 и 1, которые соответствуют <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> первому, третьему и второму пунктам в списке. В результате первый треугольник, формирующий модель куба, будет составлен из вершин (1, 1, 0), (0, 1, 0) и (0, 0, 0), а оставшиеся одиннадцать треугольников будут определяться аналогичным образом.  
  
 Можно продолжить определение модели, указав значения <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> для и свойств.  Для отображения поверхности модели графической системе требуются данные о том, какое направление поверхности является лицевым для любого данного треугольника. Система использует эти сведения для вычислений освещения модели: поверхности, обращенные к источнику освещения, отображаются ярче, чем поверхности, расположенные под углом к освещению. Хотя приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может определить векторы нормали по умолчанию, используя координаты позиции, можно также задавать различные векторы нормали для аппроксимации вида кривых поверхностей.  
  
 Свойство <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> определяет коллекцию <xref:System.Windows.Point>s, которые говорят графической системе, как сопоставить координаты, которые определяют, как текстура обращается к вершинам сетки. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>указаны как значение от нуля до 1, включительно.  Как и <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> в случае с свойством, графическая система может вычислить координаты текстурпов по умолчанию, но можно настроить различные координаты текстуры для управления картографией текстуры, которая включает в себя часть повторяющегося шаблона, например. Дополнительные сведения о координатах текстуры можно найти в последующих разделах или в пакете Managed Direct3D SDK.  
  
 В следующем примере показано создание одной грани модели куба в процедурном коде. Обратите внимание, что можно нарисовать весь куб как один объект GeometryModel3D; в этом примере грань куба отображается как отдельная модель для того, чтобы далее применить отдельные текстуры для каждой грани.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>'
## <a name="applying-materials-to-the-model"></a>Применение материалов к модели  
  
 Чтобы сетка выглядела как объект в трехмерном пространстве, к ней необходимо применить текстуру, которая покрывает поверхность, определенную ее вершинами и треугольниками. В этом случае можно осветить эту поверхность и создать ее проекцию с помощью камеры. В 2D класс <xref:System.Windows.Media.Brush> используется для нанесения цветов, узоров, градиентов или другого визуального содержимого к областям экрана.  Появление 3D-объектов, однако, является функцией модели освещения, а не только цвета или шаблона, применяемого к ним. Реальные объекты отражают свет неодинаково, в зависимости от качества поверхностей: гладкие и глянцевые поверхности выглядят иначе, чем неровные и матовые, также одни объекты поглощают свет, в то время как другие — отражают. Вы можете применять все те же кисти к 3D-объектам, которые можно применить к 2D-объектам, но вы не можете применить их напрямую.  
  
 Для определения характеристик поверхности модели [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используется <xref:System.Windows.Media.Media3D.Material> абстрактный класс. Конкретные подклассы класса Material определяют некоторые характеристики внешнего вида поверхности модели, и каждый из них предоставляет свойство Brush, которому можно передать значение SolidColorBrush, TileBrush или VisualBrush.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial>уточняется, что кисть будет применена к модели, как будто эта модель была освещена диффузно. Использование DiffuseMaterial больше всего напоминает использование кистей непосредственно на 2D-моделях; поверхности модели не отражают свет, как будто блестящие.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial>уточняется, что кисть будет применена к модели, как будто поверхность модели была твердой или блестящей, способной отражать блики. Вы можете установить степень, в которой текстура будет предлагать это отражающее качество, <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> или "блеск", указав значение для свойства.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial>позволяет указать, что текстура будет применяться так, как будто модель излучает свет, равный цвету кисти. Это не делает модель светящейся; однако это иначе влияет на затенение, чем если бы текстура была создана с помощью класса DiffuseMaterial или SpecularMaterial.  
  
 Для повышения производительности, задние грани <xref:System.Windows.Media.Media3D.GeometryModel3D> (те лица, которые находятся вне поля зрения, потому что они находятся на противоположной стороне модели от камеры) отбираются со сцены.  Чтобы указать <xref:System.Windows.Media.Media3D.Material> для применения к задней грани модели, как <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> плоскость, установите свойство модели.  
  
 Для достижения некоторых свойств поверхности, таких как свечение или эффект отражения, можно последовательно применить к модели несколько различных кистей. Вы можете применить и повторно использовать <xref:System.Windows.Media.Media3D.MaterialGroup> несколько материалов с помощью класса. Дочерние элементы класса MaterialGroup применяются от первого к последнему в нескольких проходах отрисовки.  
  
 Следующие примеры кода показывают, как применять твердый цвет и рисунок в виде кистей к 3D-моделям.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  ' [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
 ' [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
  [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>Освещение сцены  
 Свет в 3D-графике делает то, что огни делают в реальном мире: они делают поверхности видимыми. Более того, источники света определяют, какая часть сцены будет включена в проекцию. Объекты источников света в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создают различные эффекты света и тени. Они смоделированы на основе поведения различных реальных источников света. Сцена должна включать как минимум один источник света, иначе модели будут невидимыми.  
  
 Следующие огни вытекают <xref:System.Windows.Media.Media3D.Light>из базового класса:  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: Обеспечивает окружающее освещение, которое равномерно освещает все объекты независимо от их местонахождения или ориентации.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: Освещает, как далекий источник света.  Направленные огни <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> имеют указанный как Vector3D, но не указанное местоположение.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: Освещает, как близлежащий источник света. Источники света PointLights занимают определенное положение и испускают свет из этого положения. Объекты на сцене освещаются в зависимости от их положения и расстояния относительно источника света. <xref:System.Windows.Media.Media3D.PointLightBase>подвергает свойство, <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> которое определяет расстояние, за которым модели не будут освещены светом. Класс PointLight также предоставляет свойства затухания, определяющие интенсивность ослабления источника света в зависимости от расстояния. Можно указать константу, линейную или квадратичную интерполяцию затухания источника света.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: Наследует <xref:System.Windows.Media.Media3D.PointLight>от . Источники света Spotlight освещают сцену подобно источникам света и также имеют расположение и направление. Они проектировать свет в конусообразной <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> области, установленной и свойства, указанные в градусах.  
  
 Свет <xref:System.Windows.Media.Media3D.Model3D> — это объекты, поэтому вы можете преобразовывать и анимировать световые свойства, включая положение, цвет, направление и диапазон.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>Преобразование моделей  
 При создании моделей в сцене им задается определенное местоположение. Для поворота моделей, изменения их размера или перемещения внутри сцены не следует изменять вершины, определяющие сами модели.  Вместо этого, как и в 2D, вы применяете преобразования к моделям.  
  
 Каждый объект <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> модели имеет свойство, с помощью которого можно перемещать, переориентировать или изменить размер модели.  При применении преобразования все точки модели фактически смещаются с помощью определенного вектора или значения, заданного преобразованием. Другими словами, выполняется преобразование координатного пространства, в котором определена модель ("пространство модели"), при этом значения, составляющие геометрию модели в системе координат всей сцены ("мировое пространство"), не изменяются.  
  
 Для получения дополнительной информации о преобразовании моделей, см [3D Преобразования Обзор](3-d-transformations-overview.md).  
  
<a name="animations"></a>
## <a name="animating-models"></a>Анимация моделей  
 3D-реализация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] участвует в той же системе синхронизации и анимации, что и 2D-графика. Другими словами, чтобы оживить 3D-сцену, оживить свойства своих моделей. Можно непосредственно анимировать свойства примитивов, но обычно проще анимировать преобразования, изменяющие позицию или внешний вид моделей. Поскольку преобразования могут <xref:System.Windows.Media.Media3D.Model3DGroup> быть применены к объектам, а также отдельным моделям, можно применить один набор анимаций к ребенку Model3DGroup и другой набор анимаций к группе детских объектов. Также можно добиться разнообразных визуальных эффектов, анимируя свойства элементов освещения сцены. Наконец, можно анимировать саму проекцию, изменяя положение камеры или поле зрения. Дополнительные сведения о системе времени и анимации в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделах [Общие сведения об эффектах анимации](animation-overview.md), [Общие сведения о Storyboard](storyboards-overview.md) и [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 Для анимации объекта в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создайте временную шкалу, определите анимацию (которая изменяет значение некоторого свойства во времени) и укажите свойство, к которому применяется анимация. Поскольку все объекты в 3D-сцене являются <xref:System.Windows.Controls.Viewport3D>детьми, свойства, на которые нацелена любая анимация, которую вы хотите применить к сцене, являются свойствами свойств Viewport3D.  
  
 Предположим, требуется создать качающуюся на месте модель. Вы можете применить <xref:System.Windows.Media.Media3D.RotateTransform3D> к модели и оживить ось ее вращения от одного вектора к другому. В следующем примере кода демонстрируется применение Vector3DAnimation к свойству Axis преобразования элемента Rotation3D, при условии что RotateTransform3D будет одним из нескольких преобразований, применяемых к модели с TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>
## <a name="add-3d-content-to-the-window"></a>Добавление 3D-контента в окно  
 Чтобы отобразить сцену, добавьте модели <xref:System.Windows.Media.Media3D.Model3DGroup> и <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> огни <xref:System.Windows.Media.Media3D.ModelVisual3D> <xref:System.Windows.Media.Media3D.Model3DGroup>в, затем установите как . Добавить <xref:System.Windows.Media.Media3D.ModelVisual3D> в <xref:System.Windows.Controls.Viewport3D.Children%2A> коллекцию <xref:System.Windows.Controls.Viewport3D>. Добавьте камеры <xref:System.Windows.Controls.Viewport3D> к, <xref:System.Windows.Controls.Viewport3D.Camera%2A> установив его свойство.  
  
 Наконец, <xref:System.Windows.Controls.Viewport3D> добавьте в окно. Когда <xref:System.Windows.Controls.Viewport3D> включено в качестве содержимого элемента макета, такого как Canvas, <xref:System.Windows.FrameworkElement.Height%2A> укажите размер Viewport3D, установив его и <xref:System.Windows.FrameworkElement.Width%2A> свойства (унаследованные от). <xref:System.Windows.FrameworkElement>  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [Обзор 3D трансформаций](3-d-transformations-overview.md)
- [Достижение максимальной производительности WPF 3D](maximize-wpf-3d-performance.md)
- [Как-к темам](3-d-graphics-how-to-topics.md)
- [Общие сведения о фигурах и базовых средствах рисования в WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
