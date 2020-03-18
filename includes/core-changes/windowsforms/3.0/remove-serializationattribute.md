---
ms.openlocfilehash: d48ced9d0201a33f9149aba155ddd3d8bc04c93f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74643853"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a><span data-ttu-id="c5b89-101">Атрибут SerializableAttribute удален из некоторых типов Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c5b89-101">SerializableAttribute removed from some Windows Forms types</span></span>

<span data-ttu-id="c5b89-102">Атрибут <xref:System.SerializableAttribute> был удален из некоторых классов Windows Forms, для которых нет известных сценариев двоичной сериализации.</span><span class="sxs-lookup"><span data-stu-id="c5b89-102">The <xref:System.SerializableAttribute> has been removed from some Windows Forms classes that have no known binary serialization scenarios.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c5b89-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="c5b89-103">Change description</span></span>

<span data-ttu-id="c5b89-104">Следующие типы помечаются в .NET Framework атрибутом <xref:System.SerializableAttribute>, который удален в .NET Core:</span><span class="sxs-lookup"><span data-stu-id="c5b89-104">The following types are decorated with the <xref:System.SerializableAttribute> in .NET Framework, but the attribute has been removed in .NET Core:</span></span>

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

<span data-ttu-id="c5b89-105">Механизм сериализации всегда имел серьезные проблемы в плане обслуживания и безопасности.</span><span class="sxs-lookup"><span data-stu-id="c5b89-105">Historically, this serialization mechanism has had serious maintenance and security concerns.</span></span> <span data-ttu-id="c5b89-106">Поддержка `SerializableAttribute` для типов означает, что их необходимо проверять на наличие изменений сериализации в разных версиях, а также, возможно, на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="c5b89-106">Maintaining `SerializableAttribute` on types means those types must be tested for version-to-version serialization changes and potentially framework-to-framework serialization changes.</span></span> <span data-ttu-id="c5b89-107">Это затрудняет развитие таких типов и делает их обслуживание затратнее.</span><span class="sxs-lookup"><span data-stu-id="c5b89-107">This makes it harder to evolve those types and can be costly to maintain.</span></span> <span data-ttu-id="c5b89-108">Для этих типов нет известных сценариев двоичной сериализации, благодаря чему удаление атрибута имеет минимальные последствия.</span><span class="sxs-lookup"><span data-stu-id="c5b89-108">These types have no known binary serialization scenarios, which minimizes the impact of removing the attribute.</span></span>

<span data-ttu-id="c5b89-109">Дополнительные сведения см. в разделе [Двоичная сериализация](~/docs/standard/serialization/binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="c5b89-109">For more information, see [Binary serialization](~/docs/standard/serialization/binary-serialization.md).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c5b89-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c5b89-110">Version introduced</span></span>

<span data-ttu-id="c5b89-111">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="c5b89-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c5b89-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="c5b89-112">Recommended action</span></span>

<span data-ttu-id="c5b89-113">Измените код, работа которого зависит от возможности сериализации этих типов.</span><span class="sxs-lookup"><span data-stu-id="c5b89-113">Update any code that may depend on these types being marked as serializable.</span></span>

#### <a name="category"></a><span data-ttu-id="c5b89-114">Категория</span><span class="sxs-lookup"><span data-stu-id="c5b89-114">Category</span></span>

<span data-ttu-id="c5b89-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c5b89-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c5b89-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c5b89-116">Affected APIs</span></span>

- <span data-ttu-id="c5b89-117">None</span><span class="sxs-lookup"><span data-stu-id="c5b89-117">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
