---
title: "Интерфейс ICorDebugRemote"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemote
helpviewer_keywords: ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a6195b53d11877c6b7b2a52c3fd8d194dfb51810
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="a1986-102">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="a1986-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="a1986-103">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="a1986-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1986-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1986-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a1986-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a1986-105">Methods</span></span>  
  
|<span data-ttu-id="a1986-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a1986-106">Method</span></span>|<span data-ttu-id="a1986-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a1986-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1986-108">Метод ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="a1986-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="a1986-109">Создает процесса на удаленном компьютере, для отладки управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="a1986-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="a1986-110">Метод ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="a1986-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="a1986-111">Запускает процесс на удаленном компьютере в отладчике.</span><span class="sxs-lookup"><span data-stu-id="a1986-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1986-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a1986-112">Remarks</span></span>  
 <span data-ttu-id="a1986-113">В настоящее время эта функция поддерживается только для отладки приложения на основе Silverlight целевой объект, который выполняется на удаленном компьютере Macintosh.</span><span class="sxs-lookup"><span data-stu-id="a1986-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1986-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a1986-114">Requirements</span></span>  
 <span data-ttu-id="a1986-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1986-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1986-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1986-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1986-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1986-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1986-118">**Версии платформы .NET framework:** 4.5, 4, 3.5 с пакетом обновления 1</span><span class="sxs-lookup"><span data-stu-id="a1986-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1986-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a1986-119">See Also</span></span>  
 [<span data-ttu-id="a1986-120">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="a1986-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="a1986-121">ICorDebug-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a1986-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="a1986-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a1986-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
