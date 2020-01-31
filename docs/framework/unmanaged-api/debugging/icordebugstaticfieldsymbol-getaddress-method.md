---
title: Метод ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: be4d59fe668026c4b40be4c6d0afcf718c8157bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791838"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="7a874-102">Метод ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="7a874-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="7a874-103">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="7a874-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a874-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a874-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a874-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7a874-105">Parameters</span></span>  
 <span data-ttu-id="7a874-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="7a874-106">pRVA</span></span>  
 <span data-ttu-id="7a874-107">[out] Указатель на относительный виртуальный адрес (RVA) статического поля.</span><span class="sxs-lookup"><span data-stu-id="7a874-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a874-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="7a874-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a874-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="7a874-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a874-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7a874-110">Requirements</span></span>  
 <span data-ttu-id="7a874-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a874-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a874-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a874-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a874-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a874-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a874-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a874-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a874-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a874-115">See also</span></span>

- [<span data-ttu-id="7a874-116">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="7a874-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="7a874-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7a874-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
