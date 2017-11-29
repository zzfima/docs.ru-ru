---
title: "Метод ICorDebug::GetProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 189aab8a1e640d822dc8c45098b3af7cb81e916c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="29c29-102">Метод ICorDebug::GetProcess</span><span class="sxs-lookup"><span data-stu-id="29c29-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="29c29-103">Возвращает указатель на экземпляр «ICorDebugProcess» для указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="29c29-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29c29-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29c29-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29c29-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="29c29-106">[in] Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="29c29-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="29c29-107">[out] Указатель на адрес `ICorDebugProcess` экземпляра для указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="29c29-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29c29-108">Требования</span><span class="sxs-lookup"><span data-stu-id="29c29-108">Requirements</span></span>  
 <span data-ttu-id="29c29-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c29-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c29-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29c29-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29c29-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29c29-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29c29-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c29-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c29-113">См. также</span><span class="sxs-lookup"><span data-stu-id="29c29-113">See Also</span></span>  
 [<span data-ttu-id="29c29-114">ICorDebug-интерфейс</span><span class="sxs-lookup"><span data-stu-id="29c29-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
