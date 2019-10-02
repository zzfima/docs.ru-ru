---
ms.openlocfilehash: bb163d5a6eb3d926a44a83ea79572c3a497bbe8d
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181844"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Типы из пространства имен Microsoft.VisualBasic.Devices недоступны

Типы в пространстве имен <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> недоступны.

#### <a name="version-introduced"></a>Представленная версия

.NET Core 3.0 (предварительная версия 8)

#### <a name="details"></a>Сведения

Типы из пространства имен <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> были доступны в некоторых предварительных выпусках .NET Core 3.0. Начиная с предварительной версии 9 .NET Core 3.0, они больше не доступны.

Типы были удалены во избежание ненужных зависимостей сборок или критических изменений в последующих выпусках.
 
#### <a name="recommended-action"></a>Рекомендуемое действие

Если в вашем коде применяются типы <xref:Microsoft.VisualBasic.Devices> и их члены, вы можете использовать соответствующий тип или член из библиотеки классов .NET. Например, возможности, эквивалентные классу <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType>, предоставляются типами <xref:System.DateTime?displayProperty=nameWithType> и <xref:System.Environment?displayProperty=nameWithType>, а классу <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> — типами в пространстве имен <xref:System.IO.Ports?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

Visual Basic

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

