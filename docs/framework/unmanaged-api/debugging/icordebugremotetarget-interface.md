---
title: "Интерфейс ICorDebugRemoteTarget"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fcfdab2857745dee7c40823ad25592de5dc833ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="e9286-102">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="e9286-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="e9286-103">Предоставляет методы, позволяющие разработчикам отлаживать приложения на основе Silverlight в среде CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="e9286-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9286-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9286-104">Syntax</span></span>  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e9286-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e9286-105">Methods</span></span>  
  
|<span data-ttu-id="e9286-106">Метод</span><span class="sxs-lookup"><span data-stu-id="e9286-106">Method</span></span>|<span data-ttu-id="e9286-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="e9286-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9286-108">Метод ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="e9286-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="e9286-109">Возвращает имя узла или IP-адрес удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="e9286-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9286-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9286-110">Remarks</span></span>  
 <span data-ttu-id="e9286-111">Отладка в смешанном режиме (то есть управляемого и машинного кода) не поддерживается в Windows 95, Windows 98 или Windows ME или на платформах, отличных от x86 (например, IA-64 и AMD64).</span><span class="sxs-lookup"><span data-stu-id="e9286-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9286-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e9286-112">Requirements</span></span>  
 <span data-ttu-id="e9286-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9286-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9286-114">**Заголовок:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="e9286-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="e9286-115">**Библиотека:** : CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9286-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9286-116">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e9286-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9286-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e9286-117">See Also</span></span>  
 [<span data-ttu-id="e9286-118">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="e9286-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [<span data-ttu-id="e9286-119">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e9286-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="e9286-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e9286-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
