---
title: Метод ICorDebugVariableHome::GetArgumentIndex
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20f65218928ee07d67ea742154469ac3cbea9241
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421769"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="e944d-102">Метод ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="e944d-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="e944d-103">Возвращает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="e944d-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e944d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e944d-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e944d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e944d-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="e944d-106">[out] Указатель на индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="e944d-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e944d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e944d-107">Return Value</span></span>  
 <span data-ttu-id="e944d-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="e944d-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="e944d-109">Значение</span><span class="sxs-lookup"><span data-stu-id="e944d-109">Value</span></span>|<span data-ttu-id="e944d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e944d-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="e944d-111">Вызов метода вернул недопустимый аргумент индекс.</span><span class="sxs-lookup"><span data-stu-id="e944d-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="e944d-112">Текущий [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляр представляет локальную переменную.</span><span class="sxs-lookup"><span data-stu-id="e944d-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e944d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="e944d-113">Remarks</span></span>  
 <span data-ttu-id="e944d-114">Индекс аргумента можно использовать для получения метаданных для этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="e944d-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e944d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e944d-115">Requirements</span></span>  
 <span data-ttu-id="e944d-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e944d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e944d-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e944d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e944d-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e944d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e944d-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e944d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e944d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e944d-120">See Also</span></span>  
 [<span data-ttu-id="e944d-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e944d-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
