---
title: Метод ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffcd6971a3229423f055765b0d64258a2dfa2aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477950"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="0c37d-102">Метод ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="0c37d-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="0c37d-103">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="0c37d-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c37d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c37d-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c37d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c37d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0c37d-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="0c37d-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0c37d-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="0c37d-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="0c37d-108">[out] Массив символов, в котором хранится возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="0c37d-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c37d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c37d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c37d-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0c37d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c37d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0c37d-111">Requirements</span></span>  
 <span data-ttu-id="0c37d-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c37d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c37d-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c37d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c37d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c37d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c37d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c37d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c37d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0c37d-116">See also</span></span>
- [<span data-ttu-id="0c37d-117">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="0c37d-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="0c37d-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0c37d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
