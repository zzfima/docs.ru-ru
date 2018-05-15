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
ms.openlocfilehash: 9a2ea7273fec62654c168d6786d3644b184ff7f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="b98e7-102">Метод ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="b98e7-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="b98e7-103">Получает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="b98e7-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b98e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b98e7-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b98e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b98e7-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="b98e7-106">[out] Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="b98e7-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b98e7-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b98e7-107">Return Value</span></span>  
 <span data-ttu-id="b98e7-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b98e7-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="b98e7-109">Значение</span><span class="sxs-lookup"><span data-stu-id="b98e7-109">Value</span></span>|<span data-ttu-id="b98e7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b98e7-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="b98e7-111">Переменная находится в расположении относительно регистра памяти.</span><span class="sxs-lookup"><span data-stu-id="b98e7-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="b98e7-112">Переменная не существует в расположении относительно регистра памяти.</span><span class="sxs-lookup"><span data-stu-id="b98e7-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b98e7-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b98e7-113">Requirements</span></span>  
 <span data-ttu-id="b98e7-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b98e7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b98e7-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b98e7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b98e7-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b98e7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b98e7-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b98e7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98e7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b98e7-118">See Also</span></span>  
 [<span data-ttu-id="b98e7-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="b98e7-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
