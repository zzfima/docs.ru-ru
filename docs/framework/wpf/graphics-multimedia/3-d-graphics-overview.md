---
title: "Обзор трехмерной графики | Microsoft Docs"
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
  - "трехмерная"
  - "графика [WPF], трехмерный"
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Обзор трехмерной графики
<a name="introduction"></a> Функциональные возможности [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] системы [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяют разработчикам рисовать, преобразовывать и анимировать трехмерную графику как в разметке, так и в процедурном коде.  Разработчики могут сочетать графику [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] и [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] для создания многофункциональных элементов управления, предоставления сложных визуальных представлений данных или повышения удобства работы с интерфейсом приложения. Поддержка [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не предполагает предоставления полнофункциональной платформы для создания игр. В этом разделе содержатся общие сведения о функциональных возможностях [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] в графической системе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="threed_in_2d"></a>   
## 3\-D в контейнере 2\-D  
 Графическое содержимое [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] инкапсулировано в элементе <xref:System.Windows.Controls.Viewport3D>, который может участвовать в структуре двумерного элемента.  Графическая система рассматривает <xref:System.Windows.Controls.Viewport3D> как двухмерный визуальный элемент, подобный многим другим в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.Windows.Controls.Viewport3D> функционирует как окно — окно просмотра — трехмерной сцены.  Говоря точнее, это поверхность, на которую проецируется сцена [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 В традиционном приложении [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] элемент <xref:System.Windows.Controls.Viewport3D> используется как любой другой контейнерный элемент, например "Grid" или "Canvas".  Хотя элемент <xref:System.Windows.Controls.Viewport3D> можно использовать с другими графическими объектами [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] в том же графе сцены, нельзя сочетать объекты [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] и [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] внутри элемента <xref:System.Windows.Controls.Viewport3D>.  Этот раздел будет посвящен рисованию [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] графики внутри объекта <xref:System.Windows.Controls.Viewport3D>.  
  
<a name="coord_space"></a>   
## Координаты трехмерного пространства  
 Начало системы координат [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для графики [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] отсчитывается от левого верхнего угла области отрисовки \(обычно экрана\).  В системе [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] положительные значения оси x откладываются вправо, а положительные значения оси y — сверху вниз.  Однако в системе координат [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] начало располагается в центре отрисовываемой области, положительные значения оси x откладываются вправо, оси y — снизу вверх, а оси z — из центра к наблюдателю.  
  
 ![Системы координат](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-1.png "CoordSystem\-1")  
Представления традиционных двухмерных и трехмерных систем координат  
  
 Пространство, определяемое этими осями, является стационарной системой отсчета координат для объектов [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  При построении моделей в этом пространстве и создании источников света и камер для их отображения необходимо отличать стационарную систему отсчета координат \("мировую систему координат"\) от локальной системы отсчета, которая создается для каждой модели при применении к ней преобразований.  Помните, что в зависимости от освещения и настроек камеры объекты в мировой системе координат могут выглядеть различным образом или быть полностью невидимыми. При этом положение камеры не изменяет расположения объектов в мировой системе координат.  
  
<a name="cameras"></a>   
## Камеры и проекции  
 Разработчики, работающие в координатах [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], привыкли к размещению графических примитивов на двухмерном экране.  При создании сцены [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] важно помнить, что фактически создается представление [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] объектов [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  Поскольку сцена [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] выглядит по\-разному в зависимости от точки наблюдения, необходимо указать эту точку наблюдения.  Указать эту точку наблюдения для сцены [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] позволяет класс <xref:System.Windows.Media.Media3D.Camera>.  
  
 Другой способ понимания того, как представляется сцена [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] на поверхности [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], — это описание сцены как проекции на поверхность просмотра.  Камера <xref:System.Windows.Media.Media3D.ProjectionCamera> позволяет указать различные проекции и их свойства для изменения того, как наблюдатель видит модели [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  Камера <xref:System.Windows.Media.Media3D.PerspectiveCamera> указывает проекцию сцены в перспективе.  Другими словами, камера <xref:System.Windows.Media.Media3D.PerspectiveCamera> предоставляет точку схода перспективы.  Можно указать положение камеры в пространстве координат сцены, направление и поле зрения камеры и вектор, определяющий направление "вверх" в сцене.  Следующая схема иллюстрирует проекции <xref:System.Windows.Media.Media3D.PerspectiveCamera>.  
  
 Свойства <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> и <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> камеры <xref:System.Windows.Media.Media3D.ProjectionCamera> ограничивают диапазон проекции камеры.  Поскольку камеры могут быть расположены в любом месте сцены, фактически можно расположить камеру внутри модели или очень близко от нее, что усложняет правильное распознавание объекта.  Свойство <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> позволяет определить минимальное расстояние от камеры, за которым не будут располагаться объекты.  И наоборот, свойство <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> позволяет задать расстояние от камеры, дальше которого объекты не будут нарисованы; это гарантирует, что объекты, расположенные слишком далеко для распознавания, не будут включены в сцену.  
  
 ![Настройка камеры](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-6.png "CoordSystem\-6")  
Позиция камеры  
  
 Камера <xref:System.Windows.Media.Media3D.OrthographicCamera> указывает ортогональную проекцию модели [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] на визуальную поверхность [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)].  Подобно другим камерам, она указывает позицию, направление просмотра и направление "вверх".  Однако в отличие от камеры <xref:System.Windows.Media.Media3D.PerspectiveCamera>, камера <xref:System.Windows.Media.Media3D.OrthographicCamera> описывает проекцию, которая не включает ракурс перспективы.  Другими словами, камера <xref:System.Windows.Media.Media3D.OrthographicCamera> описывает призму, стороны которой параллельны, вместо призмы, стороны которой сходятся в точке камеры.  На следующем рисунке показана одна модель, отображенная с использованием камер <xref:System.Windows.Media.Media3D.PerspectiveCamera> и <xref:System.Windows.Media.Media3D.OrthographicCamera>.  
  
 ![Ортогональная и перспективная проекции](../../../../docs/framework/wpf/graphics-multimedia/media/camera-projections4.png "Camera\_projections4")  
Перспективная и ортогональная проекции  
  
 В следующем коде показано несколько обычных параметров камеры.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## Примитивы модели и сетки  
 <xref:System.Windows.Media.Media3D.Model3D> — это абстрактный базовый класс, представляющий универсальный объект [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  Чтобы построить сцену [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], необходимо, чтобы некоторые объекты для отображения и объекты, составляющие граф сцены, наследовали от класса <xref:System.Windows.Media.Media3D.Model3D>.  В настоящее время приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает моделирование геометрических объектов с помощью класса <xref:System.Windows.Media.Media3D.GeometryModel3D>.  Свойство <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> данной модели принимает примитив сетки.  
  
 Начните построение модели с создания примитива, или сетки.  Примитив [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] представляет собой набор вершин, образующих одну сущность [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  Большинство систем [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] предоставляют примитивы, смоделированные на основе простейшей замкнутой фигуры: треугольника, определенного тремя вершинами.  Поскольку три точки треугольника лежат в одной плоскости, можно добавлять треугольники для моделирования более сложных фигур, называемых сетками.  
  
 Текущая система [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет класс <xref:System.Windows.Media.Media3D.MeshGeometry3D>, позволяющий определить любую геометрическую форму; в настоящее время не поддерживаются примитивы [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], такие как сферы или кубические формы.  Начните создание класса <xref:System.Windows.Media.Media3D.MeshGeometry3D> с определения списка вершин треугольников в качестве свойства <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>.  Каждая вершина задается как свойство <xref:System.Windows.Media.Media3D.Point3D>.  \(В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] укажите это свойство в виде списка чисел, сгруппированных тройками и представляющих координаты каждой вершины.\) В зависимости от геометрического объекта, сетка может состоять из множества треугольников, некоторые из которых совместно используют общие углы \(вершины\).  Чтобы нарисовать сетку правильно, приложению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] требуются данные о том, какие вершины треугольников являются общими.  Предоставить эти данные можно, указав список индексов треугольников в свойстве <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>.  Этот список определяет порядок, в котором точки, указанные в списке <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, будут определять треугольник.  
  
 [!code-xml[basic3d#Basic3DXAML3DN3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 В предыдущем примере список <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> задает восемь вершин для определения сетки кубической формы.  Свойство <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> указывает список двенадцати групп по три индекса.  Каждое число в списке определяет смещение в списке <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>.  Например, первыми тремя вершинами, заданными списком <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, являются \(1,1,0\), \(0,1,0\) и \(0,0,0\).  Первыми тремя индексами, заданными <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, являются 0, 2 и 1, что соответствует первому, третьему и второму пунктам в списке <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>.  В результате, первый треугольник, формирующий модель куба, будет составлен из вершин \(1,1,0\), \(0,1,0\) и \(0,0,0\), а оставшиеся одиннадцать треугольников будут определяться аналогичным образом.  
  
 Можно продолжить определение модели путем указания значений свойств <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> и <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>.  Для отображения поверхности модели графической системе требуются данные о том, какое направление поверхности является лицевым для любого данного треугольника.  Система использует эти сведения для вычислений освещения модели: поверхности, обращенные к источнику освещения, отображаются ярче, чем поверхности, расположенные под углом к освещению.  Хотя приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может определить векторы нормали по умолчанию, используя координаты позиции, можно задавать различные векторы нормали для аппроксимации вида кривых поверхностей.  
  
 Свойство <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> указывает коллекцию объектов <xref:System.Windows.Point>, сообщающую графической системе, каким образом сопоставлять координаты, определяющие отображение текстуры, с вершинами сетки.  Свойства <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> задаются как значение от нуля до 1 включительно.  Также как и со свойством <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, графическая система может вычислить координаты текстуры по умолчанию, но можно установить различные координаты текстуры, например, для управления отображением текстуры, содержащей часть повторяющегося узора.  Дополнительные сведения о координатах текстуры можно найти в последующих разделах или в пакете Managed Direct3D SDK.  
  
 В следующем примере показано создание одной грани модели куба в процедурном коде.  Обратите внимание, что можно нарисовать весь куб как один объект GeometryModel3D; в этом примере грань куба отображается как отдельная модель для того, чтобы далее применить отдельные текстуры для каждой грани.  
  
 [!code-csharp[3doverview#3DOverview3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## Применение материалов к модели  
 Чтобы сетка выглядела как объект в трехмерном пространстве, к ней необходимо применить текстуру, которая покрывает поверхность, определенную ее вершинами и треугольниками. В этом случае можно осветить эту поверхность и создать ее проекцию с помощью камеры.  В объектах [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] для применения цветов, узоров, градиентов или другого визуального содержимого к участкам экрана можно использовать класс <xref:System.Windows.Media.Brush>.  Однако вешний вид объектов [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] является функцией модели освещения, а не только примененного к ним цвета или узора.  Реальные объекты отражают свет неодинаково, в зависимости от качества поверхностей: гладкие и глянцевые поверхности выглядят иначе, чем неровные и матовые, также одни объекты поглощают свет, в то время как другие — отражают.  К объектам [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] можно применить те же кисти, что и к объектам [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], но применить их напрямую невозможно.  
  
 Для определения характеристик поверхности модели приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует абстрактный класс <xref:System.Windows.Media.Media3D.Material>.  Конкретные подклассы класса "Material" определяют некоторые характеристики внешнего вида поверхности модели, и каждый из них предоставляет свойство "Brush", которому можно передать значение "SolidColorBrush", "TileBrush" или "VisualBrush".  
  
-   Класс <xref:System.Windows.Media.Media3D.DiffuseMaterial> определяет, что кисть будет применена к модели, как если бы она была освещена рассеянным светом.  Использование класса "DiffuseMaterial" больше всего напоминает применение кистей непосредственно в моделях [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]; поверхности модели не отражают свет, как блестящие поверхности.  
  
-   Класс <xref:System.Windows.Media.Media3D.SpecularMaterial> определяет, что кисть будет применена к модели, как если бы поверхность модели была твердой или блестящей, способной отражать блики.  Можно установить степень гладкости или "глянца" текстуры, задав значение свойства <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A>.  
  
-   Класс <xref:System.Windows.Media.Media3D.EmissiveMaterial> позволяет указать, что текстура будет применена, как если бы модель излучала свет, эквивалентный цвету кисти.  Это не делает модель светящейся; однако это иначе влияет на затенение, чем если бы текстура была создана с помощью класса "DiffuseMaterial" или "SpecularMaterial".  
  
 Для повышения производительности противоположные поверхности объекта <xref:System.Windows.Media.Media3D.GeometryModel3D> \(грани, которые невидимы, поскольку находятся на противоположной стороне модели относительно камеры\) удаляются из сцены.  Чтобы указать класс <xref:System.Windows.Media.Media3D.Material> для применения к противоположной поверхности модели, например плоскости, задайте свойство <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> модели.  
  
 Для достижения некоторых свойств поверхности, таких как свечение или эффект отражения, можно последовательно применить к модели несколько различных кистей.  Можно применять и повторно использовать несколько материалов с помощью класса <xref:System.Windows.Media.Media3D.MaterialGroup>.  Дочерние элементы класса "MaterialGroup" применяются от первого к последнему в нескольких проходах отрисовки.  
  
 Следующий пример кода демонстрирует применение сплошного цвета и рисования с помощью кистей к модели [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 [!code-xml[basic3d#Basic3DXAML3DN5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xml[3doverview#3DOverview3DN9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## Освещение сцены  
 Источники света в графике [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] выполняют ту же роль, что и реальные источники света: они делают поверхности видимыми.  Более того, источники света определяют, какая часть сцены будет включена в проекцию.  Объекты источников света в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создают различные эффекты света и тени. Они смоделированы на основе поведения различных реальных источников света.  Сцена должна включать, как минимум, один источник света, иначе модели будут невидимыми.  
  
 Указанные ниже источники света являются производными от базового класса <xref:System.Windows.Media.Media3D.Light>:  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>: создает рассеянное освещение, при котором все объекты освещены одинаково, независимо от их расположения или ориентации.  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>: создает освещение, аналогичное удаленному источнику света.  Направленные источники света имеют свойство <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A>, которое указывается как объект Vector3D, но без заданного местоположения.  
  
-   <xref:System.Windows.Media.Media3D.PointLight> создает освещение, как от ближнего источника света.  Источники света "PointLights" занимают определенное положение и испускают свет из этого положения.  Объекты на сцене освещаются в зависимости от их положения и расстояния относительно источника света.  <xref:System.Windows.Media.Media3D.PointLightBase> предоставляет свойство <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A>, которое определяет расстояние, за пределами которого модели не будут освещены светом.  Класс "PointLight" также предоставляет свойства затухания, определяющие интенсивность ослабления источника света в зависимости от расстояния.  Можно указать константу, линейную или квадратичную интерполяцию затухания источника света.  
  
-   Исключение <xref:System.Windows.Media.Media3D.SpotLight> наследуется от исключения <xref:System.Windows.Media.Media3D.PointLight>.  Источники света "Spotlights" освещают сцену подобно источникам света PointLight и также имеют расположение и направление.  Они проектируют свет в конусообразную область, задаваемую свойствами <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A>, значения которых указываются в градусах.  
  
 Источники света являются объектами <xref:System.Windows.Media.Media3D.Model3D>, поэтому можно преобразовывать и анимировать свойства источников света, включая положение, цвет, направление и диапазон.  
  
 [!code-xml[hittest3d#HitTest3D3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## Преобразование моделей  
 При создании моделей в сцене им задается определенное местоположение.  Для поворота моделей, изменения их размера или перемещения внутри сцены не следует изменять вершины, определяющие сами модели.  Вместо этого, как и в моделировании [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], применяются преобразования моделей.  
  
 Каждый объект модели имеет свойство <xref:System.Windows.Media.Media3D.Model3D.Transform%2A>, с помощью которого можно перемещать модель, изменять ее направление или размер.  При применении преобразования фактически смещаются все точки модели с помощью вектора или значения, заданного преобразованием.  Другими словами, выполняется преобразование координатного пространства, в котором определена модель \("пространство модели"\), при этом значения, составляющие геометрию модели в системе координат всей сцены \("мировое пространство"\), не изменяются.  
  
 Дополнительные сведения о преобразовании моделей см. в разделе [Общие сведения о трехмерных преобразованиях](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## Анимация моделей  
 Реализация модели [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] действует в той же системе анимации и времени, что и графика [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)].  Другими словами, для анимации трехмерной сцены необходимо анимировать свойства ее моделей.  Можно непосредственно анимировать свойства примитивов, но обычно проще анимировать преобразования, изменяющие позицию или внешний вид моделей.  Поскольку преобразования можно применить к объектам <xref:System.Windows.Media.Media3D.Model3DGroup> также как и к отдельным моделям, то возможно применение одного набора анимаций к дочернему элементу Model3DGroup, а другого набора — к группе дочерних объектов.  Также можно добиться разнообразных визуальных эффектов, анимируя свойства элементов освещения сцены.  Наконец, можно анимировать саму проекцию, изменяя положение камеры или поле зрения.  Общие сведения о системе времени и анимации в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделах [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md), [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) и [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Для анимации объекта в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создайте временную шкалу, определите анимацию \(которая изменяет значение некоторого свойства во времени\) и укажите свойство, к которому применяется анимация.  Поскольку все объекты в сцене [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] являются дочерними элементами объекта <xref:System.Windows.Controls.Viewport3D>, свойства, к которым применяется анимация, являются свойствами "Viewport3D".  
  
 Предположим, требуется создать качающуюся на месте модель.  Можно применить свойство <xref:System.Windows.Media.Media3D.RotateTransform3D> к модели и анимировать ее ось вращения от одного вектора к другому.  В следующем примере кода показано применение объекта "Vector3DAnimation" к свойству "Axis" для "Rotation3D" преобразования, предполагая, что "RotateTransform3D" будет одним из нескольких преобразований, примененных к модели с помощью "TransformGroup".  
  
 [!code-csharp[3doverview#3DOverview3DN1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## Добавление трехмерного содержимого к окну  
 Для отображения сцены добавьте модели и источники света к объекту <xref:System.Windows.Media.Media3D.Model3DGroup>, затем задайте объект <xref:System.Windows.Media.Media3D.Model3DGroup> как свойство <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> объекта <xref:System.Windows.Media.Media3D.ModelVisual3D>.  Добавьте <xref:System.Windows.Media.Media3D.ModelVisual3D> к коллекции <xref:System.Windows.Controls.Viewport3D.Children%2A> объекта <xref:System.Windows.Controls.Viewport3D>.  Добавьте камеры к объекту <xref:System.Windows.Controls.Viewport3D>, задав его свойство <xref:System.Windows.Controls.Viewport3D.Camera%2A>.  
  
 Наконец, добавьте объект <xref:System.Windows.Controls.Viewport3D> к окну.  При включении объекта <xref:System.Windows.Controls.Viewport3D> в качестве содержимого элемента макета, такого как "Canvas", укажите размер объекта "Viewport3D", задав его свойства <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A>\(наследуемые от объекта <xref:System.Windows.FrameworkElement>\).  
  
 [!code-xml[hostingwpfusercontrolinwf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## См. также  
 <xref:System.Windows.Controls.Viewport3D>   
 <xref:System.Windows.Media.Media3D.PerspectiveCamera>   
 <xref:System.Windows.Media.Media3D.DirectionalLight>   
 <xref:System.Windows.Media.Media3D.Material>   
 [Общие сведения о трехмерных преобразованиях](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)   
 [Достижение максимальной производительности WPF 3D](../../../../docs/framework/wpf/graphics-multimedia/maximize-wpf-3d-performance.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-how-to-topics.md)   
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)