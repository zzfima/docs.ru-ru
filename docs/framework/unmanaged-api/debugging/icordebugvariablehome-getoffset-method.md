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
ms.openlocfilehash: 687c3bb441c2a12529c873b4fa5f9283b9326a40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659073"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="76339-102">Метод ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="76339-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="76339-103">Получает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="76339-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76339-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76339-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76339-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76339-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="76339-106">[out] Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="76339-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76339-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="76339-107">Return Value</span></span>  
 <span data-ttu-id="76339-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="76339-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="76339-109">Значение</span><span class="sxs-lookup"><span data-stu-id="76339-109">Value</span></span>|<span data-ttu-id="76339-110">Описание</span><span class="sxs-lookup"><span data-stu-id="76339-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="76339-111">Переменная находится в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="76339-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="76339-112">Переменная не существует в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="76339-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76339-113">Требования</span><span class="sxs-lookup"><span data-stu-id="76339-113">Requirements</span></span>  
 <span data-ttu-id="76339-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76339-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76339-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76339-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76339-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76339-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76339-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76339-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76339-118">См. также</span><span class="sxs-lookup"><span data-stu-id="76339-118">See also</span></span>
- [<span data-ttu-id="76339-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="76339-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
