---
title: Функция LoadFromHistory - Ссылка на Неуправляемый API WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141579"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="6dec3-102">Функция LoadFromHistory (Ссылка на Неуправляемый API WPF)</span><span class="sxs-lookup"><span data-stu-id="6dec3-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="6dec3-103">Этот API поддерживает инфраструктуру Фонда презентаций Windows (WPF) и не предназначен для использования непосредственно из вашего кода.</span><span class="sxs-lookup"><span data-stu-id="6dec3-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="6dec3-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления окнами.</span><span class="sxs-lookup"><span data-stu-id="6dec3-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dec3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6dec3-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dec3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6dec3-106">Parameters</span></span>  
 <span data-ttu-id="6dec3-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="6dec3-107">pHistoryStream</span></span>  
 <span data-ttu-id="6dec3-108">Указатель на поток информации об истории.</span><span class="sxs-lookup"><span data-stu-id="6dec3-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="6dec3-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="6dec3-109">pBindCtx</span></span>  
 <span data-ttu-id="6dec3-110">Указатель на контекст связывания.</span><span class="sxs-lookup"><span data-stu-id="6dec3-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dec3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6dec3-111">Requirements</span></span>  
 <span data-ttu-id="6dec3-112">**Платформы:** Смотрите [требования рамочной системы .NET](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dec3-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dec3-113">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="6dec3-113">**DLL:**</span></span>  
  
 <span data-ttu-id="6dec3-114">В рамках .NET 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="6dec3-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="6dec3-115">В рамках .NET 4 и позже: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="6dec3-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="6dec3-116">**Рамочная версия .NET:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dec3-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dec3-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6dec3-117">See also</span></span>

- [<span data-ttu-id="6dec3-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="6dec3-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
