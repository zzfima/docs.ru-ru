---
title: Метод ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3067cdee1d3a5df0ad5594bce581139431fd1846
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936878"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="f6918-102">Метод ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="f6918-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="f6918-103">Возвращает размер в байтах загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="f6918-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6918-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6918-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6918-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6918-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="f6918-106">[out] Указатель на число байтов в загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="f6918-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6918-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6918-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6918-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f6918-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6918-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f6918-109">Requirements</span></span>  
 <span data-ttu-id="f6918-110">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6918-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6918-111">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f6918-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6918-112">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f6918-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6918-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6918-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6918-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f6918-114">See also</span></span>

- [<span data-ttu-id="f6918-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="f6918-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="f6918-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f6918-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
