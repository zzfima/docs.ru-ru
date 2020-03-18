---
ms.openlocfilehash: 01c0689bbfb102f8f4d9455f9d258e8ea5515d9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859358"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Неправильная реализация MemberDescriptor.Equals

|   |   |
|---|---|
|Подробнее|Исходная реализация метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> сравнивает два разных свойства строки из объектов для сравнения: имя категории и строка описания. Исправление заключается в сравнении <xref:System.ComponentModel.MemberDescriptor.Category> первого объекта с <xref:System.ComponentModel.MemberDescriptor.Category> второго объекта, и <xref:System.ComponentModel.MemberDescriptor.Description> первого объекта с <xref:System.ComponentModel.MemberDescriptor.Description> второго.|
|Предложение|Если приложение зависит от того, что <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> иногда возвращает значение <code>false</code>, когда дескрипторы эквивалентны, и вы используете .NET Framework 4.6.2 или более поздней версии, у вас есть несколько вариантов:<ol><li>Изменения в коде для сравнения полей <xref:System.ComponentModel.MemberDescriptor.Category> и <xref:System.ComponentModel.MemberDescriptor.Description> вручную в дополнение к вызову метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.</li><li>Откажитесь от этого изменения, добавив следующее значение в файл app.config:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Если ваше приложение предназначено для .NET Framework 4.6.1 или более ранней версии и выполняется на .NET Framework 4.6.2 или более поздней версии и вы хотите включить это изменение, вы можете указать для переключателя совместимости значение <code>false</code>, добавив следующее значение в файл app.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Version|4.6.2|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|
