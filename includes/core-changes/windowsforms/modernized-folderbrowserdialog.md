---
ms.openlocfilehash: 24141f4b95cda2ae382a923da034e75c329b8555
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216909"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>Модернизация FolderBrowserDialog

В приложениях Windows Forms для .NET Core в элемент управления <xref:System.Windows.Forms.FolderBrowserDialog> внесены изменения.

#### <a name="change-description"></a>Описание изменений

В Windows Forms в .NET Framework для элемента управления <xref:System.Windows.Forms.FolderBrowserDialog> используется следующее диалоговое окно:

![FolderBrowserDialogControl в .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

В .NET Core 3.0 в Windows Forms используется более новый элемент управления на основе COM, появившийся в Windows Vista:

![FolderBrowserDialogControl в .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

Диалоговое окно будет обновлено автоматически.

Если вы хотите оставить исходное диалоговое окно, перед отображением диалогового окна задайте для свойства <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> значение `false`, как показано в следующем фрагменте кода:

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->
