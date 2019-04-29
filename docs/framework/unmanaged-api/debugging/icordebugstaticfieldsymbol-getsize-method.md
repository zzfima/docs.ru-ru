---
title: Метод ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9baa3632b6ede9ce45f34302611710344ed33761
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782607"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="f5a6e-102">Метод ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="f5a6e-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="f5a6e-103">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="f5a6e-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5a6e-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a6e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5a6e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="f5a6e-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="f5a6e-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5a6e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5a6e-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5a6e-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f5a6e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a6e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f5a6e-109">Requirements</span></span>  
 <span data-ttu-id="f5a6e-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a6e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a6e-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5a6e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5a6e-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a6e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a6e-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a6e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a6e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f5a6e-114">See also</span></span>

- [<span data-ttu-id="f5a6e-115">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="f5a6e-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="f5a6e-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f5a6e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
