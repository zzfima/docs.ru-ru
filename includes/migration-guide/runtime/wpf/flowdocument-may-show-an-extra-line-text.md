---
ms.openlocfilehash: 6c1740df66ead271afa5f97dc125587810946bc6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379675"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="bfd5d-101">FlowDocument может отображать дополнительную строку текста</span><span class="sxs-lookup"><span data-stu-id="bfd5d-101">FlowDocument may show an extra line of text</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bfd5d-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="bfd5d-102">Details</span></span>|<span data-ttu-id="bfd5d-103">В некоторых случаях при работе с .NET Framework 4.5 в элементе <xref:System.Windows.Documents.FlowDocument> отображается лишняя строка текста по сравнению с выполнением в .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="bfd5d-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="bfd5d-104">Случаи неправильного или неразборчивого отображения текста в связи с этим изменением не выявлены, однако эта проблема может привести к отображению текста, который ранее был опущен из представления <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="bfd5d-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>|
|<span data-ttu-id="bfd5d-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="bfd5d-105">Suggestion</span></span>|<span data-ttu-id="bfd5d-106">В некоторых случаях для восстановления исходного количества строк можно уменьшить значение свойства PageHeight на единицу.</span><span class="sxs-lookup"><span data-stu-id="bfd5d-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>|
|<span data-ttu-id="bfd5d-107">Область</span><span class="sxs-lookup"><span data-stu-id="bfd5d-107">Scope</span></span>|<span data-ttu-id="bfd5d-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="bfd5d-108">Edge</span></span>|
|<span data-ttu-id="bfd5d-109">Версия</span><span class="sxs-lookup"><span data-stu-id="bfd5d-109">Version</span></span>|<span data-ttu-id="bfd5d-110">4.5</span><span class="sxs-lookup"><span data-stu-id="bfd5d-110">4.5</span></span>|
|<span data-ttu-id="bfd5d-111">Тип</span><span class="sxs-lookup"><span data-stu-id="bfd5d-111">Type</span></span>|<span data-ttu-id="bfd5d-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="bfd5d-112">Runtime</span></span>|
|<span data-ttu-id="bfd5d-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="bfd5d-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Documents.FlowDocument.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor?displayProperty=nameWithType></li></ul>|
