---
ms.openlocfilehash: 843007ac6467584fbe6350b6ea19ef67609d73e2
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643847"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a>Замена `Control.DefaultFont` на `Segoe UI 9pt`

#### <a name="change-description"></a>Описание изменений

В .NET Framework свойству <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> присвоено значение `Microsoft Sans Serif 8pt`. На следующем рисунке показано окно, в котором используется шрифт по умолчанию.

![Шрифт по умолчанию для элемента управления в .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

В .NET Core начиная с .NET Core 3.0 для него задано значение `Segoe UI 9pt` (тот же шрифт, что и для <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>). В результате этого изменения размер форм и элементов управления будет увеличен на 27 % с учетом увеличенного размера нового шрифта по умолчанию. Например:

![Шрифт по умолчанию для элемента управления в .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Это изменение было внесено в соответствии с [рекомендациями по пользовательскому интерфейсу Windows](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

Так как размер форм и элементов управления изменился, убедитесь, что приложение отображается правильно.

Чтобы оставить исходный шрифт, задайте для формы шрифт по умолчанию: `Microsoft Sans Serif 8pt`. Например:

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a>Категория

- Windows Forms

#### <a name="affected-apis"></a>Затронутые API

Отсутствует.

<!--

### Affected APIs

- Not detectable via API analysis

-->
