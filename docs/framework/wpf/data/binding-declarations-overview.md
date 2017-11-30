---
title: "Общие сведения об объявлении привязок"
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
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28b139f6ea2aad41e4d733e8c622699f2474b3e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="binding-declarations-overview"></a>Общие сведения об объявлении привязок
В этом разделе описываются различные способы объявления привязок.  
  
 
  
<a name="Prereq"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Важно, чтобы перед прочтением этого раздела вы были знакомы с основными понятиями и принципами использования расширений разметки. Подробнее о расширениях разметки см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 В этом разделе не рассматриваются сведения о привязке данных. Описание концепции привязки данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
<a name="BindinginXAML"></a>   
## <a name="declaring-a-binding-in-xaml"></a>Объявление привязки в XAML  
 В этом разделе описывается объявление привязки в XAML.  
  
<a name="MarkupExtensionSyntax"></a>   
### <a name="markup-extension-usage"></a>Использование расширения разметки  
 <xref:System.Windows.Data.Binding> является расширением разметки. Если для объявления привязки вы используете расширение привязки, то объявление состоит из ряда предложений, следующих за ключевым словом `Binding` и разделенных запятыми (,). Предложения в объявлении привязки могут следовать в любом порядке, и существует множество различных комбинаций. Эти предложения представляют *имя*=*значение* пары where *имя* имя <xref:System.Windows.Data.Binding> свойство и *значение* — значение настраиваемого свойства.  
  
 При создании строк объявления привязки в разметке они должны быть присоединены к конкретному свойству зависимостей целевого объекта. Следующий пример показывает, как привязать <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> свойства с помощью расширения привязки, указав <xref:System.Windows.Data.Binding.Source%2A> и <xref:System.Windows.Data.Binding.Path%2A> свойства.  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Большинство свойств можно указать <xref:System.Windows.Data.Binding> таким способом. Дополнительные сведения о расширении привязки, а также список <xref:System.Windows.Data.Binding> свойства, которые нельзя задать с помощью расширения привязки в разделе [расширение разметки со связыванием](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) Обзор.  
  
