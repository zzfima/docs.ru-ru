---
title: "Загрузка кода XAML и свойства зависимостей | Microsoft Docs"
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
  - "пользовательские свойства зависимостей"
  - "свойства зависимостей, загрузка XAML и"
  - "загрузка данных XML"
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Загрузка кода XAML и свойства зависимостей
Текущая реализация процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], по сути, учитывает свойство зависимостей.  При загрузке двоичных файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и обработке атрибутов, которые являются свойствами зависимостей, процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует методы системы свойств для свойств зависимостей.  При этом эффективно выполняется обход оболочек свойств.  При реализации пользовательских свойств зависимостей необходимо учитывать такое поведение и избегать размещения в оболочке свойства любого другого кода, отличного от методов системы свойств <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Предварительные требования  
 В этом разделе предполагается, что пользователь, как заказчик и автор, понимает свойства зависимостей и ознакомился с разделами [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) и [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  Следует также прочитать разделы [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) и [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## Реализация загрузчика XAML WPF и производительность  
 С точки зрения реализации, для определения свойства как свойства зависимости и доступа к методу <xref:System.Windows.DependencyObject.SetValue%2A> системы свойств для его установки требуется значительно меньше затрат, чем для использования оболочки свойства и ее метода установки.  Причина этого заключается в том, что процессору [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] требуется логически вывести всю объектную модель вспомогательного кода, основываясь только на сведениях о типе и связи между членами, которые определены структурой разметки и различными строками.  
  
 Поиск типа осуществляется посредством сочетания элементов XMLNS и атрибутов сборки, однако для идентификации членов, определения тех членов, которые можно установить в качестве атрибута, и типов, поддерживаемых значениями свойств, требуется расширенное отражение с помощью объекта <xref:System.Reflection.PropertyInfo>.  Поскольку свойства зависимостей данного типа доступны в виде таблицы хранилища с помощью системы свойств, реализация приложением [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] его процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] использует эту таблицу и логически выводит, что любое данное свойство *ABC* может быть задано более эффективно посредством вызова метода <xref:System.Windows.DependencyObject.SetValue%2A> в содержащем его производном типе <xref:System.Windows.DependencyObject>, используя идентификатор свойства зависимостей *свойство\_ABC*.  
  
<a name="implications"></a>   
## Последствия использования пользовательских свойств зависимостей  
 Поскольку текущая реализация процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] при установке свойства полностью обходит программы\-оболочки, не следует помещать дополнительную логику в определения метода set программы\-оболочки для пользовательского свойства зависимостей.  Если поместить такую логику в определение метода set, она не будет выполняться, если свойство задается в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а не в коде.  
  
 Аналогичным образом, другие аспекты процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], которые получают значения свойств в результате обработки кода [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также используют метод <xref:System.Windows.DependencyObject.GetValue%2A> вместо программы\-оболочки.  Поэтому следует также избегать любых дополнительных реализаций в определении метода `get` за пределами вызова метода <xref:System.Windows.DependencyObject.GetValue%2A>.  
  
 В следующем примере показано рекомендуемое определение свойства зависимости с оболочками, где идентификатор свойства хранится в виде поля с атрибутами `public` `static` `readonly`, а определения методов `get` и `set` не содержат кода за пределами необходимых методов системы свойств, определяющих резервное свойство зависимости.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## См. также  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Метаданные свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Свойства зависимостей типа коллекция](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)   
 [Безопасность свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-security.md)   
 [Шаблоны безопасного конструктора для DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)