---
ms.openlocfilehash: 335647f899c79eff22e313fa40b2e2a73e7cfff0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804870"
---
### <a name="wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>Теперь WF сериализует Expressions.Literal\<T> DateTimes по-другому (нарушает работу пользовательских средств синтаксического анализа XAML)

|   |   |
|---|---|
|Подробные сведения|Связанный объект <xref:System.Windows.Markup.ValueSerializer> преобразует объект <xref:System.DateTime?displayProperty=name> или <xref:System.DateTimeOffset?displayProperty=name>, компоненты Second и <xref:System.DateTime.Millisecond?displayProperty=name> которого не равны нулю и (для значения <xref:System.DateTime?displayProperty=name>) свойство <xref:System.DateTime.Kind> которого не равно Unspecified, в синтаксис элемента свойства вместо строки. Это изменение позволяет передавать значения <xref:System.DateTime?displayProperty=name> и <xref:System.DateTimeOffset?displayProperty=name> в оба конца. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.|
|Предложение|Это изменение позволяет передавать значения <xref:System.DateTime?displayProperty=name> и <xref:System.DateTimeOffset?displayProperty=name> в оба конца. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
