---
ms.openlocfilehash: 58e65bae1593f23945a971b896a1db4a929b4587
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567425"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Типы из пространства имен Microsoft.VisualBasic.MyServices недоступны

Типы в пространстве имен <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> недоступны.

#### <a name="version-introduced"></a>Представленная версия

.NET Core 3.0 (предварительная версия 8)

#### <a name="change-description"></a>Описание изменений

Типы из пространства имен <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> были доступны в некоторых предварительных выпусках .NET Core 3.0. Начиная с предварительной версии 9 .NET Core 3.0, они больше не доступны.

Типы были удалены во избежание ненужных зависимостей сборок или критических изменений в последующих выпусках.

#### <a name="recommended-action"></a>Рекомендуемое действие

Если в вашем коде применяются типы **Microsoft.VisualBasic.MyServices** и их члены, вы можете использовать соответствующие типы и члены из библиотеки классов .NET. Ниже представлено сопоставление типов **Microsoft.VisualBasic.MyServices** и эквивалентных типов в библиотеке классов .NET.

|Тип Microsoft.VisualBasic.MyServices|Тип в библиотеке классов .NET|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<xref:System.Windows.Clipboard?displayProperty=nameWithType> для приложений WPF, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> для приложений Windows Forms|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|Типы в пространстве имен <xref:System.IO>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|Связанные с реестром типы в пространстве имен <xref:Microsoft.Win32>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a>Категория

Visual Basic

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

