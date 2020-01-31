---
title: Метод ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: deeb887dad38417e3ebb980f5ef2f89392388d65
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791818"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="e5162-102">Метод ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="e5162-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="e5162-103">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="e5162-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5162-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5162-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5162-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5162-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="e5162-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="e5162-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5162-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="e5162-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5162-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e5162-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5162-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e5162-109">Requirements</span></span>  
 <span data-ttu-id="e5162-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5162-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5162-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5162-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5162-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5162-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5162-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5162-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5162-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5162-114">See also</span></span>

- [<span data-ttu-id="e5162-115">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e5162-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="e5162-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e5162-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
