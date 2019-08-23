---
title: Метод ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d41b99d7410333cb6a22443271c1fcbc41c3594
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962701"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="6ecc7-102">Метод ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="6ecc7-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="6ecc7-103">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ecc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ecc7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ecc7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6ecc7-105">Parameters</span></span>  
 <span data-ttu-id="6ecc7-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="6ecc7-106">pRVA</span></span>  
 <span data-ttu-id="6ecc7-107">[out] Указатель на относительный виртуальный адрес (RVA) статического поля.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ecc7-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ecc7-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ecc7-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ecc7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6ecc7-110">Requirements</span></span>  
 <span data-ttu-id="6ecc7-111">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ecc7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ecc7-112">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6ecc7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ecc7-113">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="6ecc7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ecc7-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ecc7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecc7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6ecc7-115">See also</span></span>

- [<span data-ttu-id="6ecc7-116">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="6ecc7-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="6ecc7-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6ecc7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
