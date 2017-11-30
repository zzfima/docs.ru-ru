---
title: "Привязка расширения разметки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d2bbca799e1eda1abae3d199dd71e004b17c4c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="binding-markup-extension"></a>Привязка расширения разметки
Определяет значение свойства на значение с привязкой к данным, создавая объект промежуточного выражения и интерпретируя контекст данных, который применяется к элементу и его привязке во время выполнения.  
  
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
  
## <a name="syntax-notes"></a>Заметки о синтаксисе  
 В этих синтаксисов `[]` и `*` не являются литералами. Они являются частью нотации, чтобы указать, что ноль или более *платформы*`=`*значение* можно использовать, с `,` разделитель между ними и предыдущими *платформы*  `=` *значение* пары.  
  
 Любые свойства, перечисленные в разделе «Привязки свойства, можно будет задать с расширением Binding» удалось вместо этого задать с помощью атрибутов <xref:System.Windows.Data.Binding> элемента объекта. Однако это не действительно использование расширения разметки из <xref:System.Windows.Data.Binding>, это просто общие обработки XAML атрибутов, задайте свойства среды CLR <xref:System.Windows.Data.Binding> класса. Другими словами `<Binding` *Свойство_привязки_1*`="`*значение1* `"[` *bindPropN*`="`*valueN* `"]*/>` — это эквивалентный синтаксис атрибутов <xref:System.Windows.Data.Binding> использование элемента вместо объекта `Binding` использование выражений. Дополнительные сведения о конкретных свойств использование атрибута XAML <xref:System.Windows.Data.Binding>, см. в разделе «Использование атрибута XAML», соответствующие свойства <xref:System.Windows.Data.Binding> в библиотеке классов .NET Framework.  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Имя <xref:System.Windows.Data.Binding> или <xref:System.Windows.Data.BindingBase> задаваемого свойства. Не все <xref:System.Windows.Data.Binding> свойства могут быть заданы с `Binding` расширения и некоторые свойства могут задаваться в `Binding` выражении только с помощью дополнительные вложенные расширения разметки. См. раздел «Привязки свойства, можно будет задать с расширением Binding».|  
