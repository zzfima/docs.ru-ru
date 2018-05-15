---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 3cf3231bd48290c5b6b0ce8eeb6534de564c0c85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="4ee08-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="4ee08-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="4ee08-103">Перечисляет следующего `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) структуры в списке перечислителя, возвращая их в `rgelt` вместе с фактическое число перечисленных элементов в `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="4ee08-103">Enumerates the next `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ee08-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ee08-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ee08-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="4ee08-106">[in] Число [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) структур, возвращаемые в `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="4ee08-106">[in] Number of [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="4ee08-107">[out] Массив celt размера (или больше) для получения перечисленных структур RAWINPUTDEVICE .</span><span class="sxs-lookup"><span data-stu-id="4ee08-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="4ee08-108">[out] Указатель на количество элементов, фактически представленных в `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="4ee08-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="4ee08-109">Вызывающий объект может передать `NULL`, если `rgelt` — один.</span><span class="sxs-lookup"><span data-stu-id="4ee08-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4ee08-110">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4ee08-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="4ee08-111">HRESULT: значение S_OK, если число предоставленных элементов составляет `celt`; в противном случае значение S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="4ee08-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
