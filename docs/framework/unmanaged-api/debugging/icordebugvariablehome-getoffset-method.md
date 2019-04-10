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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212600"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="b3964-102">Метод ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="b3964-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="b3964-103">Получает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="b3964-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3964-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3964-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3964-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3964-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="b3964-106">[out] Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="b3964-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3964-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3964-107">Return Value</span></span>  
 <span data-ttu-id="b3964-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b3964-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="b3964-109">Значение</span><span class="sxs-lookup"><span data-stu-id="b3964-109">Value</span></span>|<span data-ttu-id="b3964-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b3964-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="b3964-111">Переменная находится в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="b3964-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="b3964-112">Переменная не существует в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="b3964-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3964-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b3964-113">Requirements</span></span>  
 <span data-ttu-id="b3964-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3964-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3964-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3964-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3964-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3964-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b3964-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b3964-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b3964-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b3964-118">See also</span></span>

- [<span data-ttu-id="b3964-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="b3964-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
