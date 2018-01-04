---
title: "Метод ICorDebugVariableHome::GetSlotIndex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetSlotIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ff62b79fbbb0896941730797473209872e6bfc2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="4893c-102">Метод ICorDebugVariableHome::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="4893c-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="4893c-103">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="4893c-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4893c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4893c-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4893c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4893c-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="4893c-106">[out] Указатель на индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="4893c-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4893c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4893c-107">Return Value</span></span>  
 <span data-ttu-id="4893c-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="4893c-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="4893c-109">Значение</span><span class="sxs-lookup"><span data-stu-id="4893c-109">Value</span></span>|<span data-ttu-id="4893c-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="4893c-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="4893c-111">Вызванный метод вернул значение индекс слота в `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="4893c-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="4893c-112">Текущий [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляр представляет аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="4893c-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4893c-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="4893c-113">Remarks</span></span>  
 <span data-ttu-id="4893c-114">Индекс слота можно использовать для получения метаданных об этой локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="4893c-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4893c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="4893c-115">Requirements</span></span>  
 <span data-ttu-id="4893c-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4893c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4893c-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4893c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4893c-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4893c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4893c-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4893c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4893c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4893c-120">See Also</span></span>  
 [<span data-ttu-id="4893c-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="4893c-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
