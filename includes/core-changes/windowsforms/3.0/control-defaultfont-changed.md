---
ms.openlocfilehash: 843007ac6467584fbe6350b6ea19ef67609d73e2
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643847"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a><span data-ttu-id="b567e-101">Замена `Control.DefaultFont` на `Segoe UI 9pt`</span><span class="sxs-lookup"><span data-stu-id="b567e-101">`Control.DefaultFont` changed to `Segoe UI 9pt`</span></span>

#### <a name="change-description"></a><span data-ttu-id="b567e-102">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="b567e-102">Change description</span></span>

<span data-ttu-id="b567e-103">В .NET Framework свойству <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> присвоено значение `Microsoft Sans Serif 8pt`.</span><span class="sxs-lookup"><span data-stu-id="b567e-103">In the .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="b567e-104">На следующем рисунке показано окно, в котором используется шрифт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b567e-104">The following figure shows a window that uses the default font.</span></span>

![Шрифт по умолчанию для элемента управления в .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="b567e-106">В .NET Core начиная с .NET Core 3.0 для него задано значение `Segoe UI 9pt` (тот же шрифт, что и для <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="b567e-106">In .NET Core starting with .NET Core 3.0, it is set to `Segoe UI 9pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="b567e-107">В результате этого изменения размер форм и элементов управления будет увеличен на 27 % с учетом увеличенного размера нового шрифта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b567e-107">As a result of this change, forms and controls will be sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="b567e-108">Например:</span><span class="sxs-lookup"><span data-stu-id="b567e-108">For example:</span></span>

![Шрифт по умолчанию для элемента управления в .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="b567e-110">Это изменение было внесено в соответствии с [рекомендациями по пользовательскому интерфейсу Windows](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span><span class="sxs-lookup"><span data-stu-id="b567e-110">This change was made to align with [Windows UX guidelines](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b567e-111">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b567e-111">Version introduced</span></span>

<span data-ttu-id="b567e-112">3.0</span><span class="sxs-lookup"><span data-stu-id="b567e-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b567e-113">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="b567e-113">Recommended action</span></span>

<span data-ttu-id="b567e-114">Так как размер форм и элементов управления изменился, убедитесь, что приложение отображается правильно.</span><span class="sxs-lookup"><span data-stu-id="b567e-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="b567e-115">Чтобы оставить исходный шрифт, задайте для формы шрифт по умолчанию: `Microsoft Sans Serif 8pt`.</span><span class="sxs-lookup"><span data-stu-id="b567e-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="b567e-116">Например:</span><span class="sxs-lookup"><span data-stu-id="b567e-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="b567e-117">Категория</span><span class="sxs-lookup"><span data-stu-id="b567e-117">Category</span></span>

- <span data-ttu-id="b567e-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b567e-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b567e-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b567e-119">Affected APIs</span></span>

<span data-ttu-id="b567e-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b567e-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
