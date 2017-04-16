---
title: "Достижение максимальной производительности WPF 3D | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "трехмерная графика [WPF]"
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Достижение максимальной производительности WPF 3D
При использовании [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] для построения трехмерных элементов управления и включения трехмерных сцен в приложения необходимо рассмотреть вопрос оптимизации производительности. В этом разделе предоставляется список классов и свойств для трехмерных объектов, которые влияют на быстродействие приложения, а также рекомендации по оптимизации их производительности.  
  
 Этот раздел рассчитан на пользователей, профессионально использующих возможности 3D [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Предложения в этом документе справедливы для "отрисовки 2 уровня" — то есть для аппаратного обеспечения, которое поддерживает построитель текстуры версии 2.0 и вершинный построитель текстуры версии 2.0.  Дополнительные сведения см. в разделе [Уровни графической отрисовки](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## Влияние на производительность: высокое  
  
|||  
|-|-|  
|Свойство.|Рекомендации|  
|<xref:System.Windows.Media.Brush>|Скорость кисти \(от самой быстрой к самой медленной\):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> \(кэшированное\)<br /><br /> <xref:System.Windows.Media.VisualBrush> \(кэшированное\)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> \(некэшированное\)<br /><br /> <xref:System.Windows.Media.VisualBrush> \(некэшированное\)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|Устанавливайте `Viewport3D.ClipToBounds` в значение false, если [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] не должен явным образом отсекать содержимое <xref:System.Windows.Controls.Viewport3D> в прямоугольнике Viewport3D. Отсечение [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] со сглаживанием может быть очень медленным, а по умолчанию `ClipToBounds` в <xref:System.Windows.Controls.Viewport3D> включено \(т. е. выполняется медленно\).|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|Устанавливайте для свойства `Viewport3D.IsHitTestVisible` значение false, если приложению [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] не требуется учитывать содержимое элемента управления <xref:System.Windows.Controls.Viewport3D> при выполнении проверки нажатия мыши. Проверка нажатия трехмерного содержимого выполняется программным образом, и для больших сеточных моделей она может быть достаточно продолжительной. Свойство <xref:System.Windows.UIElement.IsHitTestVisible%2A> элемента управления <xref:System.Windows.Controls.Viewport3D> по умолчанию включено \(т.е. выполняется медленно\).|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|Создавайте различные модели только в том случае, если для них требуются различные материалы или преобразования.  В противном случае попробуйте объединить несколько экземпляров <xref:System.Windows.Media.Media3D.GeometryModel3D> с теми же материалами и преобразованиями в несколько больших экземпляров <xref:System.Windows.Media.Media3D.GeometryModel3D> и <xref:System.Windows.Media.Media3D.MeshGeometry3D>.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Сеточная анимация \(т. е. покадровое изменение отдельных вершин сетки\) не всегда эффективна в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Для уменьшения влияния уведомлений об изменении на производительность при изменении каждой вершины отсоедините сетку от визуального дерева перед тем, как выполнять преобразования каждой вершины. Завершив изменения сетки, снова присоедините ее к визуальному дереву. Также следует уменьшить размер сетки, которая будет анимирована подобным образом.|  
|3D\-сглаживание|Чтобы увеличить скорость отрисовки, отключите мультисэмплинг на <xref:System.Windows.Controls.Viewport3D>, установив вложенное свойство <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> в значение `Aliased`.  По умолчанию, 3D сглаживание отключено в [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] и включено в [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] со значением в 4 сэмпла на каждый пиксель.|  
|Текст|Отображение текста в реальном масштабе времени в 3D сцене может выполняться медленно \(текст "в реальном масштабе времени", так как он содержится в <xref:System.Windows.Media.DrawingBrush> или <xref:System.Windows.Media.VisualBrush>\).  Попробуйте использовать изображения текста \(с помощью <xref:System.Windows.Media.Imaging.RenderTargetBitmap>\), если текст не будет меняться.|  
|<xref:System.Windows.Media.TileBrush>|Если <xref:System.Windows.Media.VisualBrush> или <xref:System.Windows.Media.DrawingBrush> необходимо использовать в 3D сцене, поскольку содержимое кисти не статическое, попробуйте кэшировать кисть \(с помощью установки вложенного свойства <xref:System.Windows.Media.RenderOptions.CachingHint%2A> в `Cache`\).  Задайте минимальное и максимальное пороговые значения недействительности масштаба с помощью вложенных свойств <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> и <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>. Это приведет к тому, что кэшированные кисти не будут обновляться слишком часто, но будут сохранять требуемый уровень качества.  По умолчанию <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush> не кэшируются, то есть при повторном отображении нарисованного кистью все содержимое кисти необходимо еще раз построить в промежуточной области.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect> заставляет все измененное содержимое отображаться без аппаратного ускорения.  Для лучшей производительности не следует использовать <xref:System.Windows.Media.Effects.BitmapEffect>.|  
  
## Влияние на производительность: среднее  
  
|||  
|-|-|  
|Свойство.|Рекомендации|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Когда сетка определяется как граничащие треугольники с общими вершинами, и эти вершины имеют одну и ту же позицию, нормаль и координаты текстуры, определите каждую общую вершину только один раз, а затем определите треугольники по индексу с помощью <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>.|  
|<xref:System.Windows.Media.ImageBrush>|Попробуйте уменьшить размеры текстуры при наличии явного управления размером \(т.е.при использовании <xref:System.Windows.Media.Imaging.RenderTargetBitmap> или <xref:System.Windows.Media.ImageBrush>\).  Обратите внимание, что текстуры более низкого разрешения могут снизить визуальное качество, поэтому следует найти правильный баланс между качеством и производительностью.|  
|Непрозрачность|При отрисовке полупрозрачного 3D\-содержимого \(например отражений\) используйте свойства непрозрачности на кистях или материалах \(с помощью <xref:System.Windows.Media.Brush.Opacity%2A> или <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>\) вместо того, чтобы создавать отдельные прозрачные <xref:System.Windows.Controls.Viewport3D> путем установки `Viewport3D.Opacity` в значение меньше 1.|  
|<xref:System.Windows.Controls.Viewport3D>|Сократите число используемых в сцене объектов <xref:System.Windows.Controls.Viewport3D>.  Поместите несколько 3D моделей в один и тот же Viewport3D вместо создания отдельных экземпляров Viewport3D для каждой модели.|  
|<xref:System.Windows.Freezable>|Обычно это полезно для повторного использования <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, кистей и материалов.  Все они могут иметь несколько родительских элементов, так как являются производными от `Freezable`.|  
|<xref:System.Windows.Freezable>|Вызовите метод <xref:System.Windows.Freezable.Freeze%2A> на объектах Freezable, если их свойства в приложении не будут меняться.  Замораживание может уменьшить рабочее множество и повысить скорость.|  
|<xref:System.Windows.Media.Brush>|Используйте <xref:System.Windows.Media.ImageBrush> вместо <xref:System.Windows.Media.VisualBrush> или <xref:System.Windows.Media.DrawingBrush>, если содержимое кисти не будет меняться.  2D\-содержимое может быть преобразовано в <xref:System.Windows.Controls.Image> с помощью <xref:System.Windows.Media.Imaging.RenderTargetBitmap> и затем использовано в <xref:System.Windows.Media.ImageBrush>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|Не используйте <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>, если <xref:System.Windows.Media.Media3D.GeometryModel3D> не требуется отображать с обратной стороны.|  
|<xref:System.Windows.Media.Media3D.Light>|Скорость света \(от самой быстрой к самой медленной\):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Попробуйте сохранять размер сетки в следующих пределах:<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20 001 экземпляр <xref:System.Windows.Media.Media3D.Point3D><br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60003 экземпляра <xref:System.Int32>|  
|<xref:System.Windows.Media.Media3D.Material>|Скорость материала \(от самой быстрой до самой медленной\):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|Трехмерная система [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] не отказывается от невидимых кистей \(черных кистей окружения, кистей очистки и т. д.\) согласованным образом. Попробуйте отказаться от этих средств в сценах.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|Каждый <xref:System.Windows.Media.Media3D.Material> в <xref:System.Windows.Media.Media3D.MaterialGroup> вызывает следующий проход отрисовки. Таким образом, включение большого количества материалов, даже самых простых, может значительно увеличить загруженность графического процессора.  Уменьшите количество материалов в <xref:System.Windows.Media.Media3D.MaterialGroup>.|  
  
## Влияние на производительность: низкое  
  
|||  
|-|-|  
|Свойство.|Рекомендации|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|Когда анимация или привязка данных не требуется, используйте один <xref:System.Windows.Media.Media3D.MatrixTransform3D> вместо преобразования группы, содержащей несколько преобразований. Для этого установите его таким образом, чтобы он был произведением всех преобразований, которые бы в противном случае существовали в группе преобразования независимо.|  
|<xref:System.Windows.Media.Media3D.Light>|Сократите число источников света в сценах.  Слишком большое количество источников света в сцене заставит [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] прибегнуть к программной отрисовке. Максимально допустимо около 110 объектов <xref:System.Windows.Media.Media3D.DirectionalLight>, 70 объектов <xref:System.Windows.Media.Media3D.PointLight> или 40 объектов <xref:System.Windows.Media.Media3D.SpotLight>.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|Отделяйте перемещаемые объекты от статических объектов, помещая их в отдельные экземпляры <xref:System.Windows.Media.Media3D.ModelVisual3D>.  ModelVisual3D "тяжелее" <xref:System.Windows.Media.Media3D.GeometryModel3D>, так как он кэширует преобразованные границы.  GeometryModel3D оптимизирован для использования в качестве модели, а ModelVisual3D оптимизирован для того, чтобы быть узлом сцены.  Используйте ModelVisual3D для помещения в сцену общих экземпляров GeometryModel3D.|  
|<xref:System.Windows.Media.Media3D.Light>|Сократите изменения числа источников света в сцене.  Каждое изменение числа источников света вызывает восстановление и повторную компиляцию построителя за исключением того случая, когда конфигурация существовала ранее и, таким образом, ее построитель уже кэширован.|  
|Свет|Черные источники света не будут отображаться, но будут увеличивать время построения. Попробуйте по возможности отказаться от них.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Для минимизации времени построения больших коллекций в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], таких как MeshGeometry3D <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> и <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, установите размер коллекции до заполнения значениями.  По возможности передавайте конструкторам коллекции уже заполненные структуры данных, например массивы или списки.|  
  
## См. также  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)