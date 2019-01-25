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
ms.openlocfilehash: 42be46d836a299139bded938237fe2a06e9794a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646937"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="fc5be-102">Функция LoadFromHistory (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="fc5be-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="fc5be-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="fc5be-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="fc5be-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="fc5be-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc5be-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc5be-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc5be-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc5be-106">Parameters</span></span>  
 <span data-ttu-id="fc5be-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="fc5be-107">pHistoryStream</span></span>  
 <span data-ttu-id="fc5be-108">Указатель на поток данных предыстории.</span><span class="sxs-lookup"><span data-stu-id="fc5be-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="fc5be-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="fc5be-109">pBindCtx</span></span>  
 <span data-ttu-id="fc5be-110">Указатель на контекст привязки.</span><span class="sxs-lookup"><span data-stu-id="fc5be-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc5be-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fc5be-111">Requirements</span></span>  
 <span data-ttu-id="fc5be-112">**Платформы:** См. в разделе [системные требования .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc5be-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc5be-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="fc5be-113">**DLL:**</span></span>  
  
 <span data-ttu-id="fc5be-114">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="fc5be-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="fc5be-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="fc5be-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="fc5be-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc5be-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5be-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fc5be-117">See also</span></span>
- [<span data-ttu-id="fc5be-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="fc5be-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
