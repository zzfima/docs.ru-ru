---
title: Интерфейс ICorDebugRemote
ms.date: 03/30/2017
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbed34f53ff43ca7887a58b3c879eaa74703da3e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744748"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="8a2f1-102">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="8a2f1-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="8a2f1-103">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="8a2f1-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a2f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a2f1-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8a2f1-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8a2f1-105">Methods</span></span>  
  
|<span data-ttu-id="8a2f1-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8a2f1-106">Method</span></span>|<span data-ttu-id="8a2f1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8a2f1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a2f1-108">Метод ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="8a2f1-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="8a2f1-109">Создает процесс на удаленном компьютере, для отладки управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8a2f1-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="8a2f1-110">Метод ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="8a2f1-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="8a2f1-111">Запускает процесс на удаленном компьютере в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="8a2f1-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a2f1-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a2f1-112">Remarks</span></span>  
 <span data-ttu-id="8a2f1-113">В настоящее время эта функция поддерживается только для отладки приложения на основе Silverlight целевой объект, который выполняется на удаленном компьютере Macintosh.</span><span class="sxs-lookup"><span data-stu-id="8a2f1-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a2f1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8a2f1-114">Requirements</span></span>  
 <span data-ttu-id="8a2f1-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a2f1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a2f1-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a2f1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a2f1-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a2f1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a2f1-118">**Версии платформы .NET framework:** 4.5, 4, 3.5 С ПАКЕТОМ ОБНОВЛЕНИЯ 1</span><span class="sxs-lookup"><span data-stu-id="8a2f1-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a2f1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8a2f1-119">See also</span></span>

- [<span data-ttu-id="8a2f1-120">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="8a2f1-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="8a2f1-121">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="8a2f1-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="8a2f1-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8a2f1-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
