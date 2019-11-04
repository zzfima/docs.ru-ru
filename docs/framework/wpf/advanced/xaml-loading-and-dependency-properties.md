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
ms.openlocfilehash: 57c25297f995acd1ef307466258b5f4e03cc3098
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459544"
---
# <a name="xaml-loading-and-dependency-properties"></a>Загрузка кода XAML и свойства зависимостей
Текущая реализация процессора [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], по сути, учитывает свойство зависимостей. При загрузке двоичных файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и обработке атрибутов, которые являются свойствами зависимостей, процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует методы системы свойств для свойств зависимостей. При этом выполняется обход оболочек свойств. При реализации пользовательских свойств зависимостей необходимо учитывать такое поведение и избегать размещения любого другого кода в оболочке свойств, отличной от методов системы свойств <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A>.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Необходимые компоненты  
 В этом разделе предполагается, что вы, как пользователь и разработчик, понимаете свойства зависимостей и ознакомились с разделами [Общие сведения о свойствах зависимости](dependency-properties-overview.md) и [Пользовательские свойства зависимостей](custom-dependency-properties.md). Следует также прочитать разделы [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) и [Подробное описание синтаксиса XAML](xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Реализация загрузчика XAML WPF и производительность  
 В целях реализации для того, чтобы определить свойство как свойство зависимости и получить доступ к системе свойств <xref:System.Windows.DependencyObject.SetValue%2A> методу, чтобы задать его, вместо использования оболочки свойства и ее метода задания требуется меньше затрат. Причина этого заключается в том, что процессору [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] требуется вывести всю объектную модель вспомогательного кода, основываясь только на сведениях о типе и связях между членами, которые определены структурой разметки и различными строками.  
  
 Тип определяется сочетанием атрибутов xmlns и сборки, но определение элементов, определение того, какие из них могут поддерживаться в качестве атрибута, и разрешение типов, которые поддерживаются значениями свойств, в противном случае требуют расширенного отражения. Использование <xref:System.Reflection.PropertyInfo>. Поскольку свойства зависимостей для данного типа доступны в виде таблицы хранения через систему свойств, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ная реализация процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] использует эту таблицу и определяет, что любое заданное свойство *ABC* может быть более эффективно установлено вызов <xref:System.Windows.DependencyObject.SetValue%2A> для содержащего <xref:System.Windows.DependencyObject> производного типа с помощью идентификатора свойства зависимостей *абкпроперти*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Последствия использования пользовательских свойств зависимостей  
 Так как текущая реализация процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] при установке свойства полностью обходит оболочки, не следует помещать дополнительную логику в определения метода set оболочки для пользовательского свойства зависимости. Если поместить такую логику в определение метода set, она не будет выполняться, если свойство задается в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а не в коде.  
  
 Аналогичным образом, другие аспекты процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], которые получают значения свойств из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обработки, также используют <xref:System.Windows.DependencyObject.GetValue%2A>, а не с помощью оболочки. Поэтому следует также избегать дополнительной реализации в определении `get` за пределами <xref:System.Windows.DependencyObject.GetValue%2A> вызова.  
  
 В приведенном ниже примере показано рекомендуемое определение свойства зависимости с оболочками, где идентификатор свойства хранится в виде поля с атрибутами `public` `static` `readonly`, а определения методов `get` и `set` не содержат никакого кода, кроме необходимых методов системы свойств, определяющих резервное свойство зависимости.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Метаданные свойства зависимостей](dependency-property-metadata.md)
- [Свойства зависимостей типа коллекции](collection-type-dependency-properties.md)
- [Безопасность свойства зависимостей](dependency-property-security.md)
- [Шаблоны безопасного конструктора для DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md)
