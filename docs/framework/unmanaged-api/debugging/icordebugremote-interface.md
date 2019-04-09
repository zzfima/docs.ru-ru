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
ms.openlocfilehash: a50a799c625c647aa275994bc92738b8a4267eec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135581"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="adcdc-102">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="adcdc-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="adcdc-103">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="adcdc-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adcdc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adcdc-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="adcdc-105">Методы</span><span class="sxs-lookup"><span data-stu-id="adcdc-105">Methods</span></span>  
  
|<span data-ttu-id="adcdc-106">Метод</span><span class="sxs-lookup"><span data-stu-id="adcdc-106">Method</span></span>|<span data-ttu-id="adcdc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="adcdc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="adcdc-108">Метод ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="adcdc-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="adcdc-109">Создает процесс на удаленном компьютере, для отладки управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="adcdc-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="adcdc-110">Метод ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="adcdc-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="adcdc-111">Запускает процесс на удаленном компьютере в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="adcdc-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adcdc-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="adcdc-112">Remarks</span></span>  
 <span data-ttu-id="adcdc-113">В настоящее время эта функция поддерживается только для отладки приложения на основе Silverlight целевой объект, который выполняется на удаленном компьютере Macintosh.</span><span class="sxs-lookup"><span data-stu-id="adcdc-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adcdc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="adcdc-114">Requirements</span></span>  
 <span data-ttu-id="adcdc-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adcdc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adcdc-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adcdc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adcdc-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adcdc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adcdc-118">**Версии платформы .NET framework:** 4.5, 4, 3.5 С ПАКЕТОМ ОБНОВЛЕНИЯ 1</span><span class="sxs-lookup"><span data-stu-id="adcdc-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adcdc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="adcdc-119">See also</span></span>

- [<span data-ttu-id="adcdc-120">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="adcdc-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="adcdc-121">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="adcdc-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="adcdc-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="adcdc-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
