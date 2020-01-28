---
title: Функция Форвардтранслатеакцелератор — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747037"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="19ebc-102">Функция Форвардтранслатеакцелератор (Справочник по неуправляемым интерфейсам API WPF)</span><span class="sxs-lookup"><span data-stu-id="19ebc-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="19ebc-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.</span><span class="sxs-lookup"><span data-stu-id="19ebc-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="19ebc-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления Windows.</span><span class="sxs-lookup"><span data-stu-id="19ebc-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ebc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19ebc-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="19ebc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="19ebc-106">Parameters</span></span>  
 <span data-ttu-id="19ebc-107">пмсг</span><span class="sxs-lookup"><span data-stu-id="19ebc-107">pMsg</span></span>  
 <span data-ttu-id="19ebc-108">Указатель на сообщение.</span><span class="sxs-lookup"><span data-stu-id="19ebc-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="19ebc-109">аппунхандлед</span><span class="sxs-lookup"><span data-stu-id="19ebc-109">appUnhandled</span></span>  
 <span data-ttu-id="19ebc-110">`true`, когда приложению уже предоставлен шанс обработать входное сообщение, но оно не обработано. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="19ebc-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19ebc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="19ebc-111">Requirements</span></span>  
 <span data-ttu-id="19ebc-112">**Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19ebc-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19ebc-113">**КОМПОНОВКИ**</span><span class="sxs-lookup"><span data-stu-id="19ebc-113">**DLL:**</span></span>  
  
 <span data-ttu-id="19ebc-114">В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll</span><span class="sxs-lookup"><span data-stu-id="19ebc-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="19ebc-115">В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="19ebc-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="19ebc-116">**Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19ebc-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ebc-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="19ebc-117">See also</span></span>

- [<span data-ttu-id="19ebc-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="19ebc-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
