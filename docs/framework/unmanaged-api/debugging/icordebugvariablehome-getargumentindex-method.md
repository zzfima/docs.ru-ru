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
ms.openlocfilehash: 175e45758d26d8168279c825d41ee58d049edf0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="beae4-102">Метод ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="beae4-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="beae4-103">Возвращает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="beae4-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beae4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beae4-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="beae4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="beae4-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="beae4-106">[out] Указатель на индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="beae4-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="beae4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="beae4-107">Return Value</span></span>  
 <span data-ttu-id="beae4-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="beae4-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="beae4-109">Значение</span><span class="sxs-lookup"><span data-stu-id="beae4-109">Value</span></span>|<span data-ttu-id="beae4-110">Описание</span><span class="sxs-lookup"><span data-stu-id="beae4-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="beae4-111">Вызов метода вернул недопустимый аргумент индекс.</span><span class="sxs-lookup"><span data-stu-id="beae4-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="beae4-112">Текущий [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляр представляет локальную переменную.</span><span class="sxs-lookup"><span data-stu-id="beae4-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beae4-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="beae4-113">Remarks</span></span>  
 <span data-ttu-id="beae4-114">Индекс аргумента можно использовать для получения метаданных для этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="beae4-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beae4-115">Требования</span><span class="sxs-lookup"><span data-stu-id="beae4-115">Requirements</span></span>  
 <span data-ttu-id="beae4-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beae4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beae4-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beae4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beae4-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beae4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beae4-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beae4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beae4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="beae4-120">See Also</span></span>  
 [<span data-ttu-id="beae4-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="beae4-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
