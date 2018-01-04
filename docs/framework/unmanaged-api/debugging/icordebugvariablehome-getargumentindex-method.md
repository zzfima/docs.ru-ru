---
title: "Метод ICorDebugVariableHome::GetArgumentIndex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetArgumentIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 739d4d787858f64871269ea9bd467bc49424fbae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="e1126-102">Метод ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="e1126-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="e1126-103">Возвращает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="e1126-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1126-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1126-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1126-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1126-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="e1126-106">[out] Указатель на индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="e1126-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1126-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e1126-107">Return Value</span></span>  
 <span data-ttu-id="e1126-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="e1126-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="e1126-109">Значение</span><span class="sxs-lookup"><span data-stu-id="e1126-109">Value</span></span>|<span data-ttu-id="e1126-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="e1126-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="e1126-111">Вызов метода вернул недопустимый аргумент индекс.</span><span class="sxs-lookup"><span data-stu-id="e1126-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="e1126-112">Текущий [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляр представляет локальную переменную.</span><span class="sxs-lookup"><span data-stu-id="e1126-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1126-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1126-113">Remarks</span></span>  
 <span data-ttu-id="e1126-114">Индекс аргумента можно использовать для получения метаданных для этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="e1126-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1126-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e1126-115">Requirements</span></span>  
 <span data-ttu-id="e1126-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1126-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1126-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1126-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1126-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1126-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1126-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1126-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1126-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e1126-120">See Also</span></span>  
 [<span data-ttu-id="e1126-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e1126-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
