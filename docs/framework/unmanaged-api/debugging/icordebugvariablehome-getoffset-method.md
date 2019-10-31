---
title: 'Метод ICorDebugVariableHome:: методом offset'
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
ms.openlocfilehash: 3af8c925b80b9fd4ed0a46d2bd50fe37a6f3154a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125095"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="d31de-102">Метод ICorDebugVariableHome:: методом offset</span><span class="sxs-lookup"><span data-stu-id="d31de-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="d31de-103">Возвращает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="d31de-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d31de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d31de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d31de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d31de-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="d31de-106">заполняет Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="d31de-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d31de-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d31de-107">Return Value</span></span>  
 <span data-ttu-id="d31de-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d31de-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="d31de-109">значения</span><span class="sxs-lookup"><span data-stu-id="d31de-109">Value</span></span>|<span data-ttu-id="d31de-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d31de-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="d31de-111">Переменная находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="d31de-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="d31de-112">Переменная не находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="d31de-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d31de-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d31de-113">Requirements</span></span>  
 <span data-ttu-id="d31de-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d31de-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d31de-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d31de-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d31de-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d31de-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d31de-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d31de-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31de-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d31de-118">See also</span></span>

- [<span data-ttu-id="d31de-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="d31de-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
