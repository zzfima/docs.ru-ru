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
ms.openlocfilehash: 957035591090fb5a6a615662c4840ff16509ee20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138510"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="2344c-102">Метод ICorDebugHandleValue::Dispose</span><span class="sxs-lookup"><span data-stu-id="2344c-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="2344c-103">Освобождает дескриптор, на который ссылается этот объект ICorDebugHandleValue, без явного освобождения указателя интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2344c-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2344c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2344c-104">Syntax</span></span>  
  
```cpp  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="2344c-105">Требования</span><span class="sxs-lookup"><span data-stu-id="2344c-105">Requirements</span></span>  
 <span data-ttu-id="2344c-106">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2344c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2344c-107">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2344c-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2344c-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2344c-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2344c-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2344c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
