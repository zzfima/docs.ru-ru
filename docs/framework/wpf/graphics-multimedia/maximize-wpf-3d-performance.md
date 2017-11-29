---
title: "Достижение максимальной производительности WPF 3D"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26df55c9658721eb907db5837ac467a5899e84eb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="maximize-wpf-3d-performance"></a>Достижение максимальной производительности WPF 3D
При использовании [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] для построения трехмерных элементов управления и включения трехмерных сцен в приложении, необходимо рассмотреть вопрос оптимизации производительности. Здесь представлен список 3D классов и свойств, которые влияют на производительность приложения, а также рекомендации по оптимизации производительности при их использовании.  
  
 В этом разделе предполагается глубокого понимания [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] возможности 3D. В этом документе приводятся советы для «уровня отрисовки 2» — примерно определенные аппаратного обеспечения, которое поддерживает построитель текстуры версии 2.0 и вершинный построитель текстуры версии 2.0. Дополнительные сведения см. в разделе [уровни отрисовки графики](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## <a name="performance-impact-high"></a>Влияние на производительность: высокий  
  
|Свойство|Рекомендация|  
|-|-|  
|<xref:System.Windows.Media.Brush>|Скорость кисти (от самой быстрой к самой медленной):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(с кэшированием)<br /><br /> <xref:System.Windows.Media.VisualBrush>(с кэшированием)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(без кэш-памяти)<br /><br /> <xref:System.Windows.Media.VisualBrush>(без кэш-памяти)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|Задать `Viewport3D.ClipToBounds` значение false, если необходимо иметь [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] явно усечение содержимого <xref:System.Windows.Controls.Viewport3D> Viewport3D прямоугольник. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Сглаженный обрезки может вычисляться очень медленно, и `ClipToBounds` (медленно) включено по умолчанию в <xref:System.Windows.Controls.Viewport3D>.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|Задать `Viewport3D.IsHitTestVisible` значение false, если нет необходимости [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] рассмотреть содержимое <xref:System.Windows.Controls.Viewport3D> при выполнении проверки нажатия мыши.  Проверка нажатия трехмерного содержимого выполняется программным образом и может быть достаточно больших сеточных. <xref:System.Windows.UIElement.IsHitTestVisible%2A>(медленно) включено по умолчанию в <xref:System.Windows.Controls.Viewport3D>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|Создайте различные модели только в том случае, если они требуются различные материалы или преобразования.  В противном случае попробуйте объединить несколько <xref:System.Windows.Media.Media3D.GeometryModel3D> экземпляры с одним и тем же материалы и преобразования в несколько больших <xref:System.Windows.Media.Media3D.GeometryModel3D> и <xref:System.Windows.Media.Media3D.MeshGeometry3D> экземпляры.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Сетка анимации — Изменение отдельных вершин сетки на основе кадров, не всегда эффективно в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Чтобы свести к минимуму влияние на производительность уведомления об изменении при изменении каждой вершины, отсоедините сетку от визуального дерева перед выполнением каждой вершины.  После сетки был изменен, снова присоедините ее к визуальному дереву.  Кроме того попробуйте уменьшить размер сетки, которая будет анимированы таким образом.|  
|3D сглаживание|Чтобы увеличить скорость отрисовки, отключите множественную выборку на <xref:System.Windows.Controls.Viewport3D> , задав значение вложенного свойства <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> для `Aliased`.  По умолчанию, 3D сглаживание отключено в [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] и включена на [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] с образцами 4 на пиксель.|  
|Text|Live текст в трехмерной сцене (live, так как он <xref:System.Windows.Media.DrawingBrush> или <xref:System.Windows.Media.VisualBrush>) может выполняться медленно. Попробуйте вместо этого использовать изображения текста (через <xref:System.Windows.Media.Imaging.RenderTargetBitmap>), если текст не будет меняться.|  
|<xref:System.Windows.Media.TileBrush>|Если необходимо использовать <xref:System.Windows.Media.VisualBrush> или <xref:System.Windows.Media.DrawingBrush> в трехмерной сцене, поскольку содержимое кисти не является статическим, попробуйте, кэшировать кисть (установив вложенное свойство <xref:System.Windows.Media.RenderOptions.CachingHint%2A> для `Cache`).  Задайте минимальный и максимальный масштаб недействительности пороговые значения (с вложенные свойства <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> и <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>), чтобы кэшированные кисти не будет повторно слишком часто, поддерживая нужный уровень качества.  По умолчанию <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush> не кэшируются, это означает, что каждый раз, что-нибудь, закрашенный с кистью должно быть повторно подготовленных к просмотру, все содержимое кисти сначала должны быть повторно помещены в область промежуточного.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect>заставляет все измененное содержимое будет отображаться без аппаратного ускорения.  Для достижения оптимальной производительности следует использовать <xref:System.Windows.Media.Effects.BitmapEffect>.|  
  
## <a name="performance-impact-medium"></a>Влияние на производительность: средний  
  
|Свойство|Рекомендация|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Когда сетка определяется как соседними треугольники с общими вершинами, и эти вершины имеют одинаковые позиции, normal и координаты текстуры, определите каждую общую вершину только один раз и затем определите треугольники по индексу с помощью <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>.|  
|<xref:System.Windows.Media.ImageBrush>|Попробуйте уменьшить размеры текстуры при наличии явного управления размером (при использовании <xref:System.Windows.Media.Imaging.RenderTargetBitmap> или <xref:System.Windows.Media.ImageBrush>).  Обратите внимание, что текстуры более низкого разрешения могут снизить качество изображения, поэтому следует найти правильный баланс между качеством и производительностью.|  
|Непрозрачность|При отрисовке полупрозрачные трехмерного содержимого (например отражений), используйте свойства непрозрачности кисти или материалы (через <xref:System.Windows.Media.Brush.Opacity%2A> или <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>) вместо создавать отдельные прозрачные <xref:System.Windows.Controls.Viewport3D> , установив `Viewport3D.Opacity` значение меньше 1.|  
|<xref:System.Windows.Controls.Viewport3D>|Свести к минимуму число <xref:System.Windows.Controls.Viewport3D> объектов вы используете в сцене.  Поместите несколько 3D моделей в тот же Viewport3D вместо создания отдельных экземпляров Viewport3D для каждой модели.|  
|<xref:System.Windows.Freezable>|Обычно это полезно для повторного использования <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, кистей и материалов.  Все являются multiparentable, поскольку они являются производными от `Freezable`.|  
|<xref:System.Windows.Freezable>|Вызовите <xref:System.Windows.Freezable.Freeze%2A> метод для объектов Freezable, если их свойства останется без изменений в приложении.  Замораживание может уменьшить рабочее множество и повысить скорость.|  
|<xref:System.Windows.Media.Brush>|Используйте <xref:System.Windows.Media.ImageBrush> вместо <xref:System.Windows.Media.VisualBrush> или <xref:System.Windows.Media.DrawingBrush> при содержимое кисти не изменится.  2D-содержимого можно преобразовать в <xref:System.Windows.Controls.Image> через <xref:System.Windows.Media.Imaging.RenderTargetBitmap> , а затем использовать в <xref:System.Windows.Media.ImageBrush>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|Не используйте <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> Если действительно требуется просматривать с обратной стороны вашей <xref:System.Windows.Media.Media3D.GeometryModel3D>.|  
|<xref:System.Windows.Media.Media3D.Light>|Скорость света (от самой быстрой к самой медленной):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Попробуйте сохранять размер сетки в этих ограничений.<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20 001 <xref:System.Windows.Media.Media3D.Point3D> экземпляров<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60003 <xref:System.Int32> экземпляров|  
|<xref:System.Windows.Media.Media3D.Material>|Скорость материала (от самой быстрой к самой медленной):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Объемные эффекты не отказывается от невидимых кистей (черных кистей окружения, кистей очистки, т. д.) согласованным образом.  Рассмотрите возможность отказаться от сцены этих средств.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|Каждый <xref:System.Windows.Media.Media3D.Material> в <xref:System.Windows.Media.Media3D.MaterialGroup> вызывает другой визуализации проход множество материалов, даже очень простой материалов, могут значительно повысить требования заливки в графическом процессоре.  Минимальное число используемых материалов в вашей <xref:System.Windows.Media.Media3D.MaterialGroup>.|  
  
## <a name="performance-impact-low"></a>Влияние на производительность: низкий  
  
|Свойство|Рекомендация|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|При анимации не требуется или привязки данных, вместо использования преобразования группы, содержащей несколько преобразований, использовании один <xref:System.Windows.Media.Media3D.MatrixTransform3D>, задание будет произведением всех преобразований, которые в противном случае будут существовать независимо друг от друга в группе преобразования.|  
|<xref:System.Windows.Media.Media3D.Light>|Минимальное число источники света в сцене. Слишком большое количество источников света в сцене заставит [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] переход к программной отрисовки.  Максимально допустимо около 110 <xref:System.Windows.Media.Media3D.DirectionalLight> объектов 70 <xref:System.Windows.Media.Media3D.PointLight> объектов или 40 <xref:System.Windows.Media.Media3D.SpotLight> объектов.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|Отделяйте перемещаемые объекты от статических объектов, помещая их в отдельных <xref:System.Windows.Media.Media3D.ModelVisual3D> экземпляров.  ModelVisual3D «тяжелее» <xref:System.Windows.Media.Media3D.GeometryModel3D> , так как он кэширует преобразованные границы.  GeometryModel3D оптимизирован для модели. ModelVisual3D оптимизирован для узел сцены.  Применять ModelVisual3D для размещения общих экземпляров GeometryModel3D в сцене.|  
|<xref:System.Windows.Media.Media3D.Light>|Минимальное число раз, изменение числа источников света в сцене.  Каждое изменение числа источников света вызывает принудительное повторное создание шейдера и повторная компиляция только ранее существовал конфигурации (и тем самым ее построитель уже кэширован).|  
|Светлый|Черные источники света не будут отображаться, но будут увеличивать время построения. Рассмотрите возможность отказаться от них.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Чтобы свести к минимуму время создания больших коллекций в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], например MeshGeometry3D <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>, и <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, предварительно размер коллекции перед заполнением значение. Если это возможно передайте коллекции конструкторов уже заполненные структуры данных, например массивов или списков.|  
  
## <a name="see-also"></a>См. также  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
