---
ms.openlocfilehash: 7c0930f6606aa96d2863dc740aef8e9cab724b37
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344881"
---
### <a name="change-in-default-value-of-useshellexecute"></a>Изменение значения по умолчанию для UseShellExecute

<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> имеет значение `false` по умолчанию в .NET Core. В .NET Framework его значение по умолчанию — `true`.

#### <a name="change-description"></a>Описание изменений

<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> позволяет запускать приложение напрямую, например с помощью кода, как `Process.Start("mspaint.exe")`, запускающего Paint. Это также позволяет косвенно запускать связанное приложение, если для <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> установлено значение `true`. В .NET Framework значением по умолчанию для <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> является `true`, что означает, что такой код как `Process.Start("mytextfile.txt")` будет запускать Блокнот, если вы связали файлы *.txt* с этим редактором. Чтобы предотвратить косвенный запуск приложения на .NET Framework, необходимо явно установить `false` на <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>. В .NET Core значением по умолчанию для <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> является значение `false`. Это означает, что связанные по умолчанию приложения не запускаются при вызове `Process.Start`.

Это изменение введено в .NET Core для повышения производительности. Как правило, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> используется для непосредственного запуска приложения. Запуск приложения напрямую не требует затрагивания оболочки Windows и влечет за собой соответствующие расходы на производительность. Чтобы ускорить этот вариант по умолчанию, .NET Core изменяет значение по умолчанию <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> на `false`. При необходимости вы можете выбрать более медленный путь.

#### <a name="version-introduced"></a>Представленная версия

2.1

> [!NOTE]
> В более ранних версиях .NET Core `UseShellExecute` не был внедрен для Windows.

#### <a name="recommended-action"></a>Рекомендованное действие

Если приложение полагается на прежнее поведение, вызовите <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType>, указав для параметра <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> значение `true` в объекте <xref:System.Diagnostics.ProcessStartInfo>.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
