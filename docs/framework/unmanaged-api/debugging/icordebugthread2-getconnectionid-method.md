---
title: Метод ICorDebugThread2::GetConnectionID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d51e21eab4ac1edc81b58171e5382ada170a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946352"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="18f5d-102">Метод ICorDebugThread2::GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="18f5d-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="18f5d-103">Получает идентификатор подключения для этого объекта ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="18f5d-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f5d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18f5d-104">Syntax</span></span>  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18f5d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18f5d-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="18f5d-106">[out] Объект `CONNID` , представляющий идентификатор соединения.</span><span class="sxs-lookup"><span data-stu-id="18f5d-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18f5d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="18f5d-107">Remarks</span></span>  
 <span data-ttu-id="18f5d-108">`GetConnectionID` Метод возвращает нуль в `pdwConnectionId` параметра, если этот поток не является частью подключения.</span><span class="sxs-lookup"><span data-stu-id="18f5d-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="18f5d-109">Если этот поток был подключен к экземпляру из Microsoft SQL Server 2005 Analysis Services (SSAS), `CONNID` сопоставляется идентификатор серверного процесса (SPID).</span><span class="sxs-lookup"><span data-stu-id="18f5d-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f5d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="18f5d-110">Requirements</span></span>  
 <span data-ttu-id="18f5d-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18f5d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f5d-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18f5d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18f5d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18f5d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18f5d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f5d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
