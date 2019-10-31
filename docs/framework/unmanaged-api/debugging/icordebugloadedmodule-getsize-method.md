---
title: Метод ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 3f2f8a1721847b8f7b845c42aa3c91e032c2d474
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122634"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="a2ac8-102">Метод ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="a2ac8-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="a2ac8-103">Возвращает размер в байтах загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ac8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2ac8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2ac8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2ac8-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="a2ac8-106">[out] Указатель на число байтов в загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2ac8-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="a2ac8-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2ac8-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2ac8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a2ac8-109">Requirements</span></span>  
 <span data-ttu-id="a2ac8-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2ac8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2ac8-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2ac8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2ac8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2ac8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2ac8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2ac8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ac8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a2ac8-114">See also</span></span>

- [<span data-ttu-id="a2ac8-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="a2ac8-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="a2ac8-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a2ac8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
