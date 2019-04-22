---
title: Функция LoadFromHistory (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: a4480d54390aea2771e2939b0a0825f6c49c3564
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084982"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="c376d-102">Функция LoadFromHistory (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="c376d-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="c376d-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="c376d-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="c376d-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="c376d-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c376d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c376d-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="c376d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c376d-106">Parameters</span></span>  
 <span data-ttu-id="c376d-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="c376d-107">pHistoryStream</span></span>  
 <span data-ttu-id="c376d-108">Указатель на поток данных предыстории.</span><span class="sxs-lookup"><span data-stu-id="c376d-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="c376d-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="c376d-109">pBindCtx</span></span>  
 <span data-ttu-id="c376d-110">Указатель на контекст привязки.</span><span class="sxs-lookup"><span data-stu-id="c376d-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c376d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c376d-111">Requirements</span></span>  
 <span data-ttu-id="c376d-112">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c376d-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c376d-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="c376d-113">**DLL:**</span></span>  
  
 <span data-ttu-id="c376d-114">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="c376d-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="c376d-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="c376d-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="c376d-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c376d-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c376d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c376d-117">See also</span></span>

- [<span data-ttu-id="c376d-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="c376d-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
