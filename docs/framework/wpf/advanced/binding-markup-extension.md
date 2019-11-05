---
title: Привязка расширения разметки
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: d0a437e756da16db978d8074c4355fd83d211b67
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453611"
---
# <a name="binding-markup-extension"></a>Привязка расширения разметки
Откладывает значение свойства на значение, привязанное к данным, создавая объект промежуточного выражения и обрабатывая контекст данных, который применяется к элементу и его привязке во время выполнения.  
  
## <a name="binding-expression-usage"></a>Использование выражений привязки  
  
```xaml  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>Примечания синтаксиса  
 В этих синтаксисах `[]` и `*` не являются литералами. Они являются частью нотации для указания того, что можно использовать ноль или более пар *биндпроп*`=`*значений* , с `,` разделителем между ними и предшествующими *биндпроп*`=`ными парами *значений* .  
  
 Все свойства, перечисленные в разделе "Свойства привязки, которые можно задать с помощью расширения привязки", вместо этого можно задать с помощью атрибутов элемента <xref:System.Windows.Data.Binding> объекта. Тем не менее, это не <xref:System.Windows.Data.Binding>использования расширения разметки, это просто общая обработка XAML атрибутов, устанавливающих свойства <xref:System.Windows.Data.Binding> класса CLR. Иными словами, `<Binding` *bindProp1*`="`*значение1*`"[` *биндпропн*`="`*Контрольное*`"]*/>` — это эквивалентный синтаксис для атрибутов <xref:System.Windows.Data.Binding> использования объектных элементов вместо использования выражения `Binding`. Дополнительные сведения об использовании атрибутов XAML для конкретных свойств <xref:System.Windows.Data.Binding>см. в разделе "использование атрибутов XAML" соответствующего свойства <xref:System.Windows.Data.Binding> в библиотеке классов .NET Framework.  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Имя свойства <xref:System.Windows.Data.Binding> или <xref:System.Windows.Data.BindingBase>, которое необходимо задать. Не все свойства <xref:System.Windows.Data.Binding> можно задать с помощью расширения `Binding`, а некоторые свойства могут быть заданы в выражении `Binding` только с помощью вложенных расширений разметки. См. раздел "Свойства привязки, которые могут быть установлены с помощью расширения привязки".|  
|`value1, valueN`|Значение, которое следует задать для свойства. Обработка значения атрибута в конечном итоге зависит от типа и логики конкретного устанавливаемого свойства <xref:System.Windows.Data.Binding>.|  
|`path`|Строка пути, которая задает неявное свойство <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. См. также [синтаксис PropertyPath языка XAML](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Неквалифицированная {Binding}  
 `{Binding}`ное использование, показанное в "использование выражения привязки", создает объект <xref:System.Windows.Data.Binding> со значениями по умолчанию, которые включают начальную <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> `null`. Это все еще полезно во многих сценариях, поскольку созданные <xref:System.Windows.Data.Binding> могут полагаться на ключевые свойства привязки данных, такие как <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> и <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> задаются в контексте данных времени выполнения. Дополнительные сведения о концепции контекста данных см. в разделе [Привязка данных](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Неявный путь  
 Расширение разметки `Binding` использует <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> в качестве концептуального свойства по умолчанию, где `Path=` не требуется указывать в выражении. Если указать `Binding` выражение с неявным путем, то перед любыми другими `bindProp`=`value` пары, в которых свойство <xref:System.Windows.Data.Binding> задано по имени, в выражении должен стоять неявный путь. Например: `{Binding PathString}`, где `PathString` — это строка, которая вычисляется как значение <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> в <xref:System.Windows.Data.Binding>, созданное с использованием расширения разметки. Можно добавить неявный путь с другими именованными свойствами после разделителя запятой, например `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Свойства привязки, которые можно задать с помощью расширения привязки  
 Синтаксис, приведенный в этом разделе, использует общую `bindProp`=`value` аппроксимации, так как существует множество свойств для чтения и записи <xref:System.Windows.Data.BindingBase> или <xref:System.Windows.Data.Binding>, которые можно задать с помощью синтаксиса `Binding` разметки/выражения. Их можно задать в любом порядке, за исключением неявного <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (У вас есть возможность явно указать `Path=`, в этом случае ее можно задать в любом порядке). По сути, можно задать ноль или несколько свойств в списке ниже, используя `bindProp`=`value` пары, разделенные запятыми.  
  
 Для некоторых из этих значений свойств требуются типы объектов, которые не поддерживают преобразование машинного типа из текстового синтаксиса в XAML и поэтому нуждаются в расширениях разметки для установки в качестве значения атрибута. Дополнительные сведения см. в разделе Использование атрибутов XAML в библиотеке классов .NET Framework для каждого свойства. Строка, используемая для синтаксиса атрибута XAML с дальнейшим использованием расширения разметки, по сути аналогична значению, указанному в `Binding` выражении, за исключением того, что кавычки вокруг каждого `bindProp`=`value` в выражение `Binding`.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: строка, определяющая возможную группу привязки. Это относительно сложная концепция привязки. <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>см. на странице справки.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolean, может иметь значение `true` или `false`. Значение по умолчанию: `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: можно задать в качестве `bindProp`=строки `value` в выражении, но для этого требуется ссылка на объект для значения, например [расширение разметки StaticResource](staticresource-markup-extension.md). Значение в этом случае является экземпляром пользовательского класса преобразователя.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: устанавливаемое в выражении как идентификатор на основе стандартов; см. раздел справки по <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: можно задать в качестве `bindProp`=`value` строку в выражении, но это зависит от типа передаваемого параметра. При передаче ссылочного типа для значения для этого использования требуется ссылка на объект, например вложенное [расширение разметки StaticResource](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: взаимоисключающее и <xref:System.Windows.Data.Binding.RelativeSource%2A> и <xref:System.Windows.Data.Binding.Source%2A>; Каждое из этих свойств привязки представляет конкретную методологию привязки. См. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: можно задать в качестве `bindProp`=`value` строку в выражении, но это зависит от типа передаваемого значения. При передаче ссылочного типа требуется ссылка на объект, например вложенное [расширение разметки StaticResource](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolean, может иметь значение `true` или `false`. Значение по умолчанию: `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *value* — это имя константы из перечисления <xref:System.Windows.Data.BindingMode>. Например, `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolean, может иметь значение `true` или `false`. Значение по умолчанию: `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolean, может иметь значение `true` или `false`. Значение по умолчанию: `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolean, может иметь значение `true` или `false`. Значение по умолчанию: `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: строка, описывающая путь к объекту данных или общей объектной модели. Формат предоставляет несколько различных соглашений для обхода объектной модели, которые не могут быть надлежащим образом описаны в этом разделе. См. раздел [синтаксис языка XAML PropertyPath](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: взаимоисключающее и с <xref:System.Windows.Data.Binding.ElementName%2A> и <xref:System.Windows.Data.Binding.Source%2A>; Каждое из этих свойств привязки представляет конкретную методологию привязки. См. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md). Для указания значения требуется вложенное использование [RelativeSource MarkupExtension](relativesource-markupextension.md) .  
  
