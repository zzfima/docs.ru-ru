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
ms.openlocfilehash: 864cb893511bceabd61ce0064065b3866ce01dfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986756"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="f920d-102">Метод ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="f920d-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="f920d-103">Получает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="f920d-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f920d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f920d-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f920d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f920d-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="f920d-106">[out] Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="f920d-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f920d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f920d-107">Return Value</span></span>  
 <span data-ttu-id="f920d-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f920d-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="f920d-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f920d-109">Value</span></span>|<span data-ttu-id="f920d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f920d-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="f920d-111">Переменная находится в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="f920d-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="f920d-112">Переменная не существует в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="f920d-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f920d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f920d-113">Requirements</span></span>  
 <span data-ttu-id="f920d-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f920d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f920d-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f920d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f920d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f920d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f920d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f920d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f920d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f920d-118">See also</span></span>

- [<span data-ttu-id="f920d-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="f920d-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
