---
ms.openlocfilehash: 2413e1997b6e729b9d5889677e25254aaa24afea
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859358"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Неправильная реализация MemberDescriptor.Equals

|   |   |
|---|---|
|Подробные сведения|Исходная реализация метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> сравнивает два разных свойства строки из объектов для сравнения: имя категории и строка описания. Исправление заключается в сравнении <xref:System.ComponentModel.MemberDescriptor.Category> первого объекта с <xref:System.ComponentModel.MemberDescriptor.Category> второго объекта, и <xref:System.ComponentModel.MemberDescriptor.Description> первого объекта с <xref:System.ComponentModel.MemberDescriptor.Description> второго.|
|Предложение|Если приложение зависит от того, что <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> иногда возвращает значение <code>false</code>, когда дескрипторы эквивалентны, и вы используете .NET Framework 4.6.2 или более поздней версии, у вас есть несколько вариантов:<ol><li>Изменения в коде для сравнения полей <xref:System.ComponentModel.MemberDescriptor.Category> и <xref:System.ComponentModel.MemberDescriptor.Description> вручную в дополнение к вызову метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.</li><li>Откажитесь от этого изменения, добавив следующее значение в файл app.config:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Если ваше приложение предназначено для .NET Framework 4.6.1 или более ранней версии и выполняется на .NET Framework 4.6.2 или более поздней версии и вы хотите включить это изменение, вы можете указать для переключателя совместимости значение <code>false</code>, добавив следующее значение в файл app.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|

