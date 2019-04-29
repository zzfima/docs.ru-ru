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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766136"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="79d4c-102">Функция LoadFromHistory (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="79d4c-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="79d4c-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="79d4c-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="79d4c-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="79d4c-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79d4c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79d4c-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="79d4c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="79d4c-106">Parameters</span></span>  
 <span data-ttu-id="79d4c-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="79d4c-107">pHistoryStream</span></span>  
 <span data-ttu-id="79d4c-108">Указатель на поток данных предыстории.</span><span class="sxs-lookup"><span data-stu-id="79d4c-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="79d4c-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="79d4c-109">pBindCtx</span></span>  
 <span data-ttu-id="79d4c-110">Указатель на контекст привязки.</span><span class="sxs-lookup"><span data-stu-id="79d4c-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79d4c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="79d4c-111">Requirements</span></span>  
 <span data-ttu-id="79d4c-112">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79d4c-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79d4c-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="79d4c-113">**DLL:**</span></span>  
  
 <span data-ttu-id="79d4c-114">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="79d4c-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="79d4c-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="79d4c-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="79d4c-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79d4c-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d4c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="79d4c-117">See also</span></span>

- [<span data-ttu-id="79d4c-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="79d4c-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
