---
title: 'Метод Икордебугстатикфиелдсимбол:: метода Address'
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 65761e48491b2a4c81ccd05b17d8723f71f52e5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131800"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="0028c-102">Метод Икордебугстатикфиелдсимбол:: метода Address</span><span class="sxs-lookup"><span data-stu-id="0028c-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="0028c-103">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="0028c-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0028c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0028c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0028c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0028c-105">Parameters</span></span>  
 <span data-ttu-id="0028c-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="0028c-106">pRVA</span></span>  
 <span data-ttu-id="0028c-107">[out] Указатель на относительный виртуальный адрес (RVA) статического поля.</span><span class="sxs-lookup"><span data-stu-id="0028c-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0028c-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="0028c-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0028c-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0028c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0028c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0028c-110">Requirements</span></span>  
 <span data-ttu-id="0028c-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0028c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0028c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0028c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0028c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0028c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0028c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0028c-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0028c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0028c-115">See also</span></span>

- [<span data-ttu-id="0028c-116">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="0028c-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="0028c-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0028c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
