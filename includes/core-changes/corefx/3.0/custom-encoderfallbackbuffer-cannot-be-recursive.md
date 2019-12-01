---
ms.openlocfilehash: 58d1c8cd3aff52703522391c14348bd81c108587
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568139"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a>Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат

Пользовательские экземпляры <xref:System.Text.EncoderFallbackBuffer> не поддерживают рекурсивный откат. В результате реализации <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> должна быть создана последовательность символов, которая преобразуется в целевую кодировку. В противном случае возникает исключение.

#### <a name="change-description"></a>Описание изменений

При перекодировании символов в байты среда выполнения обнаруживает некорректные или непреобразуемые последовательности UTF-16 и передает эти символы методу <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>. Метод `Fallback` определяет, какие символы следует заменить в исходных непреобразуемых данных, и эти символы удаляются путем вызова <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> в цикле.

Затем среда выполнения пытается перекодировать эти символы подстановки в целевую кодировку. Если это удалось выполнить, среда выполнения продолжит перекодировку с того места, где она остановилась на исходной входной строке.

В предварительной версии .NET Core 7 и более ранних версиях пользовательские реализации <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> могут возвращать последовательности символов, которые нельзя преобразовать в целевую кодировку. Если подставляемые символы не поддерживают такое преобразование, среда выполнения снова вызовет метод <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> с символами подстановки, ожидая, что метод <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> вернет новую последовательность символов подстановки. Этот процесс продолжится до тех пор, пока среда выполнения не увидит правильно сформированную и преобразуемую последовательность символов подстановки или пока не будет достигнуто максимальное число рекурсий.

Начиная с версии .NET Core 3.0, пользовательские реализации <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> должны возвращать последовательности символов, преобразуемые в целевую кодировку. Если подставляемые символы нельзя перекодировать в целевую кодировку, создается исключение <xref:System.ArgumentException>. Среда выполнения больше не будет выполнять рекурсивные вызовы к экземпляру <xref:System.Text.EncoderFallbackBuffer>.

Такой подход применяется только в том случае, если выполнены все следующие три условия:

- Среда выполнения обнаруживает последовательность UTF-16, которая была неправильно сформирована или не подлежит преобразованию в целевую кодировку.
- Указана пользовательская реализация <xref:System.Text.EncoderFallback>.
- Пользовательская реализация <xref:System.Text.EncoderFallback> пытается заменить новую неправильно сформированную или непреобразуемую последовательность UTF-16.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

В большинстве случаев от разработчиков не требуется никаких действий.

Если приложение использует пользовательский класс <xref:System.Text.EncoderFallback> и <xref:System.Text.EncoderFallbackBuffer>, убедитесь, что реализация <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> заполняет буфер отката правильно сформированными данными UTF-16, которые можно сразу же преобразовать в целевую кодировку, когда среда выполнения впервые вызывает метод <xref:System.Text.EncoderFallbackBuffer.Fallback%2A>.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