- <xref:System.Windows.Data.Binding.Source%2A>: взаимоисключающее и <xref:System.Windows.Data.Binding.RelativeSource%2A> и <xref:System.Windows.Data.Binding.ElementName%2A>; Каждое из этих свойств привязки представляет конкретную методологию привязки. См. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md). Требует вложенного расширения, обычно это [расширение разметки StaticResource](staticresource-markup-extension.md) , которое ссылается на источник данных объекта из словаря ресурсов с ключом.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: строка, описывающая соглашение о формате строки для привязанных данных. Это относительно сложная концепция привязки. <xref:System.Windows.Data.BindingBase.StringFormat%2A>см. на странице справки.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: можно задать в качестве `bindProp`=`value` строку в выражении, но это зависит от типа передаваемого параметра. При передаче ссылочного типа для значения требуется ссылка на объект, например вложенное [расширение разметки StaticResource](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *value* — это имя константы из перечисления <xref:System.Windows.Data.UpdateSourceTrigger>. Например, `{Binding UpdateSourceTrigger=LostFocus}`. Определенные элементы управления потенциально имеют разные значения по умолчанию для этого свойства привязки. См. раздел <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolean, может иметь значение `true` или `false`. Значение по умолчанию: `false`. См. заметки.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolean, может иметь значение `true` или `false`. Значение по умолчанию: `false`. См. заметки.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: строка, описывающая путь к XMLDOM источника XML-данных. См. статью [Привязка к XML-данным с помощью XmlDataProvider и запросов XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Ниже приведены свойства <xref:System.Windows.Data.Binding>, которые не могут быть заданы с помощью формы выражения расширения разметки `Binding`/`{Binding}`.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: это свойство принимает ссылку на реализацию обратного вызова. В синтаксисе XAML нельзя ссылаться на обратные вызовы и методы, отличные от обработчиков событий.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: свойство принимает универсальную коллекцию объектов <xref:System.Windows.Controls.ValidationRule>. Это может быть выражено как элемент свойства в <xref:System.Windows.Data.Binding> элементе объекта, но в выражении `Binding` не имеет легко доступной методики синтаксического анализа атрибутов. См. раздел Справочник по <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Заметки  
  
> [!IMPORTANT]
> В плане приоритета свойства зависимости `Binding` выражение эквивалентно локально заданному значению. Если задать локальное значение для свойства, которое ранее имело `Binding` выражение, `Binding` будет полностью удалена. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](dependency-property-value-precedence.md).  
  
 Описание привязки данных на базовом уровне не рассматривается в этом разделе. См. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding> и <xref:System.Windows.Data.PriorityBinding> не поддерживают синтаксис расширения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Вместо этого следует использовать элементы свойств. <xref:System.Windows.Data.MultiBinding> и <xref:System.Windows.Data.PriorityBinding>см. в справочных материалах.  
  
 Логические значения для XAML не учитывают регистр. Например, можно указать либо `{Binding NotifyOnValidationError=true}`, либо `{Binding NotifyOnValidationError=True}`.  
  
 Привязки, которые подразумевают проверку данных, обычно задаются явно `Binding`ным элементом, а не `{Binding ...}` выражением, и установка <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> или <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> в выражении является редким. Это связано с тем, что сопутствующее свойство <xref:System.Windows.Data.Binding.ValidationRules%2A> не может быть легко задано в форме выражения. Дополнительные сведения см. в разделе [Реализация проверки привязки](../data/how-to-implement-binding-validation.md).  
  
 `Binding` является расширением разметки. Расширения разметки обычно реализуются, если требуется, чтобы значения атрибутов были другими, чем литеральные значения или имена обработчиков, а требование является более глобальным, чем преобразователи типов, имеющие атрибуты для определенных типов или свойств. Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе атрибутов, что является соглашением, по которому обработчик XAML распознает, что расширение разметки должно обработать содержимое строки. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding` является нетипичным расширением разметки в том, что класс <xref:System.Windows.Data.Binding>, реализующий функциональность расширения для реализации XAML в WPF, также реализует несколько других методов и свойств, не связанных с XAML. Другие члены предназначены для того, чтобы <xref:System.Windows.Data.Binding> более гибким и автономным классом, который может решить многие сценарии привязки данных в дополнение к работе в качестве расширения разметки XAML.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.Binding>
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
