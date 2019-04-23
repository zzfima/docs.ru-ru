---
ms.openlocfilehash: b4e062fe3a00b76da144e706841f87b2a95888e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774410"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="7d5f8-101">Конструктор EncoderParameter устарел</span><span class="sxs-lookup"><span data-stu-id="7d5f8-101">EncoderParameter ctor is obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7d5f8-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7d5f8-102">Details</span></span>|<span data-ttu-id="7d5f8-103">Конструктор <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> устарел. При его использовании будут выводиться предупреждения сборки.</span><span class="sxs-lookup"><span data-stu-id="7d5f8-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>|
|<span data-ttu-id="7d5f8-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="7d5f8-104">Suggestion</span></span>|<span data-ttu-id="7d5f8-105">Несмотря на то, что конструктор <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> будет продолжать работать, во избежание вывода устаревшего предупреждения сборки при повторной компиляции кода с помощью средств .NET Framework 4.5 нужен следующий конструктор: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="7d5f8-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>|
|<span data-ttu-id="7d5f8-106">Область</span><span class="sxs-lookup"><span data-stu-id="7d5f8-106">Scope</span></span>|<span data-ttu-id="7d5f8-107">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="7d5f8-107">Minor</span></span>|
|<span data-ttu-id="7d5f8-108">Версия</span><span class="sxs-lookup"><span data-stu-id="7d5f8-108">Version</span></span>|<span data-ttu-id="7d5f8-109">4.5</span><span class="sxs-lookup"><span data-stu-id="7d5f8-109">4.5</span></span>|
|<span data-ttu-id="7d5f8-110">Тип</span><span class="sxs-lookup"><span data-stu-id="7d5f8-110">Type</span></span>|<span data-ttu-id="7d5f8-111">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="7d5f8-111">Retargeting</span></span>|
|<span data-ttu-id="7d5f8-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7d5f8-112">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