|`value1, valueN`|Свойству присвоено значение. В конечном счете обработки значения атрибута относится к типу и логику конкретной <xref:System.Windows.Data.Binding> устанавливаемое свойство.|  
|`path`|Строка пути, которое задает неявный <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> свойство. См. также [синтаксис PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Неполное {Binding}  
 `{Binding}` Использовании в «Использование привязки выражение» создает <xref:System.Windows.Data.Binding> объекта со значениями по умолчанию, которая содержит первоначальную <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> из `null`. Это по-прежнему полезно во многих сценариях, поскольку созданный <xref:System.Windows.Data.Binding> например полагаться на свойства привязки данных ключа <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> и <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> устанавливается в контексте данных во время выполнения. Дополнительные сведения о концепции контекста данных см. в разделе [привязки данных](../../../../docs/framework/wpf/data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Неявный путь  
 `Binding` Использует расширение разметки <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> как концептуальной «свойство по умолчанию», где `Path=` не требуется в выражении. При указании `Binding` выражение с неявный путь неявный путь должно быть первым в выражении, перед любой другой `bindProp` = `value` пары where <xref:System.Windows.Data.Binding> свойство указывается по имени. Например: `{Binding PathString}`, где `PathString` представляет собой строку, которое вычисляется в качестве значения для <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> в <xref:System.Windows.Data.Binding> созданные использование расширения разметки. Можно добавить неявный путь с другими именованными свойствами после запятой-разделителя, например, `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Свойства привязки, которые могут быть установлены с расширением Binding  
 Синтаксис, показанный в этом разделе использует универсальный `bindProp` = `value` приближения, так как многие свойства чтения и записи <xref:System.Windows.Data.BindingBase> или <xref:System.Windows.Data.Binding> , можно задать с помощью `Binding` расширения разметки или синтаксис выражения. Их можно задать в любом порядке, за исключением неявный <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (Имеется возможность явно задать `Path=`, в этом случае могут задаваться в любом порядке). По сути, можно задать ноль или несколько свойств в списке ниже, используя `bindProp` = `value` пары, разделенных запятыми.  
  
 Некоторые из этих значений свойств требуют типы объектов, которые не поддерживают собственное преобразование типов из текстового синтаксиса в XAML и следовательно, чтобы задать в качестве значения атрибута требуют расширения разметки. Проверьте в разделе в библиотеке классов .NET Framework для каждого свойства подробнее; использование атрибута XAML Строка используется для синтаксиса атрибутов XAML с или без дальнейшего расширения разметки используется в основном таким же, как значение, указываемое в `Binding` выражения, за исключением не размещайте кавычки вокруг каждого `bindProp` = `value` в `Binding` выражение.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: строка, определяющая группу возможных привязки. Это — это понятие относительно Расширенная привязка; в разделе справочника, посвященных <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: можно задать в качестве `bindProp` = `value` строки в выражении, но для этого требуется ссылка на объект для значения, такие как [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). Значение в этом случае является экземпляром класса настраиваемого преобразователя.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: можно задать в выражение в качестве идентификатора, основанную на стандартах; в разделе справки для <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: можно задать в качестве `bindProp` = `value` строки в выражение, но это зависит от типа параметра, переданного. Если передача ссылочного типа значение, такое использование требуется ссылка на объект, например вложенный [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: взаимно исключают друг друга и <xref:System.Windows.Data.Binding.RelativeSource%2A> и <xref:System.Windows.Data.Binding.Source%2A>; каждый из этих свойств привязки представляет определенную методологию привязки. В разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: можно задать в качестве `bindProp` = `value` строки в выражение, но это зависит от типа передаваемого значения. Если передача ссылочного типа, требуется ссылка на объект, например вложенный [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *значение* является именем константы из <xref:System.Windows.Data.BindingMode> перечисления. Например, `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: строка, описывающая пути в объект данных или общие объектной модели. Формат предоставляет несколько разных соглашений для обхода объектной модели, которая не может быть адекватно описан в данном разделе. В разделе [синтаксис PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: взаимно исключают друг друга и с <xref:System.Windows.Data.Binding.ElementName%2A> и <xref:System.Windows.Data.Binding.Source%2A>; каждый из этих свойств привязки представляет определенную методологию привязки. В разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md). Требуется вложенный [RelativeSource MarkupExtension](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) использования для указания значения.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: взаимно исключают друг друга и <xref:System.Windows.Data.Binding.RelativeSource%2A> и <xref:System.Windows.Data.Binding.ElementName%2A>; каждый из этих свойств привязки представляет определенную методологию привязки. В разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md). Обычно требует использование вложенного расширения, [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) , ссылается на источник данных объекта из словаря ресурсов с ключом.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: строка, описывающая соглашение строковое формат для связанных данных. Это — это понятие относительно Расширенная привязка; в разделе справочника, посвященных <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: можно задать в качестве `bindProp` = `value` строки в выражение, но это зависит от типа параметра, переданного. Если передача ссылочного типа в качестве значения требуется ссылка на объект, например вложенный [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *значение* является именем константы из <xref:System.Windows.Data.UpdateSourceTrigger> перечисления. Например, `{Binding UpdateSourceTrigger=LostFocus}`. Потенциально определенные элементы управления имеют разные значения по умолчанию для этого свойства привязки. См. раздел <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`. См. заметки.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Логическое значение может быть либо `true` или `false`. Значение по умолчанию — `false`. См. заметки.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: строка, описывающая путь в XMLDOM источника данных XML. В разделе [привязать к XML-данных с помощью XMLDataProvider и запросы XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Ниже приведены свойства <xref:System.Windows.Data.Binding> , нельзя задать с помощью `Binding` расширения разметки или`{Binding}` форма выражения.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: это свойство ожидает ссылку на реализацию обратного вызова. Обратные вызовы и методы, отличные от обработчиков событий нельзя ссылаться в синтаксисе XAML.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: свойство принимает универсальную коллекцию <xref:System.Windows.Controls.ValidationRule> объектов. Это можно выразить как элемент свойства в <xref:System.Windows.Data.Binding> объекта элемента, но имеет не доступны метод разбора атрибута для использования в `Binding` выражение. В разделе справки для <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  С точки зрения приоритета свойств зависимостей `Binding` выражение эквивалентно локально заданное значение. Если вы установите локальное значение для свойства, которое ранее было `Binding` выражение, `Binding` полностью удаляется. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Описание привязки данных на базовом уровне не рассматривается в этом разделе. В разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding>и <xref:System.Windows.Data.PriorityBinding> не поддерживают [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксиса расширения. Вместо этого следует использовать элементы свойств. В разделах справочника для <xref:System.Windows.Data.MultiBinding> и <xref:System.Windows.Data.PriorityBinding>.  
  
 Логические значения для XAML учитывается регистр. Например можно указать либо `{Binding NotifyOnValidationError=true}` или `{Binding NotifyOnValidationError=True}`.  
  
 Привязки, включающие проверку данных обычно определяются явно `Binding` элемент, а не как `{Binding ...}` выражение, а параметр <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> или <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> в выражении является редко. Это обусловлено дополнительное свойство <xref:System.Windows.Data.Binding.ValidationRules%2A> невозможно легко задать в виде выражения. Дополнительные сведения см. в разделе [проверки привязки, реализующие](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md).  
  
 `Binding` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или обработчик имена и если требуется больше, чем установка атрибутов на определенными типами или свойствами преобразователей типов. Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать содержимое строки. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 `Binding`является необычным расширением разметки в том, что <xref:System.Windows.Data.Binding> класс, реализующий функциональные возможности расширения для реализации XAML в WPF также реализует несколько методов и свойств, которые не связаны с XAML. Другие члены предназначены для сделать <xref:System.Windows.Data.Binding> более гибким, автономная класс, который можно решить многие сценарии привязки данных в дополнение к его как расширение разметки XAML.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.Binding>  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
