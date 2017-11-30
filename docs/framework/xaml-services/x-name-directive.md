---
title: "Директива x:Name"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 90f0d27f3bf5adffe8a9b47940451e71fda082b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xname-directive"></a>Директива x:Name
Однозначно определяет элементы, определенные в XAML, в области имен XAML. Области видимости имен XAML и их уникальность моделей могут применяться к экземпляры объектов при платформы предоставляют интерфейсы API или реализации поведений, которые обращаются к graph XAML-объекта, созданного во время выполнения.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`XAMLNameValue`|Строку, которая соответствует ограничениям [Грамматика XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
  
## <a name="remarks"></a>Примечания  
 После `x:Name` применяется к платформу резервное модель программирования, имя соответствует переменной, содержащей ссылку на объект или как возвращаемым конструктором экземпляра.  
  
 Значение `x:Name` использование директив должно быть уникальным в пределах пространства имен XAML. По умолчанию при использовании API служб XAML .NET Framework, в основной области имен XAML определяется в корневом элементе XAML одной рабочей среды XAML и включает в себя элементы, содержащиеся в этой рабочей среды XAML. Дополнительные дискретные области видимости имен XAML, могут происходить в одной рабочей среды XAML могут определяться платформами для конкретных сценариев. Например в WPF новые области имен XAML определяются и созданные шаблоном, который также определен на этой рабочей среды XAML. Дополнительные сведения об области видимости имен XAML (записанных для WPF, но относящихся ко много общих концепций области видимости имен XAML) см. в разделе [области имен XAML WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 Как правило `x:Name` не следует применять в ситуациях, которые также используют `x:Key`. Реализации XAML конкретными платформами, существующие была введена концепция подстановки между `x:Key` и `x:Name`, но не рекомендуется. При обработке имени и ключа сведения, такие как служб XAML .NET framework не поддерживает такие понятия подстановки <xref:System.Windows.Markup.INameScope> или <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Правила разрешения атрибута `x:Name` а также принудительное применение уникальность имени потенциально определяются конкретными реализациями платформ. Тем не менее, который можно использовать со службами XAML .NET Framework, определения framework уникальности области видимости имен XAML должно быть согласовано с определением <xref:System.Windows.Markup.INameScope> сведения в этой документации и следует использовать те же правила, касающиеся where сведения о применении. Например [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] реализации которой различные элементы разметки в отдельные <xref:System.Windows.NameScope> диапазоны, например словари ресурсов, логическое дерево, созданные XAML уровня страниц, шаблоны и другие отложенного содержимого и затем применяет XAML уникальность имени в каждой из этих областей видимости имен XAML.  
  
 Для пользовательских типов, использующих средства записи объектов XAML служб XAML .NET Framework, свойство, сопоставляемый `x:Name` на тип можно установить или изменить. Это поведение определяется, ссылаясь на имя свойства для сопоставления с <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> в коде определения типа.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>Представляет атрибут уровня типа.  
  
 Службы XAML структуры Using.NET, логика резервного поддержку области имен XAML можно определить как нейтральную framework путем реализации <xref:System.Windows.Markup.INameScope> интерфейса.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 В стандартной конфигурации построения для [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] приложения, использующего XAML, разделяемые классы и код программной части, указанный `x:Name` становится имя поля, которое создается в основной код, при [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] обрабатываемых разметки задачи компиляции сборки и это поле содержит ссылку на объект. По умолчанию созданное поле является внутренним. Доступ к полю можно изменить, указав [атрибут x: FieldModifier](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md). В WPF и Silverlight последовательность является определяет компиляции разметки и имена полей в разделяемый класс, однако это значение изначально пуста. Затем созданный метод с именем `InitializeComponent` вызывается из конструктора класса. `InitializeComponent`состоит из `FindName` вызовы с использованием всех `x:Name` значения, которые существуют в части разделяемого класса как определенные в XAML входных строк. Возвращаемые значения затем присваивается ссылка на поле с одинаковыми именами для заполнения значений полей с объектами, которые были созданы на основе XAML синтаксического анализа. Выполнение `InitializeComponent` делают возможным граф объекта время выполнения с помощью ссылки `x:Name` / имя поля напрямую, вместо того, чтобы вызвать `FindName` явным образом в любое время, требуется ссылка на объект, определенные в XAML.  
  
 Для приложения WPF, использующего [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] предназначен и включает файлы XAML с `Page` действия построения, отдельное свойство ссылки создается во время компиляции, который добавляет `WithEvents` ключевое слово, чтобы все элементы, имеющие `x:Name`в поддерживает `Handles` синтаксис для делегатов обработчика событий. Это свойство всегда является открытым. Дополнительные сведения см. в разделе [Обработка событий в Visual Basic и WPF](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name`используется обработчиком WPF XAML для регистрации имени в области видимости имен XAML во время загрузки, даже в тех случаях, когда страница не скомпилированного с разметкой путем сборки действий (например, свободного XAML словарь ресурсов). Одна из причин такое поведение обусловлено `x:Name` могут потребоваться для <xref:System.Windows.Data.Binding.ElementName%2A> привязки. Дополнительные сведения см. в разделе [Общие сведения о привязке данных](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Как упоминалось ранее, `x:Name` (или `Name`) не следует применять в ситуациях, которые также используют `x:Key`. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> Имеет специальное поведение определение себя в качестве пространства имен XAML, но возврат не реализована или значения null для <xref:System.Windows.Markup.INameScope> интерфейсы API, как способ обеспечения такого поведения. Если средство синтаксического анализа WPF XAML сталкивается `Name` или `x:Name` в определенных XAML <xref:System.Windows.ResourceDictionary>, имя не добавляется в любой области видимости имен XAML. Предпринимается попытка найти это имя из любой области видимости имен XAML и `FindName` методы не возвращают правильные результаты.  
  
### <a name="xname-and-name"></a>x: Name и имя  
 Многих сценариях приложений WPF можно избежать любое использование `x:Name` атрибут, так как `Name` свойств зависимостей как указано в значение по умолчанию пространства имен XAML для нескольких важных базовых классов такие как <xref:System.Windows.FrameworkElement> и <xref:System.Windows.FrameworkContentElement> удовлетворяет этой же цели. Все еще существуют некоторые распространенные сценарии XAML и WPF когда код доступа к элементу не `Name` свойства на уровне framework важен. Например, не поддерживают определенные классы поддержки анимации и раскадровки `Name` свойства, но они часто требуется ссылка в коде, чтобы контролировать анимации. Следует указать `x:Name` как атрибут шкал времени и преобразований, созданных в XAML, если вы планируете позже ссылкой из кода.  
  
 Если <xref:System.Windows.FrameworkElement.Name%2A> доступен как свойство класса, <xref:System.Windows.FrameworkElement.Name%2A> и `x:Name` можно взаимозаменяемо использовать в качестве атрибутов, но приведет к исключения синтаксического анализа, если указаны оба того же элемента. Если компиляции разметки XAML, возникает исключение при компиляции разметки, в противном случае возникает при загрузке.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>можно задать с помощью синтаксиса атрибутов XAML и в коде с помощью <xref:System.Windows.DependencyObject.SetValue%2A>; Обратите внимание, однако эту настройку <xref:System.Windows.FrameworkElement.Name%2A> свойства в коде не создает действительная ссылка на поле в области имен XAML, в большинстве случаев, где уже XAML загрузить. Вместо выполняется настройка <xref:System.Windows.FrameworkElement.Name%2A> в коде используйте <xref:System.Windows.NameScope> методов из кода для соответствующих имен.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>Можно также задать с помощью синтаксиса элемента свойства с внутренний текст, но это редко. Напротив `x:Name` невозможно задать в синтаксис элемента свойства XAML или в коде с помощью <xref:System.Windows.DependencyObject.SetValue%2A>; его можно задать только с помощью синтаксиса атрибутов объектов, так как он является директивой.  
  
## <a name="silverlight-usage-notes"></a>Примечания об использовании Silverlight  
 `x:Name`для Silverlight задокументирован отдельно. Дополнительные сведения см. в разделе [пространства имен XAML (x:) Языковые возможности (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>  
 [Деревья в WPF](../../../docs/framework/wpf/advanced/trees-in-wpf.md)
