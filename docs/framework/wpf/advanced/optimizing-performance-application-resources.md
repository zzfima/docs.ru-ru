---
title: 'Оптимизация производительности: ресурсы приложения'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 53e906f31f32fb0f1df3f8d986daa0ae95ea9e4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546599"
---
# <a name="optimizing-performance-application-resources"></a>Оптимизация производительности: ресурсы приложения
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет совместно использовать ресурсы приложения, чтобы можно поддерживать согласованный внешний вид или поведение с помощью элементов одинакового типа. Этот раздел содержит несколько рекомендаций в этой области, которые могут помочь повысить производительность приложений.  
  
 Дополнительные сведения о ресурсах см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
## <a name="sharing-resources"></a>Совместное использование ресурсов  
 Если приложение использует пользовательские элементы управления и определяет ресурсы в <xref:System.Windows.ResourceDictionary> (или узле ресурсов XAML), рекомендуется определить ресурсы на <xref:System.Windows.Application> или <xref:System.Windows.Window> объекта уровень или указать их в тему по умолчанию для пользовательские элементы управления. Определение ресурсов в пользовательский элемент управления <xref:System.Windows.ResourceDictionary> оказывает влияние на производительность для всех экземпляров этого элемента управления. Например при наличии кисти ресурсоемких операций, определенных как часть определения ресурсов для пользовательского элемента управления и несколько экземпляров элемента управления рабочего набора приложения увеличит значительно.  
  
 Чтобы проиллюстрировать это, рассмотрим следующее. Предположим, что вы разрабатываете карты игры с использованием [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Для большинства карточных играх необходимо 52 карты с 52 различными вариантами лицевой стороны. Чтобы реализовать пользовательский элемент управления карты и определить 52 кисти (каждый из которых представляет лицевой стороны) в ресурсах пользовательского элемента управления карты. В главном приложении первоначально создается 52 экземпляра пользовательского элемента управления карты. Каждый экземпляр элемента управления создает 52 экземпляра <xref:System.Windows.Media.Brush> объектов, которые в итоге 52 * 52 дает <xref:System.Windows.Media.Brush> объектов в приложении. Перемещая кисти из ресурсов пользовательского элемента управления для <xref:System.Windows.Application> или <xref:System.Windows.Window> уровень объекта или определения их в тему по умолчанию для пользовательского элемента управления, можно уменьшить рабочее множество приложения, так как теперь общего 52 кисти 52 экземпляра элемента управления карты.  
  
## <a name="sharing-a-brush-without-copying"></a>Общее использование кисти без копирования  
 Если у вас есть несколько элементов, используя те же <xref:System.Windows.Media.Brush> объекта, определите кисть как ресурс и ссылки, но не определение встроенной кисти в [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Этот метод создаст один экземпляр и повторно использует его, тогда как определение встроенной кисти в [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] создает новый экземпляр для каждого элемента.  
  
 В следующем примере разметки показано:  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Использование статических ресурсов, если это возможно  
 Статический ресурс предоставляет значение для любого атрибута свойства XAML путем поиска ссылки на уже определенный ресурс. Поведение подстановки для этого ресурса является аналогом во время компиляции.  
  
 Динамический ресурс, с другой стороны, создаст временное выражение во время начальной компиляции и таким образом, отложит для ресурсов, пока значение запрошенного ресурса фактически требуется для создания объекта. Поведение подстановки для этого ресурса является аналогом подстановки во время выполнения, который оказывает влияние на производительность. Использование статических ресурсов, когда это возможно в приложении, с помощью динамического ресурсы только при необходимости.  
  
 В следующем примере разметки показано использование обоих типов ресурсов:  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>См. также  
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Планирование производительности приложения](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Использование преимуществ оборудования](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Поведение объекта](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Дополнительные рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
