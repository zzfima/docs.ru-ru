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
ms.openlocfilehash: 78031ed80fe83b736a351886457f9200534f470b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591517"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="13ff4-102">Функция ForwardTranslateAccelerator (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="13ff4-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="13ff4-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="13ff4-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="13ff4-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="13ff4-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13ff4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13ff4-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13ff4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="13ff4-106">Parameters</span></span>  
 <span data-ttu-id="13ff4-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="13ff4-107">pMsg</span></span>  
 <span data-ttu-id="13ff4-108">Указатель на сообщение.</span><span class="sxs-lookup"><span data-stu-id="13ff4-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="13ff4-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="13ff4-109">appUnhandled</span></span>  
 <span data-ttu-id="13ff4-110">`true` Если приложение уже получил возможность для обработки входящего сообщения, но не предусмотрена. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="13ff4-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13ff4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="13ff4-111">Requirements</span></span>  
 <span data-ttu-id="13ff4-112">**Платформы:** См. в разделе [системные требования .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13ff4-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13ff4-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="13ff4-113">**DLL:**</span></span>  
  
 <span data-ttu-id="13ff4-114">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="13ff4-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="13ff4-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="13ff4-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="13ff4-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13ff4-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ff4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="13ff4-117">See also</span></span>
- [<span data-ttu-id="13ff4-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="13ff4-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
