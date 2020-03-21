---
title: Метод ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 3ac1f8ab98583357a3aa622b5032d9ae121ebdf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178920"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="b3f1a-102">Метод ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="b3f1a-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="b3f1a-103">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="b3f1a-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3f1a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3f1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3f1a-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="b3f1a-106">Значение [CORDB_ADDRESS,](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) представляющее адрес в модуле.</span><span class="sxs-lookup"><span data-stu-id="b3f1a-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="b3f1a-107">(ваут) [Значение CORDB_ADDRESS,](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="b3f1a-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="b3f1a-108">Указатель на размер модуля.</span><span class="sxs-lookup"><span data-stu-id="b3f1a-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3f1a-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3f1a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3f1a-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b3f1a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3f1a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b3f1a-111">Requirements</span></span>  
 <span data-ttu-id="b3f1a-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3f1a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f1a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3f1a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3f1a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3f1a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3f1a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f1a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f1a-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3f1a-116">See also</span></span>

- [<span data-ttu-id="b3f1a-117">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="b3f1a-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="b3f1a-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b3f1a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
