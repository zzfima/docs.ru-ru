---
title: Метод ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ff0ddc266ef9a3f5fabf56f43f1eba2c74e3a8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910172"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="84983-102">Метод ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="84983-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="84983-103">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="84983-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84983-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84983-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84983-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84983-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="84983-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="84983-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84983-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="84983-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84983-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="84983-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84983-109">Требования</span><span class="sxs-lookup"><span data-stu-id="84983-109">Requirements</span></span>  
 <span data-ttu-id="84983-110">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84983-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84983-111">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="84983-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84983-112">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="84983-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84983-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84983-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84983-114">См. также</span><span class="sxs-lookup"><span data-stu-id="84983-114">See also</span></span>

- [<span data-ttu-id="84983-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="84983-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="84983-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="84983-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
