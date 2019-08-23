---
title: Метод ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d99e06c1093dbc67e9c1999e4b9ccabd6579340e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962666"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="a8bb7-102">Метод ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="a8bb7-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="a8bb7-103">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="a8bb7-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bb7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8bb7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8bb7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8bb7-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="a8bb7-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="a8bb7-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8bb7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8bb7-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8bb7-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a8bb7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8bb7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a8bb7-109">Requirements</span></span>  
 <span data-ttu-id="a8bb7-110">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8bb7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8bb7-111">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a8bb7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8bb7-112">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="a8bb7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8bb7-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8bb7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bb7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a8bb7-114">See also</span></span>

- [<span data-ttu-id="a8bb7-115">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a8bb7-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="a8bb7-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a8bb7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
