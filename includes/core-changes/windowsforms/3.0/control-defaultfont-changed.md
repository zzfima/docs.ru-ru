---
ms.openlocfilehash: b0c4e9617677cf95e3a059b57f3d50ddfb072f4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936997"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a>Шрифт элемента управления по умолчанию изменен на Segoe UI 9 пт

#### <a name="change-description"></a>Описание изменений

В .NET Framework свойству <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> присвоено значение `Microsoft Sans Serif 8 pt`. На следующем рисунке показано окно, в котором используется шрифт по умолчанию.

![Шрифт по умолчанию для элемента управления в .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

Начиная с .NET Core 3.0 шрифтом по умолчанию является `Segoe UI 9 pt` (тот же шрифт, что и <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>). В результате этого изменения размер форм и элементов управления увеличен на 27 % с учетом увеличенного размера нового шрифта по умолчанию. Пример:

![Шрифт по умолчанию для элемента управления в .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Это изменение было внесено в соответствии с [рекомендациями по пользовательскому интерфейсу Windows](/windows/win32/uxguide/vis-fonts#fonts-and-colors).

#### <a name="version-introduced"></a>Представленная версия

3,0

#### <a name="recommended-action"></a>Рекомендованное действие

Так как размер форм и элементов управления изменился, убедитесь, что приложение отображается правильно.

Чтобы оставить исходный шрифт, задайте для формы шрифт по умолчанию: `Microsoft Sans Serif 8 pt`. Пример:

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

Нет.

<!--

### Affected APIs

- Not detectable via API analysis

-->
