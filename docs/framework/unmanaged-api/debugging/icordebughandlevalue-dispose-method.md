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
ms.openlocfilehash: 9114799b87d39333ff9da66429dc1ea99ec2131c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775704"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="72832-102">Метод ICorDebugHandleValue::Dispose</span><span class="sxs-lookup"><span data-stu-id="72832-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="72832-103">Освобождает дескриптор, на которые ссылается этот объект ICorDebugHandleValue без явно освобождая указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="72832-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72832-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72832-104">Syntax</span></span>  
  
```  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="72832-105">Требования</span><span class="sxs-lookup"><span data-stu-id="72832-105">Requirements</span></span>  
 <span data-ttu-id="72832-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72832-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72832-107">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72832-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72832-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72832-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72832-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72832-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
