---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 05867af48b64cd1898b13fa055859c8cc0367c8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949582"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="95ce1-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="95ce1-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="95ce1-103">Перечисляет следующие `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) структуры в списке перечислителя, возвращая их в `rgelt` вместе с фактическое число перечисляемых элементов в `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="95ce1-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ce1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95ce1-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95ce1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="95ce1-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="95ce1-106">[in] Число [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) структур, возвращаемые в `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="95ce1-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="95ce1-107">[out] Массив celt размера (или больше) для получения перечисленных структур RAWINPUTDEVICE .</span><span class="sxs-lookup"><span data-stu-id="95ce1-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="95ce1-108">[out] Указатель на количество элементов, фактически представленных в `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="95ce1-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="95ce1-109">Вызывающий объект может передать `NULL`, если `rgelt` — один.</span><span class="sxs-lookup"><span data-stu-id="95ce1-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="95ce1-110">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="95ce1-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="95ce1-111">HRESULT: Значение S_OK, если число предоставленных элементов является `celt`; В противном случае значение S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="95ce1-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
