---
title: Интерфейс ICorDebugRemoteTarget
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a595438c53a88fcfb06960c8b7cb6ec8949cfa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="22c37-102">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="22c37-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="22c37-103">Предоставляет методы, позволяющие разработчикам отлаживать приложения на основе Silverlight в среде CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="22c37-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c37-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22c37-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="22c37-105">Методы</span><span class="sxs-lookup"><span data-stu-id="22c37-105">Methods</span></span>  
  
|<span data-ttu-id="22c37-106">Метод</span><span class="sxs-lookup"><span data-stu-id="22c37-106">Method</span></span>|<span data-ttu-id="22c37-107">Описание</span><span class="sxs-lookup"><span data-stu-id="22c37-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22c37-108">Метод ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="22c37-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="22c37-109">Возвращает имя узла или IP-адрес удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="22c37-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22c37-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="22c37-110">Remarks</span></span>  
 <span data-ttu-id="22c37-111">Отладка в смешанном режиме (то есть управляемого и машинного кода) не поддерживается в Windows 95, Windows 98 или Windows ME или на платформах, отличных от x86 (например, IA-64 и AMD64).</span><span class="sxs-lookup"><span data-stu-id="22c37-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22c37-112">Требования</span><span class="sxs-lookup"><span data-stu-id="22c37-112">Requirements</span></span>  
 <span data-ttu-id="22c37-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22c37-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22c37-114">**Заголовок:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="22c37-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="22c37-115">**Библиотека:** : CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22c37-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="22c37-116">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="22c37-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c37-117">См. также</span><span class="sxs-lookup"><span data-stu-id="22c37-117">See Also</span></span>  
 [<span data-ttu-id="22c37-118">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="22c37-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [<span data-ttu-id="22c37-119">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="22c37-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="22c37-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="22c37-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
