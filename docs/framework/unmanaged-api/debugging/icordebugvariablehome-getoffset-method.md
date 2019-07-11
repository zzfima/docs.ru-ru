---
title: Метод ICorDebugVariableHome::GetOffset
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fdab81d499fe1508493cb0bf05a1787974a9d01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774539"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="b1e8c-102">Метод ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="b1e8c-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="b1e8c-103">Получает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="b1e8c-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e8c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1e8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1e8c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1e8c-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="b1e8c-106">[out] Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="b1e8c-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1e8c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b1e8c-107">Return Value</span></span>  
 <span data-ttu-id="b1e8c-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b1e8c-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="b1e8c-109">Значение</span><span class="sxs-lookup"><span data-stu-id="b1e8c-109">Value</span></span>|<span data-ttu-id="b1e8c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b1e8c-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="b1e8c-111">Переменная находится в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="b1e8c-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="b1e8c-112">Переменная не существует в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="b1e8c-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1e8c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b1e8c-113">Requirements</span></span>  
 <span data-ttu-id="b1e8c-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1e8c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1e8c-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1e8c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1e8c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1e8c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1e8c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1e8c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e8c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b1e8c-118">See also</span></span>

- [<span data-ttu-id="b1e8c-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="b1e8c-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
