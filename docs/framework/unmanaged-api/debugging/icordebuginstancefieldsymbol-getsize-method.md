---
title: Метод ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081454"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="d9cab-102">Метод ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="d9cab-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="d9cab-103">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="d9cab-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9cab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9cab-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9cab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9cab-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="d9cab-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="d9cab-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9cab-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9cab-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9cab-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d9cab-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9cab-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d9cab-109">Requirements</span></span>  
 <span data-ttu-id="d9cab-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9cab-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9cab-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9cab-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9cab-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9cab-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d9cab-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d9cab-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9cab-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d9cab-114">See also</span></span>

- [<span data-ttu-id="d9cab-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="d9cab-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="d9cab-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d9cab-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
