---
title: Функция ForwardTranslateAccelerator (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 4bb7e665bb836dc5f95b14f39179f1d4b9f8173d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080258"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="7ff83-102">Функция ForwardTranslateAccelerator (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7ff83-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="7ff83-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="7ff83-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="7ff83-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="7ff83-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ff83-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ff83-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ff83-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ff83-106">Parameters</span></span>  
 <span data-ttu-id="7ff83-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="7ff83-107">pMsg</span></span>  
 <span data-ttu-id="7ff83-108">Указатель на сообщение.</span><span class="sxs-lookup"><span data-stu-id="7ff83-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="7ff83-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="7ff83-109">appUnhandled</span></span>  
 <span data-ttu-id="7ff83-110">`true` Если приложение уже получил возможность для обработки входящего сообщения, но не предусмотрена. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="7ff83-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ff83-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7ff83-111">Requirements</span></span>  
 <span data-ttu-id="7ff83-112">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ff83-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ff83-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="7ff83-113">**DLL:**</span></span>  
  
 <span data-ttu-id="7ff83-114">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="7ff83-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="7ff83-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="7ff83-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="7ff83-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff83-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff83-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7ff83-117">See also</span></span>

- [<span data-ttu-id="7ff83-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="7ff83-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
