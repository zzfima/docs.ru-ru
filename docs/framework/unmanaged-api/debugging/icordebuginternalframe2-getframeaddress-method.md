---
title: Метод ICorDebugInternalFrame2::GetFrameAddress
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3293c3b0d5fa4615c351949afdb1acf8cd560b5e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480719"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="ded9c-102">Метод ICorDebugInternalFrame2::GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="ded9c-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="ded9c-103">Возвращает адрес внутреннего кадра стека.</span><span class="sxs-lookup"><span data-stu-id="ded9c-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ded9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ded9c-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ded9c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ded9c-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="ded9c-106">[out] Указатель на `CORDB_ADDRESS` для внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="ded9c-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ded9c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ded9c-107">Return Value</span></span>  
 <span data-ttu-id="ded9c-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="ded9c-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ded9c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ded9c-109">HRESULT</span></span>|<span data-ttu-id="ded9c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ded9c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ded9c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ded9c-111">S_OK</span></span>|<span data-ttu-id="ded9c-112">Адрес внутреннего кадра успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ded9c-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="ded9c-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ded9c-113">E_FAIL</span></span>|<span data-ttu-id="ded9c-114">Адрес внутреннего кадра не могут быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="ded9c-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="ded9c-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ded9c-115">E_INVALIDARG</span></span>|<span data-ttu-id="ded9c-116">Свойство `pAddress` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="ded9c-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ded9c-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ded9c-117">Remarks</span></span>  
 <span data-ttu-id="ded9c-118">Значение, возвращаемое в `pAddress` может использоваться для определения расположения внутреннего кадра относительно других фреймы в стеке.</span><span class="sxs-lookup"><span data-stu-id="ded9c-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="ded9c-119">Даже на компьютерах с архитектурой IA-64 внутренний кадр существует только в стеке, и нет соответствующего указателя в резервное хранилище.</span><span class="sxs-lookup"><span data-stu-id="ded9c-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ded9c-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ded9c-120">Requirements</span></span>  
 <span data-ttu-id="ded9c-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ded9c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ded9c-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ded9c-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ded9c-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ded9c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ded9c-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ded9c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded9c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ded9c-125">See also</span></span>
- [<span data-ttu-id="ded9c-126">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="ded9c-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="ded9c-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ded9c-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ded9c-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="ded9c-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
