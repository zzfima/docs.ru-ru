---
ms.openlocfilehash: a7cf6210e288d3521f1df248927f0e7cfaf45cab
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119122"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="cbbed-101">Модернизация FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="cbbed-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="cbbed-102">В приложениях Windows Forms для .NET Core в элемент управления <xref:System.Windows.Forms.FolderBrowserDialog> внесены изменения.</span><span class="sxs-lookup"><span data-stu-id="cbbed-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cbbed-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="cbbed-103">Change description</span></span>

<span data-ttu-id="cbbed-104">В Windows Forms в .NET Framework для элемента управления <xref:System.Windows.Forms.FolderBrowserDialog> используется следующее диалоговое окно:</span><span class="sxs-lookup"><span data-stu-id="cbbed-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![FolderBrowserDialogControl в .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="cbbed-106">В .NET Core 3.0 в Windows Forms используется более новый элемент управления на основе COM, появившийся в Windows Vista:</span><span class="sxs-lookup"><span data-stu-id="cbbed-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![FolderBrowserDialogControl в .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="cbbed-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cbbed-108">Version introduced</span></span>

<span data-ttu-id="cbbed-109">3.0</span><span class="sxs-lookup"><span data-stu-id="cbbed-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cbbed-110">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="cbbed-110">Recommended action</span></span>

<span data-ttu-id="cbbed-111">Диалоговое окно будет обновлено автоматически.</span><span class="sxs-lookup"><span data-stu-id="cbbed-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="cbbed-112">Если вы хотите оставить исходное диалоговое окно, перед отображением диалогового окна задайте для свойства <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> значение `false`, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="cbbed-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="cbbed-113">Категория</span><span class="sxs-lookup"><span data-stu-id="cbbed-113">Category</span></span>

<span data-ttu-id="cbbed-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbbed-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cbbed-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="cbbed-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!-- 

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->