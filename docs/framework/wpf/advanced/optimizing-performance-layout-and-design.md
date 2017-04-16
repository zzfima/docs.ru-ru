---
title: "Оптимизация производительности: разметка и разработка | Microsoft Docs"
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
  - "вопросы разработки"
  - "проход разметки"
  - "макет, оптимизация производительности"
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Оптимизация производительности: разметка и разработка
Разработка приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может повлиять на его производительность в результате создания ненужных служебных данных при вычислении макета и проверки ссылок на объекты.  Конструирование объектов, особенно во время выполнения, может повлиять на характеристики производительности приложения.  
  
 В этом разделе содержатся рекомендации по производительности в этих областях.  
  
## Макет  
 Термин "проход разметки" описывает процесс измерения и упорядочения объекта <xref:System.Windows.Controls.Panel> — коллекции дочерних объектов производного объекта, и затем рисование их на экране.  Проход разметки представляет собой процесс интенсивной математической нагрузки — чем больше число дочерних объектов в коллекции, тем больше требуется вычислений.  Например, при каждом изменении положения дочернего объекта <xref:System.Windows.UIElement> в коллекции, он имеет возможность инициировать новую передачу системой разметки.  Из\-за разрыва отношения между характеристиками объекта и поведением разметки важно понимать тип событий, которые могут запустить систему разметки.  Приложение будет выполняться лучше, если уменьшить, насколько возможно, ненужные вызовы прохода разметки.  
  
 Система разметки выполняет два прохода для каждого дочернего члена в коллекции: проход измерений и проход компоновки.  Каждый дочерний объект предоставляет свою собственную переопределенную реализацию методов <xref:System.Windows.UIElement.Measure%2A> и <xref:System.Windows.UIElement.Arrange%2A>, чтобы обеспечить собственное поведение отдельной разметки.  В самом простом случае макет является рекурсивной системой, в процессе которой программа изменяет размер и расположение элемента и отображает его на экране.  
  
-   Дочерний объект <xref:System.Windows.UIElement> начинает процесс разметки первым, задав его основные измеряемые свойства.  
  
-   Вычисляются свойства объекта <xref:System.Windows.FrameworkElement>, относящиеся к размеру, например <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
-   Применяется логика отдельного объекта <xref:System.Windows.Controls.Panel>, например свойство <xref:System.Windows.Controls.DockPanel.Dock%2A> объекта <xref:System.Windows.Controls.DockPanel> или свойство <xref:System.Windows.Controls.StackPanel.Orientation%2A> объекта <xref:System.Windows.Controls.StackPanel>.  
  
-   Содержимое компонуется или размещается после всех дочерних объектов, которые были измерены.  
  
-   На экране отображается коллекция дочерних объектов.  
  
 Процесс прохода разметки вызывается снова при возникновении любого из следующих событий:  
  
-   Дочерний объект добавляется к коллекции.  
  
-   Свойство <xref:System.Windows.FrameworkElement.LayoutTransform%2A> применяется к дочернему объекту.  
  
-   Метод <xref:System.Windows.UIElement.UpdateLayout%2A> вызывается для дочернего объекта.  
  
-   При изменении значения [свойства зависимости](GTMT), которое помечено метаданными, влияющими на проход измерения и компоновки.  
  
### Используйте наиболее эффективную панель там, где возможно  
 Сложность прохода разметки непосредственно основана на поведении разметки используемых элементов, производных объекта <xref:System.Windows.Controls.Panel>.  Например, объект <xref:System.Windows.Controls.Grid> или элемент управления <xref:System.Windows.Controls.StackPanel> предоставляет гораздо больше функциональных возможностей, чем элемент управления <xref:System.Windows.Controls.Canvas>.  Ценой этого значительного увеличения функциональности является увеличение затрат производительности.  Однако если не требуются функциональные возможности, предоставляемые элементом управления <xref:System.Windows.Controls.Grid>, следует использовать менее затратные варианты, например <xref:System.Windows.Controls.Canvas> или настраиваемую панель.  
  
 Дополнительные сведения см. в разделе [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).  
  
### Обновление вместо замены RenderTransform  
 Можно обновить объект <xref:System.Windows.Media.Transform> вместо замены его в качестве значения свойства <xref:System.Windows.UIElement.RenderTransform%2A>.  Это особенно верно в скриптах, включающих анимацию.  Обновление существующего объекта <xref:System.Windows.Media.Transform> позволяет избежать инициирования ненужных вычислений разметки.  
  
### Построение дерева сверху вниз  
 При добавлении или удалении узла из [логического дерева](GTMT) свойство аннулирования вызывается на родительском узле и всех дочерних узлах.  В результате, всегда требуется следовать шаблону структуры сверху вниз, во избежание ненужных аннулирований на узлах, которые уже были проверены.  В следующей таблице показана разница в скорости выполнения между построением дерева сверху вниз или снизу вверх с глубиной 150 уровней с одним объектом <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.DockPanel> на каждом уровне.  
  
|**Действие**|**Построение дерева \(мс\)**|**Отображение — включает построение дерева \(мс\)**|  
|------------------|----------------------------------|---------------------------------------------------------|  
|Снизу вверх|366|454|  
|Сверху вниз|11|96|  
  
 В следующем примере кода демонстрируется создание дерева сверху вниз.  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
## См. также  
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Планирование производительности приложения](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Использование преимуществ оборудования](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Поведение объекта](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Ресурсы приложения](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Дополнительные рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Макет](../../../../docs/framework/wpf/advanced/layout.md)