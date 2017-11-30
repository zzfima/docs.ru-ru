---
title: "Метод ICoreClrDebugTarget::FreeMemory"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreDebugTarget.FreeMemory
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7b199d3a3406a1a1dd21a560424ef342b03ce6c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="844a8-102">Метод ICoreClrDebugTarget::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="844a8-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="844a8-103">Освобождает память, выделенную [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) и [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="844a8-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="844a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="844a8-104">Syntax</span></span>  
  
```  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="844a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="844a8-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="844a8-106">[in] Указатель на массив, возвращаемый методом [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) или [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="844a8-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="844a8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="844a8-107">Requirements</span></span>  
 <span data-ttu-id="844a8-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="844a8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="844a8-109">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="844a8-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="844a8-110">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="844a8-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="844a8-111">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="844a8-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844a8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="844a8-112">See Also</span></span>  
 [<span data-ttu-id="844a8-113">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="844a8-113">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
