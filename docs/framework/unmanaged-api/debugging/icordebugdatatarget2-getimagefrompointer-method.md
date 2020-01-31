---
title: Метод ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 55c87731399cf1e7a6747720b8bb33de7e01906c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788834"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="52b81-102">Метод ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="52b81-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="52b81-103">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="52b81-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52b81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52b81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52b81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52b81-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="52b81-106">Значение [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) , представляющее адрес в модуле.</span><span class="sxs-lookup"><span data-stu-id="52b81-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="52b81-107">заполняет Значение [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="52b81-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="52b81-108">Указатель на размер модуля.</span><span class="sxs-lookup"><span data-stu-id="52b81-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52b81-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="52b81-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52b81-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="52b81-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52b81-111">Требования</span><span class="sxs-lookup"><span data-stu-id="52b81-111">Requirements</span></span>  
 <span data-ttu-id="52b81-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52b81-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52b81-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52b81-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52b81-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52b81-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52b81-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52b81-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b81-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="52b81-116">See also</span></span>

- [<span data-ttu-id="52b81-117">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="52b81-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="52b81-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="52b81-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
