---
title: Метод ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2371072261c9c75436ab86d742ce75423587765
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969444"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="52ff5-102">Метод ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="52ff5-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="52ff5-103">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="52ff5-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ff5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52ff5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52ff5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52ff5-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="52ff5-106">Значение [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) , представляющее адрес в модуле.</span><span class="sxs-lookup"><span data-stu-id="52ff5-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="52ff5-107">заполняет Значение [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="52ff5-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="52ff5-108">Указатель на размер модуля.</span><span class="sxs-lookup"><span data-stu-id="52ff5-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52ff5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="52ff5-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52ff5-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="52ff5-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52ff5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="52ff5-111">Requirements</span></span>  
 <span data-ttu-id="52ff5-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52ff5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52ff5-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="52ff5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52ff5-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="52ff5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52ff5-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52ff5-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ff5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="52ff5-116">See also</span></span>

- [<span data-ttu-id="52ff5-117">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="52ff5-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="52ff5-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="52ff5-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
