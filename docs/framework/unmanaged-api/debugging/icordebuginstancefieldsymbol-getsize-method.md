---
title: Метод ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: eb70c441441954e2ffce6ca832c58369c606b128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782282"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="39913-102">Метод ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="39913-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="39913-103">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="39913-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39913-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39913-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39913-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="39913-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="39913-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="39913-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39913-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="39913-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39913-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="39913-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39913-109">Требования</span><span class="sxs-lookup"><span data-stu-id="39913-109">Requirements</span></span>  
 <span data-ttu-id="39913-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39913-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39913-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39913-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39913-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39913-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39913-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39913-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39913-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="39913-114">See also</span></span>

- [<span data-ttu-id="39913-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="39913-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="39913-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="39913-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
