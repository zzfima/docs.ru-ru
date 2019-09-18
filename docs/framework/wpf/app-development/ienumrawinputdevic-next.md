---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053401"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="fc74e-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="fc74e-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="fc74e-103">Перечисляет следующие `celt` структуры [равинпутдевице](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) в списке перечислителя, возвращая их в `rgelt` вместе с фактическим числом перечисляемых элементов в. `pceltFetched`</span><span class="sxs-lookup"><span data-stu-id="fc74e-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc74e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc74e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc74e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc74e-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="fc74e-106">окне Число структур [равинпутдевице](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) , возвращаемых `rgelt`в.</span><span class="sxs-lookup"><span data-stu-id="fc74e-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="fc74e-107">[out] Массив celt размера (или больше) для получения перечисленных структур RAWINPUTDEVICE .</span><span class="sxs-lookup"><span data-stu-id="fc74e-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="fc74e-108">[out] Указатель на количество элементов, фактически представленных в `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="fc74e-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="fc74e-109">Вызывающий объект может передать `NULL`, если `rgelt` — один.</span><span class="sxs-lookup"><span data-stu-id="fc74e-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="fc74e-110">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc74e-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="fc74e-111">HRESULT: S_OK, если число представленных элементов равно `celt`; S_FALSE в противном случае.</span><span class="sxs-lookup"><span data-stu-id="fc74e-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
