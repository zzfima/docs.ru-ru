---
title: Метод ICorDebugHandleValue::Dispose
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.Dispose
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::Dispose
helpviewer_keywords:
- ICorDebugHandleValue::Dispose method [.NET Framework debugging]
- Dispose method [.NET Framework debugging]
ms.assetid: c1542811-0a7f-4235-bcfd-b24370d6f24b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21703aa911b5222fff71282e6da26aa5c0e2853
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756855"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="2f2dc-102">Метод ICorDebugHandleValue::Dispose</span><span class="sxs-lookup"><span data-stu-id="2f2dc-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="2f2dc-103">Освобождает дескриптор, на которые ссылается этот объект ICorDebugHandleValue без явно освобождая указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2f2dc-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f2dc-104">Syntax</span></span>  
  
```cpp  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="2f2dc-105">Требования</span><span class="sxs-lookup"><span data-stu-id="2f2dc-105">Requirements</span></span>  
 <span data-ttu-id="2f2dc-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f2dc-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f2dc-107">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f2dc-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f2dc-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f2dc-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f2dc-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f2dc-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
