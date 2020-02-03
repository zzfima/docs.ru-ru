---
title: Функция Лоадфромхистори — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727930"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a9190-102">Функция Лоадфромхистори (Справочник по неуправляемым интерфейсам API WPF)</span><span class="sxs-lookup"><span data-stu-id="a9190-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a9190-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.</span><span class="sxs-lookup"><span data-stu-id="a9190-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a9190-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления Windows.</span><span class="sxs-lookup"><span data-stu-id="a9190-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9190-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9190-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9190-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9190-106">Parameters</span></span>  
 <span data-ttu-id="a9190-107">фистористреам</span><span class="sxs-lookup"><span data-stu-id="a9190-107">pHistoryStream</span></span>  
 <span data-ttu-id="a9190-108">Указатель на поток данных журнала.</span><span class="sxs-lookup"><span data-stu-id="a9190-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="a9190-109">пбиндкткс</span><span class="sxs-lookup"><span data-stu-id="a9190-109">pBindCtx</span></span>  
 <span data-ttu-id="a9190-110">Указатель на контекст привязки.</span><span class="sxs-lookup"><span data-stu-id="a9190-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9190-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a9190-111">Requirements</span></span>  
 <span data-ttu-id="a9190-112">**Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9190-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9190-113">**КОМПОНОВКИ**</span><span class="sxs-lookup"><span data-stu-id="a9190-113">**DLL:**</span></span>  
  
 <span data-ttu-id="a9190-114">В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll</span><span class="sxs-lookup"><span data-stu-id="a9190-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a9190-115">В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="a9190-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a9190-116">**Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9190-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9190-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a9190-117">See also</span></span>

- [<span data-ttu-id="a9190-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="a9190-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