<a name="ObjectElementSyntax"></a>   
### <a name="object-element-syntax"></a>Синтаксис объектных элементов  
 Синтаксис объектных элементов является альтернативой созданию объявления привязки. В большинстве случаев нет каких-то специальных преимуществ в использовании либо только расширения разметки, либо только синтаксиса объектных элементов. Но в тех случаях, когда расширение разметки не подходит конкретно для вашего сценария (например, если значение свойства имеет нестроковый тип, для которого не существует преобразования), то следует использовать синтаксис объектных элементов.  
  
 Ниже приведен пример использования синтаксиса объектных элементов и расширения разметки:  
  
 [!code-xaml[BindConversionMarkup#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]  
  
 В примере выполняется привязка <xref:System.Windows.Controls.TextBlock.Foreground%2A> , объявляя привязки с помощью синтаксиса расширения. В объявлении привязки для <xref:System.Windows.Controls.TextBlock.Text%2A> свойство использует синтаксис элемента объекта.  
  
 Дополнительные сведения о различных терминах см. в разделе [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="MBandPB"></a>   
### <a name="multibinding-and-prioritybinding"></a>Классы MultiBinding и PriorityBinding  
 <xref:System.Windows.Data.MultiBinding>и <xref:System.Windows.Data.PriorityBinding> не поддерживают синтаксис расширения XAML. Таким образом, необходимо использовать синтаксис элемента объекта, если вы объявляете <xref:System.Windows.Data.MultiBinding> или <xref:System.Windows.Data.PriorityBinding> в XAML.  
  
<a name="BindinginCode"></a>   
## <a name="creating-a-binding-in-code"></a>Создание привязки в коде  
 Другим способом задания привязки является установка свойств непосредственно на <xref:System.Windows.Data.Binding> объекта в коде. В следующем примере показано, как создать <xref:System.Windows.Data.Binding> объекта и указать свойства в коде.  В этом примере `TheConverter` — это объект, реализующий <xref:System.Windows.Data.IValueConverter> интерфейса.  
  
 [!code-csharp[BindConversion#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
 [!code-vb[BindConversion#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]  
[!code-csharp[BindConversion#end1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#end1)]
[!code-vb[BindConversion#end1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#end1)]  
  
 Если объект выполняется привязка <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> можно вызвать `SetBinding` метод объекта напрямую, а не с помощью <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>. Пример см. в разделе [Создание привязки в коде](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md).  
  
<a name="Path_Syntax"></a>   
## <a name="binding-path-syntax"></a>Синтаксис пути привязки  
 Используйте <xref:System.Windows.Data.Binding.Path%2A> свойство, чтобы указать исходное значение, которое вы хотите привязать к:  
  
-   В самом простом случае <xref:System.Windows.Data.Binding.Path%2A> значение свойства является именем свойства исходного объекта, используемого для привязки, такие как `Path=PropertyName`.  
  
-   Подсвойства какого-либо свойства можно задавать, используя синтаксис, схожий с синтаксисом [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]. Например, предложение `Path=ShoppingCart.Order` задает привязку к подсвойству `Order` объекта или свойства `ShoppingCart`.  
  
-   Для привязки присоединенного свойства заключите его в скобки. Например, для привязки к вложенное свойство <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, синтаксис `Path=(DockPanel.Dock)`.  
  
-   Индексаторы свойства можно указать в квадратных скобках после имени свойства, для которого применяется индексатор. Например, предложение `Path=ShoppingCart[0]` задает привязку к индексу, который соответствует способу, который внутренняя индексация свойства использует для обработки символьной строки "0". Также поддерживаются вложенные индексаторы.  
  
-   Индексаторы и вложенные свойства могут сочетаться в предложении `Path`, например, `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`  
  
-   Индексаторы могут иметь несколько внутренних параметров, разделенных запятыми (,). Тип каждого параметра указывается в скобках. Например, вы можете задать предложение `Path="[(sys:Int32)42,(sys:Int32)24]"`, где `sys` сопоставляется с пространством имен `System`.  
  
-   Если источником является представлением коллекции, текущий элемент можно указать с косой чертой (/). Например, предложение `Path=/` задает привязку к текущему элементу в представлении. Если источником является коллекция, этот синтаксис задает текущий элемент представления коллекции по умолчанию.  
  
-   Имена свойств и косые черты можно объединять для обхода свойств, которые являются коллекциями. Например, предложение `Path=/Offices/ManagerName` задает текущий элемент коллекции источников, где свойство `Offices` также является коллекцией. Текущий элемент этой коллекции — объект, содержащий свойство `ManagerName`.  
  
-   При необходимости для привязки к текущему источнику можно использовать путь в виде точки (.). Например, предложение `Text="{Binding}"` эквивалентно предложению `Text="{Binding Path=.}"`.  
  
### <a name="escaping-mechanism"></a>Механизм экранирования  
  
-   Внутри индексаторов ([]) знак крышки (^) задает экранирование следующего символа.  
  
-   Если задать <xref:System.Windows.Data.Binding.Path%2A> в XAML, также необходимо экранировать (с помощью сущностей XML) некоторые символы, которые являются особыми для определения языка XML:  
  
    -   Используйте `&` в качестве escape-символа для символа &.  
  
    -   Используйте `>` для экранирования закрывающего тега ">".  
  
-   Кроме того, если вы задаете всю привязку в атрибуте, используя синтаксис расширения разметки, необходимо экранировать (с помощью обратной косой черты \\) символы, которые являются специфическими для синтаксического анализатора расширения разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    -   Обратная косая черта (\\) сама по себе является escape-символом.  
  
    -   Знак равенства (=) разделяет имя свойства и значение этого свойства.  
  
    -   Запятая (,) отделяет свойства друг от друга.  
  
    -   Закрывающая фигурная скобка (}) указывает конец расширения разметки.  
  
<a name="Default"></a>   
## <a name="default-behaviors"></a>Поведение по умолчанию  
 Поведение по умолчанию выглядит следующим образом, если не указано в объявлении.  
  
-   Создается преобразователь по умолчанию, который пытается выполнить преобразование типов между значением источника привязки и значением целевого объекта привязки. Если преобразование не удается выполнить, преобразователь по умолчанию возвращает значение `null`.  
  
-   Если вы не установите <xref:System.Windows.Data.Binding.ConverterCulture%2A>, использует механизм привязки `Language` свойства целевого объекта привязки. В языке XAML это свойство по умолчанию имеет значение "en-US" или наследует свое значение от корневого элемента (или любого элемента) страницы, если оно было задано явным образом.  
  
-   При условии, что привязка уже имеет контекст данных (например, контекст данных, наследуемый от родительского элемента), а объект или коллекция, возвращаемые этим контекстом, подходят для привязки без необходимости дополнительного изменения пути, объявление привязки может вообще не иметь предложений: `{Binding}`. Таким способом привязка часто задается для стилей данных, где привязка воздействует на коллекцию. Дополнительные сведения см. в подразделе "Использование всего объекта в качестве источника привязки" раздела [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
-   Значение по умолчанию <xref:System.Windows.Data.Binding.Mode%2A> может быть односторонним и двусторонним в свойство зависимостей, к которому осуществляется привязка. Режим привязки всегда можно объявить явным образом, чтобы обеспечить требуемое поведение привязки. В целом редактируемого свойства элемента управления такие как <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> и <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>, по умолчанию имеют двухсторонние привязки, в то время как большинство других свойств по умолчанию имеют односторонние привязки.  
  
-   Значение по умолчанию <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение зависит от используемого <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> и <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> в зависимости от того, в свойство привязанного зависимостей. Значение по умолчанию для большинства свойств зависимостей — <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, а свойство <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> имеет значение по умолчанию <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Синтаксис PropertyPath в XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)
