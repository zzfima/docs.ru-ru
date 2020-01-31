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
ms.openlocfilehash: 190671b4f690f8c2cad43cf446a1196985ec5a42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790755"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="ce7c8-102">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="ce7c8-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="ce7c8-103">Предоставляет методы, управляющие счетчиком ссылок, перечисление процессов и освобождение памяти, связанной с отладчиком, который подключен к удаленному целевому объекту Macintosh Silverlight.</span><span class="sxs-lookup"><span data-stu-id="ce7c8-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce7c8-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="ce7c8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ce7c8-105">Methods</span></span>  
  
|<span data-ttu-id="ce7c8-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ce7c8-106">Method</span></span>|<span data-ttu-id="ce7c8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ce7c8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce7c8-108">Метод ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="ce7c8-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="ce7c8-109">Перечисляет процессы, работающие на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce7c8-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="ce7c8-110">Метод ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="ce7c8-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="ce7c8-111">Перечисляет общеязыковые среды выполнения (CLR) в указанном процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce7c8-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="ce7c8-112">Метод ICoreClrDebugTarget::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="ce7c8-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="ce7c8-113">Освобождает память, выделенную методами перечисления в этом классе.</span><span class="sxs-lookup"><span data-stu-id="ce7c8-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce7c8-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="ce7c8-114">Remarks</span></span>  
 <span data-ttu-id="ce7c8-115">В настоящее время эта функция поддерживается только для отладки целевого объекта приложения на основе Silverlight, который выполняется на удаленном компьютере Macintosh.</span><span class="sxs-lookup"><span data-stu-id="ce7c8-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7c8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ce7c8-116">Requirements</span></span>  
 <span data-ttu-id="ce7c8-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce7c8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7c8-118">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="ce7c8-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ce7c8-119">**Библиотека:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="ce7c8-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ce7c8-120">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="ce7c8-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7c8-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce7c8-121">See also</span></span>

- [<span data-ttu-id="ce7c8-122">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="ce7c8-122">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="ce7c8-123">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ce7c8-123">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="ce7c8-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ce7c8-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
