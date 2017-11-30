---
title: "Метод ICorDebugThread::GetObject"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94e6d69ff2a873f387da0e93bcd859d53103d4b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="f5bd8-102">Метод ICorDebugThread::GetObject</span><span class="sxs-lookup"><span data-stu-id="f5bd8-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="f5bd8-103">Возвращает указатель на интерфейс среды выполнения (CLR) потоку выполнения.</span><span class="sxs-lookup"><span data-stu-id="f5bd8-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5bd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5bd8-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5bd8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5bd8-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="f5bd8-106">[out] Указатель на адрес объекта интерфейса ICorDebugValue, представляющий поток среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f5bd8-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5bd8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f5bd8-107">Requirements</span></span>  
 <span data-ttu-id="f5bd8-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5bd8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5bd8-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5bd8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5bd8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5bd8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5bd8-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5bd8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5bd8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f5bd8-112">See Also</span></span>  
 <xref:System.Threading.Thread>
