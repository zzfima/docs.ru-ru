---
title: Метод ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d23bf14fbb3d75534ac2d4a43eca0fbf3e994ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946423"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="c4f90-102">Метод ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="c4f90-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="c4f90-103">Получает имя поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c4f90-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4f90-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4f90-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4f90-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="c4f90-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="c4f90-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c4f90-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="c4f90-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="c4f90-108">[out] Массив символов, в котором хранится возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="c4f90-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4f90-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4f90-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4f90-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c4f90-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4f90-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c4f90-111">Requirements</span></span>  
 <span data-ttu-id="c4f90-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4f90-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4f90-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4f90-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4f90-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4f90-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4f90-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4f90-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f90-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c4f90-116">See also</span></span>

- [<span data-ttu-id="c4f90-117">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="c4f90-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="c4f90-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c4f90-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
