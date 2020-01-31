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
ms.openlocfilehash: a6f93ec3c7ffe415c41dcf094dbde2f0a08969f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791001"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="c98be-102">Метод ICorDebugVariableHome:: методом offset</span><span class="sxs-lookup"><span data-stu-id="c98be-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="c98be-103">Возвращает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="c98be-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c98be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c98be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c98be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c98be-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="c98be-106">заполняет Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="c98be-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c98be-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c98be-107">Return Value</span></span>  
 <span data-ttu-id="c98be-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c98be-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="c98be-109">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="c98be-109">Value</span></span>|<span data-ttu-id="c98be-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c98be-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="c98be-111">Переменная находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="c98be-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="c98be-112">Переменная не находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="c98be-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c98be-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c98be-113">Requirements</span></span>  
 <span data-ttu-id="c98be-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c98be-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c98be-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c98be-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c98be-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c98be-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c98be-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c98be-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c98be-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="c98be-118">See also</span></span>

- [<span data-ttu-id="c98be-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="c98be-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
