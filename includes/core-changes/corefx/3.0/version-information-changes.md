---
ms.openlocfilehash: 2a751acc129ebd1c917b87f8083ffef72c7d8c17
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568179"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a>Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла

Многие интерфейсы API, которые возвращают версию в .NET Core, теперь возвращают версию продукта, а не файла.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и предыдущих версиях такие методы, как <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> и диалоговое окно свойств файла для сборок .NET Core, сообщают версию файла. Начиная с версии .NET Core 3.0, они сообщают версию продукта.

На приведенном ниже рисунке показана разница в сведениях о версии для сборки *System.Runtime.dll* для .NET Core 2.2 (слева) и .NET Core 3.0 (справа), отображаемых в диалоговом окне свойств файла в **проводнике**.

![Разница в сведениях о версии](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

Отсутствует. Это изменение должно сделать определение версии интуитивно понятным.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
