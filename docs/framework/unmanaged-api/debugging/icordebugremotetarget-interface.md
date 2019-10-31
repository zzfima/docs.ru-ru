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
ms.openlocfilehash: 97c4e6d3c9de7dcb8d399a956a4a58c49ca6e3b9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131871"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="a1c02-102">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="a1c02-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="a1c02-103">Предоставляет методы, позволяющие разработчикам выполнять отладку приложений на основе Silverlight в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="a1c02-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c02-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1c02-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="a1c02-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a1c02-105">Methods</span></span>  
  
|<span data-ttu-id="a1c02-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a1c02-106">Method</span></span>|<span data-ttu-id="a1c02-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a1c02-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1c02-108">Метод ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="a1c02-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="a1c02-109">Возвращает имя узла или IP-адрес удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="a1c02-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1c02-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="a1c02-110">Remarks</span></span>  
 <span data-ttu-id="a1c02-111">Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME, а также на платформах, отличных от x86 (например, IA-64 и AMD64).</span><span class="sxs-lookup"><span data-stu-id="a1c02-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1c02-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a1c02-112">Requirements</span></span>  
 <span data-ttu-id="a1c02-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1c02-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1c02-114">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="a1c02-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a1c02-115">**Библиотека:** : коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="a1c02-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1c02-116">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a1c02-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c02-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a1c02-117">See also</span></span>

- [<span data-ttu-id="a1c02-118">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="a1c02-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="a1c02-119">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a1c02-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="a1c02-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a1c02-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
