---
title: Интерфейс ICoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4576d8ea7d601e1b37d0cb6f54802f93bc128622
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593788"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="9cb6d-102">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="9cb6d-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="9cb6d-103">Предоставляет методы, управления счетчиками ссылок, перечислить процессы и освобождения памяти, связанной с помощью отладчика, который подключен к удаленному целевому объекту Macintosh Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9cb6d-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cb6d-104">Syntax</span></span>  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9cb6d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9cb6d-105">Methods</span></span>  
  
|<span data-ttu-id="9cb6d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9cb6d-106">Method</span></span>|<span data-ttu-id="9cb6d-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="9cb6d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cb6d-108">Метод ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="9cb6d-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="9cb6d-109">Перечисляет процессы, работающие на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9cb6d-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="9cb6d-110">Метод ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="9cb6d-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="9cb6d-111">Перечисляет языковых сред выполнения (CLR) в указанном процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9cb6d-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="9cb6d-112">Метод ICoreClrDebugTarget::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="9cb6d-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="9cb6d-113">Освобождает память, выделенную с помощью методов перечисления в этот класс.</span><span class="sxs-lookup"><span data-stu-id="9cb6d-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cb6d-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cb6d-114">Remarks</span></span>  
 <span data-ttu-id="9cb6d-115">В настоящее время эта функция поддерживается только для отладки приложения на основе Silverlight целевой объект, который выполняется на удаленном компьютере Macintosh.</span><span class="sxs-lookup"><span data-stu-id="9cb6d-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cb6d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9cb6d-116">Requirements</span></span>  
 <span data-ttu-id="9cb6d-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cb6d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cb6d-118">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="9cb6d-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9cb6d-119">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="9cb6d-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9cb6d-120">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="9cb6d-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb6d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9cb6d-121">See also</span></span>
- [<span data-ttu-id="9cb6d-122">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="9cb6d-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="9cb6d-123">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="9cb6d-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="9cb6d-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9cb6d-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
