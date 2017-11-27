---
title: "Загрузка кода XAML и свойства зависимостей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 97970a8a292eee43b01b1eab235376ae9b8e6fad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xaml-loading-and-dependency-properties"></a>Загрузка кода XAML и свойства зависимостей
Текущая реализация процессора [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], по сути, учитывает свойство зависимостей. При загрузке двоичных файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и обработке атрибутов, которые являются свойствами зависимостей, процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует методы системы свойств для свойств зависимостей. При этом выполняется обход оболочек свойств. При реализации пользовательских свойств зависимостей необходимо учитывать такое поведение и следует избегать размещения любого другого кода в оболочке свойства Кроме методов системы свойств <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 В этом разделе предполагается, что вы, как пользователь и разработчик, понимаете свойства зависимостей и ознакомились с разделами [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) и [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md). Следует также прочитать разделы [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) и [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Реализация загрузчика XAML WPF и производительность  
 В целях реализации требуется значительно меньше затрат определить свойство как свойство зависимостей и доступа в системе свойств <xref:System.Windows.DependencyObject.SetValue%2A> метод, чтобы задать его, а не с помощью оболочки свойства и задания значения. Причина этого заключается в том, что процессору [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] требуется вывести всю объектную модель вспомогательного кода, основываясь только на сведениях о типе и связях между членами, которые определены структурой разметки и различными строками.  
  
 Тип осуществляется посредством сочетания элементов xmlns и атрибутов сборки, однако для идентификации членов, определения членов которой может установить в качестве атрибута, и разрешения, какие типы поддерживают значения свойств бы в противном случае требуется расширенное отражение с помощью <xref:System.Reflection.PropertyInfo>. Так как свойства зависимостей для заданного типа доступны в виде таблицы хранилища с помощью системы свойств, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализация его [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор использует эту таблицу и выводит все свойства заданного *ABC* может быть задано более эффективно, вызвав <xref:System.Windows.DependencyObject.SetValue%2A> в содержащем <xref:System.Windows.DependencyObject> производный тип, используя идентификатор свойства зависимостей *ABCProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Последствия использования пользовательских свойств зависимостей  
 Так как текущая реализация процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] при установке свойства полностью обходит оболочки, не следует помещать дополнительную логику в определения метода set оболочки для пользовательского свойства зависимости. Если поместить такую логику в определение метода set, она не будет выполняться, если свойство задается в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а не в коде.  
  
 Аналогичным образом, другие аспекты [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора, которые получают значения свойств из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обработки также используйте <xref:System.Windows.DependencyObject.GetValue%2A> вместо использования оболочки. Поэтому следует избегать любых дополнительных реализаций в `get` определения за пределами <xref:System.Windows.DependencyObject.GetValue%2A> вызова.  
  
 В приведенном ниже примере показано рекомендуемое определение свойства зависимости с оболочками, где идентификатор свойства хранится в виде поля с атрибутами `public` `static` `readonly`, а определения методов `get` и `set` не содержат никакого кода, кроме необходимых методов системы свойств, определяющих резервное свойство зависимости.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Метаданные свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Свойства зависимостей типа коллекции](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)  
 [Безопасность свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-security.md)  
 [Шаблоны безопасного конструктора для DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
