---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804877"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="07825-101">Свойство XmlSchemaException теперь правильно задает позиции строк</span><span class="sxs-lookup"><span data-stu-id="07825-101">XmlSchemaException now sets line positions properly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="07825-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="07825-102">Details</span></span>|<span data-ttu-id="07825-103">Если значение <xref:System.Xml.Linq.LoadOptions.SetLineInfo> передается методу Load и возникает ошибка проверки, свойства <xref:System.Xml.Schema.XmlSchemaException.LineNumber> и <xref:System.Xml.Schema.XmlSchemaException.LinePosition> теперь содержат сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="07825-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>|
|<span data-ttu-id="07825-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="07825-104">Suggestion</span></span>|<span data-ttu-id="07825-105">Код обработки исключений, который предполагает, что свойства <xref:System.Xml.Schema.XmlSchemaException.LineNumber> и <xref:System.Xml.Schema.XmlSchemaException.LinePosition> не будут задаваться, необходимо обновить, поскольку эти свойства теперь задаются правильно при использовании SetLineInfo во время загрузки XML.</span><span class="sxs-lookup"><span data-stu-id="07825-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>|
|<span data-ttu-id="07825-106">Область</span><span class="sxs-lookup"><span data-stu-id="07825-106">Scope</span></span>|<span data-ttu-id="07825-107">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="07825-107">Edge</span></span>|
|<span data-ttu-id="07825-108">Версия</span><span class="sxs-lookup"><span data-stu-id="07825-108">Version</span></span>|<span data-ttu-id="07825-109">4.5</span><span class="sxs-lookup"><span data-stu-id="07825-109">4.5</span></span>|
|<span data-ttu-id="07825-110">Тип</span><span class="sxs-lookup"><span data-stu-id="07825-110">Type</span></span>|<span data-ttu-id="07825-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="07825-111">Runtime</span></span>|
|<span data-ttu-id="07825-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="07825-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
