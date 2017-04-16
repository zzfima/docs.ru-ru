---
title: "Привязка расширения разметки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Binding"
helpviewer_keywords: 
  - "Привязка расширений разметки"
  - "XAML, привязка расширения разметки"
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Привязка расширения разметки
Определяет значение свойства как значение с привязкой к данным, создавая объект промежуточного выражения и интерпретируя контекст данных, применяемый к элементу и его привязке во время выполнения.  
  
## Использование выражений привязки  
  
```  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## Примечания по синтаксису  
 В этих синтаксисах `[]` и `*` не являются литералами.  Они представляют собой часть нотации, указывающую, что можно использовать любое количество пар *свойство\_привязки*`=`*значение*, включая ноль, устанавливая разделитель `,` между ними и предыдущими парами *свойство\_привязки*`=`*значение*.  
  
 Вместо этого можно задать любые свойства, перечисленные в разделе "Свойства привязки, которые могут быть установлены с расширением Binding", с помощью атрибутов объектного элемента <xref:System.Windows.Data.Binding>.  Однако в действительности это не использование расширения разметки <xref:System.Windows.Data.Binding>, это лишь общая обработка XAML атрибутов, задающих свойства класса <xref:System.Windows.Data.Binding> CLR.  Другими словами, `<Binding` *свойство\_привязки\_1*`="`*значение\_1*`"[` *свойство\_привязки\_N*`="`*значение\_N*`"]*/>` — это эквивалентный синтаксис для использования атрибутов элемента объекта <xref:System.Windows.Data.Binding> вместо использования выражения `Binding`.  Дополнительные сведения об использовании атрибута XAML с конкретными свойствами <xref:System.Windows.Data.Binding> см. в разделе "Использование атрибута XAML" для соответствующего свойства <xref:System.Windows.Data.Binding> в библиотеке классов платформы .NET Framework.  
  
## Значения XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Имя свойства <xref:System.Windows.Data.Binding> или <xref:System.Windows.Data.BindingBase>, которое требуется задать.  Не все свойства <xref:System.Windows.Data.Binding> можно задать с расширением `Binding`, а некоторые свойства задаются в выражении `Binding` только с помощью дальнейших вложенных расширений разметки.  См. раздел «Свойства привязки, которые могут быть установлены с расширением Binding».|  
|`value1, valueN`|Значение, задаваемое для свойства.  Обработка значения атрибута, в конечном счете, уникальна для типа и логики конкретного задаваемого свойства <xref:System.Windows.Data.Binding>.|  
|`path`|Строка пути, задающая неявное свойство <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>.  См. также раздел [Синтаксис PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## Неизвестная {Binding}  
 При использовании `{Binding}`, описанном в разделе "Использование выражений привязки", создается объект <xref:System.Windows.Data.Binding> со значениями по умолчанию, включающими начальное свойство <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>, для которого задано значение `null`.  Это все еще полезно во многих сценариях, поскольку созданный <xref:System.Windows.Data.Binding> может полагаться на ключевые свойства привязки данных, такие как <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> и <xref:System.Windows.Data.Binding.Source%2A?displayProperty=fullName>, задаваемые в контексте данных времени выполнения.  Дополнительные сведения о концепции контекста данных см. в разделе [Привязка данных](../../../../docs/framework/wpf/data/data-binding-wpf.md).  
  
## Неявный путь  
 Расширение разметки `Binding` использует <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> как концептуальное "свойство по умолчанию", где нет необходимости отображать `Path=` в выражении.  При указании выражения `Binding` с неявным путем он должен сначала отображаться в выражении до любых других пар `bindProp`\=`value`, в которых свойство <xref:System.Windows.Data.Binding> задано по имени.  Пример. `{Binding PathString}`, где `PathString` — это строка, рассматриваемая как значение свойства <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> в <xref:System.Windows.Data.Binding>, созданном с помощью расширения разметки.  Можно добавить неявный путь с другими именованными свойствами после разделительной запятой, например `{Binding LastName, Mode=TwoWay}`.  
  
## Свойства привязки, которые могут быть установлены с расширением Binding  
 В приведенном здесь синтаксисе используется обычное приближенное значение `bindProp`\= `value`, поскольку существует множество предназначенных для чтения и записи свойств <xref:System.Windows.Data.BindingBase> или <xref:System.Windows.Data.Binding>, которые можно задать с помощью синтаксиса выражения и расширения разметки `Binding`.  Их можно задать в любом порядке, за исключением неявного свойства <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>.  \(Имеется возможность явно задать `Path=`, при этом его также можно задать в любом порядке.\)  По существу, можно задать любое количество свойств, включая ноль, в списке ниже, используя пары `bindProp`\=`value`, разделенные запятыми.  
  
 Некоторым из этих значений свойств требуются типы объектов, не поддерживающие собственное преобразование типов из текстового синтаксиса в XAML, то есть требуется задание расширений разметки в качестве значения атрибута.  Дополнительные сведения о каждом свойстве см. в разделе "Использование атрибута XAML" в библиотеке классов платформы .NET Framework. Строка, используемая для синтаксиса атрибута XAML с дальнейшим использованием расширения разметки или без него, по существу, аналогична значению, задаваемому в выражении `Binding`, за исключением того, что кавычки вокруг каждой пары `bindProp`\=`value` в выражении `Binding` не вставляются.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>. Строка, определяющая возможную группу привязки.  Это относительно новое понятие привязки. Дополнительные сведения по свойству <xref:System.Windows.Data.BindingBase.BindingGroupName%2A> см. на странице ссылок.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>. Логическое свойство, которому может быть присвоено как значение `true`, так и `false`.  Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>. Можно задать как строку `bindProp`\=`value` в выражении, но для этого требуется ссылка на объект для значения, например [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  Значение в данном случае является экземпляром класса пользовательского преобразователя.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>. Можно задать в выражении в качестве стандартного идентификатора. Дополнительные сведения по свойству <xref:System.Windows.Data.Binding.ConverterCulture%2A> см. в справочном разделе.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>. Можно задать как строку `bindProp`\=`value` в выражении, но это зависит от типа передаваемого параметра.  При передаче типа по ссылке для значения для такого использования требуется ссылка на объект, например вложенный [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: взаимоисключающее с <xref:System.Windows.Data.Binding.RelativeSource%2A> и <xref:System.Windows.Data.Binding.Source%2A>; каждое из этих свойств привязки представляет определенную методологию привязки.  Дополнительные сведения см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>. Можно задать как строку `bindProp`\=`value` в выражении, но это зависит от типа передаваемого значения.  При передаче типа по ссылке требуется ссылка на объект, например вложенный [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>. Логическое свойство, которому может быть присвоено как значение `true`, так и `false`.  Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>. *значение* является именем константы из перечисления <xref:System.Windows.Data.BindingMode>.  Например, `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>. Логическое свойство, которому может быть присвоено как значение `true`, так и `false`.  Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>. Логическое свойство, которому может быть присвоено как значение `true`, так и `false`.  Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>. Логическое свойство, которому может быть присвоено как значение `true`, так и `false`.  Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>. Строка, описывающая путь к объекту данных или общей объектной модели.  Формат предоставляет несколько разных соглашений для обхода объектной модели, для которой не приводится соответствующего описания в этом разделе.  Дополнительные сведения см. в разделе [Синтаксис PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: взаимоисключает свойства <xref:System.Windows.Data.Binding.ElementName%2A> и <xref:System.Windows.Data.Binding.Source%2A>; каждое из этих свойств привязки представляет определенную методологию привязки.  Дополнительные сведения см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  Требует использование вложенного [Расширение разметки RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) для задания значения.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: взаимоисключающее с <xref:System.Windows.Data.Binding.RelativeSource%2A> и <xref:System.Windows.Data.Binding.ElementName%2A>; каждое из этих свойств привязки представляет определенную методологию привязки.  Дополнительные сведения см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  Требует использование вложенного расширения, как правило, [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md), относящегося к источнику данных объекта из словаря ресурсов с ключом.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>. Строка, описывающая соглашение формата строки для связанных данных.  Это относительно новое понятие привязки. Дополнительные сведения по свойству <xref:System.Windows.Data.BindingBase.StringFormat%2A> см. на странице ссылок.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>. Можно задать как строку `bindProp`\=`value` в выражении, но это зависит от типа передаваемого параметра.  При передаче типа по ссылке для значения требуется ссылка на объект, например вложенный [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>. *значение* является именем константы из перечисления <xref:System.Windows.Data.UpdateSourceTrigger>.  Например, `{Binding UpdateSourceTrigger=LostFocus}`.  Потенциально определенные элементы управления имеют разные значения по умолчанию для этого свойства привязки.  Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>. Логическое свойство, которому может быть присвоено как значение `true`, так и `false`.  Значение по умолчанию — `false`.  См. примечания.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>. Логическое свойство, которому может быть присвоено как значение `true`, так и `false`.  Значение по умолчанию — `false`.  См. примечания.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>. Строка, описывающая путь к XMLDOM источника данных XML.  Дополнительные сведения см. в разделе [Привязка к XML\-данным с помощью XMLDataProvider и запросов XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Ниже перечислены свойства <xref:System.Windows.Data.Binding>, которые невозможно задать с помощью расширения разметки `Binding`\/формы выражения `{Binding}`.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: это свойство ожидает ссылку на реализацию обратного вызова.  На обратные вызовы и методы, отличные от обработчиков событий, нельзя ссылаться в синтаксисе XAML.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>. Принимает универсальную коллекцию объектов <xref:System.Windows.Controls.ValidationRule>.  Это можно выразить как элемент свойства в объектном элементе <xref:System.Windows.Data.Binding>, но метод разбора атрибута для использования в выражении `Binding`, доступный сразу, отсутствует.  См. раздел справки, посвященный <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## Заметки  
  
> [!IMPORTANT]
>  В отношении приоритета свойств зависимостей выражение `Binding` эквивалентно локальному заданному значению.  Если установить локальное значение для свойства, в котором ранее имелось выражение `Binding`, то `Binding` полностью удаляется.  Дополнительные сведения см. в разделе [Приоритет значения свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Описание привязки данных на базовом уровне не рассматривается в этом разделе.  Дополнительные сведения см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding> и <xref:System.Windows.Data.PriorityBinding> не поддерживают синтаксис расширения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Вместо этого используйте  элементы свойств.  См. разделы справки, посвященные <xref:System.Windows.Data.MultiBinding> и <xref:System.Windows.Data.PriorityBinding>.  
  
 Логические значения для XAML нечувствительные к реестру.  Например, можно указать либо `{Binding NotifyOnValidationError=true}`, либо `{Binding NotifyOnValidationError=True}`.  
  
 Привязки, задействующие проверку данных, обычно задаются явным элементом `Binding`, а не как выражение `{Binding ...}`, а установка в качестве значений свойств <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> или <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> выражений встречается редко.  Это происходит потому, что сопутствующее свойство <xref:System.Windows.Data.Binding.ValidationRules%2A> нельзя без труда задать в форме выражения.  Дополнительные сведения см. в разделе [Реализация проверки привязки](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md).  
  
 `Binding` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем установка атрибутов преобразователей типов для определенных типов или свойств.  Все расширения разметки в XAML используют знаки `{` и `}` в синтаксисе своих атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать содержимое строки.  Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 `Binding` является необычным расширением разметки в том, что класс <xref:System.Windows.Data.Binding>, реализующий функциональные возможности расширения для реализации XAML в WPF, также реализует несколько других методов и свойств, которые не связаны с XAML.  Другие члены предназначены для того, чтобы сделать <xref:System.Windows.Data.Binding> более гибким и самодостаточным классом, для которого может использоваться множество сценариев привязки данных в дополнение к функционированию в качестве расширения разметки XAML.  
  
## См. также  
 <xref:System.Windows.Data.Binding>   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)