---
ms.openlocfilehash: d207a937917da78f6b902ad8ca4f02fa9a46c2e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116352"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Типы из пространства имен Microsoft.VisualBasic.MyServices недоступны

Типы в пространстве имен <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> недоступны.

#### <a name="version-introduced"></a>Представленная версия

.NET Core 3.0 (предварительная версия 8)

#### <a name="change-description"></a>Описание изменений

Типы из пространства имен <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> были доступны в некоторых предварительных выпусках .NET Core 3.0. Начиная с предварительной версии 9 .NET Core 3.0, они больше не доступны.

Типы были удалены во избежание ненужных зависимостей сборок или критических изменений в последующих выпусках.

#### <a name="recommended-action"></a>Рекомендованное действие

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

-->
