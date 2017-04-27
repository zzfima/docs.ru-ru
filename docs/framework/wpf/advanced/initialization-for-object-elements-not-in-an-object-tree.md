---
title: "Инициализация для элементов типа Object вне дерева объектов | Microsoft Docs"
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
  - "элементы, инициализация"
  - "инициализация элементов"
  - "логическое дерево"
  - "визуальное дерево"
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Инициализация для элементов типа Object вне дерева объектов
Некоторые аспекты инициализации [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] откладываются для процессов, которые обычно полагаются на то, что элемент подключен либо к [логическому дереву](GTMT) или [визуальному дерево](GTMT).  В этом разделе описываются действия, необходимые для инициализации элемента, который не подключен ни к одному из деревьев.  
  
   
  
## Элементы и логическое дерево  
 При создании экземпляра класса [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] в коде следует иметь в виду, что несколько аспектов инициализации объекта для класса [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] преднамеренно не являются частью кода, выполняющегося при вызове конструктора класса.  Большая часть визуального представления элемента управления, особенно для класса элемента управления, не определяется конструктором.  Вместо этого визуальное представление определяется шаблоном элемента управления.  Шаблон может быть получен из различных источников, но наиболее часто он берется из тематических стилей.  Шаблоны фактически выполняют позднее связывание. Необходимый шаблон не присоединяется к элементу управления до тех пор, пока элемент управления не будет подготовлен для макета.  А элемент управления не готов для макета до тех пор, пока он не будет присоединен к логическому дереву, которое подключается к отрисовываемой поверхности в корневом элементе.  Это элемент корневого уровня, который инициирует отрисовку всех дочерних элементов, как определено в логическом дереве.  
  
 Визуальное дерево также участвует в этом процессе.  Элементы, которые с помощью шаблонов являются частью визуального дерева, также полностью не создаются до тех пор, пока не произойдет подключение.  
  
 Последствием этого является то, что для определенных операций, зависящих от завершенных визуальных характеристик элемента, требуется выполнение дополнительных действий.  Примером является попытка получить визуальные характеристики класса, который был создан, но еще не присоединен к дереву.  Например, если необходимо вызвать <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> на <xref:System.Windows.Media.Imaging.RenderTargetBitmap> и передаваемый визуальный элемент не подключен к дереву, то визуально этот элемент остается незавершенным, пока не будут выполнены дополнительные шаги инициализации.  
  
### Использование BeginInit и EndInit для инициализации элемента  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] интерфейс <xref:System.ComponentModel.ISupportInitialize> реализуют различные классы.  Для обозначения области кода, содержащей действия для инициализации \(такие как установка значений свойств, влияющих на отрисовку\), можно использовать методы <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> и <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> интерфейса.  После вызова <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> в последовательности система разметки может обработать элемент и начать поиск неявного стиля.  
  
 Если элемент, для которого устанавливаются свойства, является производным классом <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, то можно вызвать версии класса <xref:System.Windows.FrameworkElement.BeginInit%2A> и <xref:System.Windows.FrameworkElement.EndInit%2A> вместо приведения к <xref:System.ComponentModel.ISupportInitialize>.  
  
### Пример кода  
 В следующем примере представлен образец кода консольного приложения, использующего отрисовку [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] и <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=fullName> свободного файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для иллюстрации правильного размещения <xref:System.Windows.FrameworkElement.BeginInit%2A> и <xref:System.Windows.FrameworkElement.EndInit%2A> относительно других вызовов [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], влияющих на отображение.  
  
 В данном примере иллюстрируется только основная функция.  Функции `Rasterize` и `Save` \(не отображены\) являются служебными функциями, которые отвечают за обработку изображения и ввод\-вывод.  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## См. также  
 [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)   
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)