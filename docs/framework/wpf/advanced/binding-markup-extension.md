---
title: Привязка расширения разметки
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: 616e405e191cb264a002e903bed60cf04559a675
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964899"
---
# <a name="binding-markup-extension"></a>Привязка расширения разметки
Откладывает значение свойства на значение, привязанное к данным, создавая объект промежуточного выражения и обрабатывая контекст данных, который применяется к элементу и его привязке во время выполнения.  
  
## <a name="binding-expression-usage"></a>Использование выражений привязки  
  
```  
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
 В этих синтаксисах `[]` и `*` не являются литералами. Они являются частью нотации для указания того, что `,` можно использовать ноль или более пар *биндпроп*`=`*значений* с разделителем между ними и предшествующими парами *биндпроп*`=`*значений* .  
  
 Все свойства, перечисленные в разделе "Свойства привязки, которые могут быть заданы с помощью расширения привязки", вместо этого можно задать с помощью атрибутов <xref:System.Windows.Data.Binding> элемента Object. Тем не менее, это не все, что является расширением <xref:System.Windows.Data.Binding>разметки, это просто общая обработка XAML атрибутов, устанавливающих свойства класса CLR <xref:System.Windows.Data.Binding> . Иными словами `<Binding` , *bindProp1*`="`*value1* <xref:System.Windows.Data.Binding> биндпропн контрольное — это эквивалентный синтаксис для атрибутов использования объектных элементов.`"]*/>` `="``"[` Вместо использования выражения `Binding` . Дополнительные сведения об использовании атрибутов XAML для конкретных свойств <xref:System.Windows.Data.Binding>см. в разделе "использование атрибутов XAML" соответствующего <xref:System.Windows.Data.Binding> свойства в библиотеке классов .NET Framework.  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Имя <xref:System.Windows.Data.Binding> свойства или <xref:System.Windows.Data.BindingBase> , которое необходимо задать. Не все <xref:System.Windows.Data.Binding> свойства можно задать `Binding` с помощью расширения, а некоторые `Binding` свойства могут быть заданы в выражении только с помощью вложенных расширений разметки. См. раздел "Свойства привязки, которые могут быть установлены с помощью расширения привязки".|  
|`value1, valueN`|Значение, которое нужно присвоить свойству. Обработка значения атрибута в конечном итоге зависит от типа и логики <xref:System.Windows.Data.Binding> устанавливаемого свойства.|  
|`path`|Строка пути, которая задает неявное <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> свойство. См. также [синтаксис PropertyPath языка XAML](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Неквалифицированная {Binding}  
 Использование, показанное в "использовании выражений привязки", <xref:System.Windows.Data.Binding> создает объект со значениями по умолчанию, `null`которые <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> включают в себя начальное значение. `{Binding}` Это все еще полезно во многих сценариях, так как <xref:System.Windows.Data.Binding> создаваемые данные могут полагаться на ключевые свойства привязки <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> данных <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> , такие как и, которые задаются в контексте данных времени выполнения. Дополнительные сведения о концепции контекста данных см. в разделе [Привязка данных](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Неявный путь  
 Расширение разметки использует <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> как концептуальное свойство по умолчанию, где `Path=` не требуется указывать в выражении. `Binding` `Binding` При указании выражения с неявным путем неявный путь должен располагаться первым в выражении до любых других `bindProp` = `value` пар, где <xref:System.Windows.Data.Binding> свойство задается по имени. Например: `{Binding PathString}`, где `PathString` — это строка, которая вычисляется как значение <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> в элементе, <xref:System.Windows.Data.Binding> созданном с использованием расширения разметки. Можно добавить неявный путь с другими именованными свойствами после разделителя запятой, `{Binding LastName, Mode=TwoWay}`например.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Свойства привязки, которые можно задать с помощью расширения привязки  
 Синтаксис, приведенный в этом разделе, использует `bindProp` обобщенное <xref:System.Windows.Data.Binding> = `value` приближение, так как существует множество свойств чтения и <xref:System.Windows.Data.BindingBase> записи `Binding` для или, которые можно задать с помощью расширения разметки/ Синтаксис выражения. Они могут быть заданы в любом порядке, за исключением неявного <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (У вас есть возможность явно указать `Path=`, в этом случае ее можно задать в любом порядке). По сути, можно задать ноль или более свойств в приведенном ниже списке, используя `bindProp` = `value` пары, разделенные запятыми.  
  
 Для некоторых из этих значений свойств требуются типы объектов, которые не поддерживают преобразование машинного типа из текстового синтаксиса в XAML и поэтому нуждаются в расширениях разметки для установки в качестве значения атрибута. Дополнительные сведения см. в разделе Использование атрибутов XAML в библиотеке классов .NET Framework для каждого свойства. Строка, используемая для синтаксиса атрибута XAML с дальнейшим использованием расширения разметки, в основном совпадает со значением, указанным в `Binding` выражении, за исключением того, что кавычки вокруг них `bindProp` =незаключены.ввыражении. `value` `Binding`  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: строка, определяющая возможную группу привязки. Это относительно сложная концепция привязки. см. страницу справочника по <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: может быть `bindProp` задан как = `value` строка в выражении, но для этого требуется ссылка на объект для значения, например расширение разметки [StaticResource](staticresource-markup-extension.md). Значение в этом случае является экземпляром пользовательского класса преобразователя.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: задается в выражении как идентификатор на основе стандартов; см. справочный раздел <xref:System.Windows.Data.Binding.ConverterCulture%2A>по.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: может быть задан как `bindProp` = `value` строка в выражении, но это зависит от типа передаваемого параметра. При передаче ссылочного типа для значения для этого использования требуется ссылка на объект, например вложенное [расширение разметки StaticResource](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: взаимоисключающее <xref:System.Windows.Data.Binding.RelativeSource%2A> и и <xref:System.Windows.Data.Binding.Source%2A>; каждое из этих свойств привязки представляет конкретную методологию привязки. См. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: может быть задан как `bindProp` = `value` строка в выражении, но это зависит от типа передаваемого значения. При передаче ссылочного типа требуется ссылка на объект, например вложенное [расширение разметки StaticResource](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *value* — это имя константы из <xref:System.Windows.Data.BindingMode> перечисления. Например, `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: строка, описывающая путь к объекту данных или общей объектной модели. Формат предоставляет несколько различных соглашений для обхода объектной модели, которые не могут быть надлежащим образом описаны в этом разделе. См. раздел [синтаксис языка XAML PropertyPath](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: взаимоисключающее и с <xref:System.Windows.Data.Binding.ElementName%2A> и <xref:System.Windows.Data.Binding.Source%2A>; каждое из этих свойств привязки представляет конкретную методологию привязки. См. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md). Для указания значения требуется вложенное использование [RelativeSource MarkupExtension](relativesource-markupextension.md) .  
  
- <xref:System.Windows.Data.Binding.Source%2A>: взаимоисключающее <xref:System.Windows.Data.Binding.RelativeSource%2A> и и <xref:System.Windows.Data.Binding.ElementName%2A>; каждое из этих свойств привязки представляет конкретную методологию привязки. См. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md). Требует вложенного расширения, обычно это [расширение разметки StaticResource](staticresource-markup-extension.md) , которое ссылается на источник данных объекта из словаря ресурсов с ключом.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: строка, описывающая соглашение о формате строки для привязанных данных. Это относительно сложная концепция привязки. см. страницу справочника по <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: может быть задан как `bindProp` = `value` строка в выражении, но это зависит от типа передаваемого параметра. При передаче ссылочного типа для значения требуется ссылка на объект, например вложенное [расширение разметки StaticResource](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *value* — это имя константы из <xref:System.Windows.Data.UpdateSourceTrigger> перечисления. Например, `{Binding UpdateSourceTrigger=LostFocus}`. Определенные элементы управления потенциально имеют разные значения по умолчанию для этого свойства привязки. См. раздел <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`. См. заметки.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`. См. заметки.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: строка, описывающая путь к XMLDOM источника XML-данных. См. статью [Привязка к XML-данным с помощью XmlDataProvider и запросов XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Ниже перечислены свойства <xref:System.Windows.Data.Binding> , которые нельзя задать `Binding` с помощью формы расширения разметки или`{Binding}` выражения.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: это свойство принимает ссылку на реализацию обратного вызова. В синтаксисе XAML нельзя ссылаться на обратные вызовы и методы, отличные от обработчиков событий.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: свойство принимает универсальную коллекцию <xref:System.Windows.Controls.ValidationRule> объектов. Это может быть выражено как элемент свойства в <xref:System.Windows.Data.Binding> элементе Object, но `Binding` в нем нет легко доступной методики синтаксического анализа атрибутов для использования в выражении. См. раздел Справочник <xref:System.Windows.Data.Binding.ValidationRules%2A>по.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
> В плане приоритета `Binding` свойства зависимости выражение эквивалентно локальному заданному значению. Если задать локальное значение для свойства, которое ранее имело `Binding` выражение, то `Binding` оно будет полностью удалено. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](dependency-property-value-precedence.md).  
  
 Описание привязки данных на базовом уровне не рассматривается в этом разделе. См. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>и <xref:System.Windows.Data.PriorityBinding> не[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] поддерживают синтаксис расширения. Вместо этого следует использовать элементы свойств. См. разделы справки <xref:System.Windows.Data.MultiBinding> по <xref:System.Windows.Data.PriorityBinding>и.  
  
 Логические значения для XAML не учитывают регистр. Например, можно указать либо `{Binding NotifyOnValidationError=true}`. `{Binding NotifyOnValidationError=True}`  
  
 Привязки, которые подразумевают проверку данных, обычно задаются `Binding` явным элементом, а `{Binding ...}` не выражением, а <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> установка <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> или в выражении является редким. Это обусловлено тем, что <xref:System.Windows.Data.Binding.ValidationRules%2A> сопутствующее свойство не может быть задано в форме выражения. Дополнительные сведения см. в разделе [Реализация проверки привязки](../data/how-to-implement-binding-validation.md).  
  
 `Binding` является расширением разметки. Расширения разметки обычно реализуются, если требуется, чтобы значения атрибутов были другими, чем литеральные значения или имена обработчиков, а требование является более глобальным, чем преобразователи типов, имеющие атрибуты для определенных типов или свойств. Все расширения разметки в XAML используют `{` символы `}` и в синтаксисе атрибутов, что является соглашением, по которому обработчик XAML распознает, что расширение разметки должно обработать содержимое строки. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding`является нетипичным расширением разметки в <xref:System.Windows.Data.Binding> том, что класс, реализующий функциональность расширения для реализации XAML в WPF, также реализует несколько других методов и свойств, которые не связаны с XAML. Другие члены предназначены для создания <xref:System.Windows.Data.Binding> более гибкого и автономного класса, который может решать многие сценарии привязки данных в дополнение к работе в качестве расширения разметки XAML.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.Binding>
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Общие сведения о языке XAML (WPF)](xaml-overview-wpf.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
