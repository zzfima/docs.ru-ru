---
title: Загрузка кода XAML и свойства зависимостей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
ms.openlocfilehash: de8050e582f5b1a5a288c350c179cfa24fb5471c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186256"
---
# <a name="xaml-loading-and-dependency-properties"></a>Загрузка кода XAML и свойства зависимостей
Текущая реализация процессора [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], по сути, учитывает свойство зависимостей. Процессор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] использует методы системы свойств для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] свойств зависимостей при загрузке двоичных и обрабатывающих атрибутов, которые являются свойствами зависимости. При этом выполняется обход оболочек свойств. При реализации пользовательских свойств зависимости необходимо учитывать это поведение и избегать размещения любого другого <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A>кода в обертке свойств, кроме методов системы свойств и:  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 В этом разделе предполагается, что вы, как пользователь и разработчик, понимаете свойства зависимостей и ознакомились с разделами [Общие сведения о свойствах зависимости](dependency-properties-overview.md) и [Пользовательские свойства зависимостей](custom-dependency-properties.md). Следует также прочитать разделы [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) и [Подробное описание синтаксиса XAML](xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Реализация загрузчика XAML WPF и производительность  
 По причинам реализации, это вычислительно дешевле, чтобы определить свойство как <xref:System.Windows.DependencyObject.SetValue%2A> свойство зависимости и получить доступ к методу системы свойств, чтобы установить его, а не с помощью обертки свойства и его сеттер. Причина этого заключается в том, что процессору [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] требуется вывести всю объектную модель вспомогательного кода, основываясь только на сведениях о типе и связях между членами, которые определены структурой разметки и различными строками.  
  
 Тип просматривается через комбинацию xmlns и атрибутов сборки, но идентифицирует членов, определяя, какие из них могут поддерживать установку в качестве атрибута, и разрешая, какие типы поддержки значений свойств в противном случае потребовали бы обширного отражения с помощью. <xref:System.Reflection.PropertyInfo> Поскольку свойства зависимости от данного типа доступны в виде [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] таблицы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] хранения через систему свойств, реализация его процессора использует эту <xref:System.Windows.DependencyObject.SetValue%2A> таблицу <xref:System.Windows.DependencyObject> и выводит, что любое данное свойство *ABC* может быть более эффективно установлено, вызывая содержащий производный тип, используя идентификатор свойств зависимости *ABCProperty.*  
  
<a name="implications"></a>
## <a name="implications-for-custom-dependency-properties"></a>Последствия использования пользовательских свойств зависимостей  
 Так как текущая реализация процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] при установке свойства полностью обходит оболочки, не следует помещать дополнительную логику в определения метода set оболочки для пользовательского свойства зависимости. Если поместить такую логику в определение метода set, она не будет выполняться, если свойство задается в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а не в коде.  
  
 Аналогичным образом, другие аспекты [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора, которые получают значения свойств от [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обработки также использовать, <xref:System.Windows.DependencyObject.GetValue%2A> а не с помощью обертки. Таким образом, следует также избегать `get` какой-либо дополнительной реализации в определении за пределами <xref:System.Windows.DependencyObject.GetValue%2A> вызова.  
  
 Следующим примером является рекомендуемое определение свойств зависимости с обертками, `public` `static` `readonly` где идентификатор свойств хранится в виде поля, `get` а определения и `set` определения не содержат кода за пределами необходимых методов системы свойств, определяющих поддержку свойств зависимости.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Метаданные свойства зависимости](dependency-property-metadata.md)
- [Свойства зависимостей типа коллекции](collection-type-dependency-properties.md)
- [Безопасность свойства зависимости](dependency-property-security.md)
- [Шаблоны безопасного конструктора для DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md)
