---
ms.openlocfilehash: dc733ee32184db5af59bb06e294cd73765977581
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449569"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a>FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации

Начиная с .NET Core версии 3.0, при попытке задать значение в статическом поле <xref:System.Reflection.FieldAttributes.InitOnly> путем вызова <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>, возникает исключение.

#### <a name="change-description"></a>Описание изменений

В .NET Framework и версиях .NET Core до 3.0 можно было задать значение статического поля, которое являлось константой после его инициализации ([только для чтения в C#](~/docs/csharp/language-reference/keywords/readonly.md)) путем вызова <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>. Однако установка такого поля таким образом приведет к непредсказуемому поведению в зависимости от целевой платформы и параметров оптимизации.

В .NET Core 3.0 и более поздних версиях, при вызове <xref:System.Reflection.FieldInfo.SetValue%2A> для статического поля <xref:System.Reflection.FieldAttributes.InitOnly> создается исключение <xref:System.FieldAccessException?displayProperty=nameWithType>.

> [!TIP]
> Поле <xref:System.Reflection.FieldAttributes.InitOnly> — это поле, которое можно задать только во время объявления или в конструкторе содержащего класса. Иными словами, оно остается константой после инициализации.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Инициализируйте статические поля <xref:System.Reflection.FieldAttributes.InitOnly> в статическом конструкторе. Это относится как к динамическим, так и к не динамическим типам.

Кроме того, можно удалить атрибут <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> из поля, а затем вызвать <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
