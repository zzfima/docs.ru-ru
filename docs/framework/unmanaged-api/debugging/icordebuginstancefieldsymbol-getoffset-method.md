---
title: 'Метод ICorDebugInstanceFieldSymbol:: методом offset'
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 3886e29a1c2fd44fbe50d1eef722f99da7abdbe5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139013"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="6fce3-102">Метод ICorDebugInstanceFieldSymbol:: методом offset</span><span class="sxs-lookup"><span data-stu-id="6fce3-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="6fce3-103">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="6fce3-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fce3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fce3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fce3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6fce3-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="6fce3-106">Указатель на число байтов, на которое это поле экземпляра смещается в своем родительском классе.</span><span class="sxs-lookup"><span data-stu-id="6fce3-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fce3-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="6fce3-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6fce3-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6fce3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fce3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6fce3-109">Requirements</span></span>  
 <span data-ttu-id="6fce3-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fce3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fce3-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fce3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fce3-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fce3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fce3-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fce3-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fce3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6fce3-114">See also</span></span>

- [<span data-ttu-id="6fce3-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="6fce3-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="6fce3-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6fce3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
