---
ms.openlocfilehash: b4e062fe3a00b76da144e706841f87b2a95888e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234802"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="0e7b5-101">Конструктор EncoderParameter устарел</span><span class="sxs-lookup"><span data-stu-id="0e7b5-101">EncoderParameter ctor is obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0e7b5-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0e7b5-102">Details</span></span>|<span data-ttu-id="0e7b5-103">Конструктор <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> устарел. При его использовании будут выводиться предупреждения сборки.</span><span class="sxs-lookup"><span data-stu-id="0e7b5-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>|
|<span data-ttu-id="0e7b5-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="0e7b5-104">Suggestion</span></span>|<span data-ttu-id="0e7b5-105">Несмотря на то, что конструктор <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> будет продолжать работать, во избежание вывода устаревшего предупреждения сборки при повторной компиляции кода с помощью средств .NET Framework 4.5 нужен следующий конструктор: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="0e7b5-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>|
|<span data-ttu-id="0e7b5-106">Область</span><span class="sxs-lookup"><span data-stu-id="0e7b5-106">Scope</span></span>|<span data-ttu-id="0e7b5-107">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="0e7b5-107">Minor</span></span>|
|<span data-ttu-id="0e7b5-108">Версия</span><span class="sxs-lookup"><span data-stu-id="0e7b5-108">Version</span></span>|<span data-ttu-id="0e7b5-109">4.5</span><span class="sxs-lookup"><span data-stu-id="0e7b5-109">4.5</span></span>|
|<span data-ttu-id="0e7b5-110">Тип</span><span class="sxs-lookup"><span data-stu-id="0e7b5-110">Type</span></span>|<span data-ttu-id="0e7b5-111">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="0e7b5-111">Retargeting</span></span>|
|<span data-ttu-id="0e7b5-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0e7b5-112">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
