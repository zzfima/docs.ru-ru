---
title: Метод ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acb72a7d6c39efa5fa93bfddc314d07ec6cd8348
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419098"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="32593-102">Метод ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="32593-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="32593-103">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="32593-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32593-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32593-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32593-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32593-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="32593-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="32593-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32593-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="32593-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32593-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="32593-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32593-109">Требования</span><span class="sxs-lookup"><span data-stu-id="32593-109">Requirements</span></span>  
 <span data-ttu-id="32593-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32593-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32593-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32593-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32593-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32593-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32593-113">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32593-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32593-114">См. также</span><span class="sxs-lookup"><span data-stu-id="32593-114">See Also</span></span>  
 [<span data-ttu-id="32593-115">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="32593-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="32593-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="32593-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
