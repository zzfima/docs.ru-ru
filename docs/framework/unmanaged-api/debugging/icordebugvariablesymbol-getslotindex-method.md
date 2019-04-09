---
title: Метод ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: affe67006c9e37d55b0f9d107c92441da44c9ab8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138798"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="8c99e-102">Метод ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="8c99e-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="8c99e-103">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="8c99e-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c99e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c99e-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c99e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c99e-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="8c99e-106">[выходной] Указатель на индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="8c99e-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c99e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c99e-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="8c99e-108">При успешном выполнении.</span><span class="sxs-lookup"><span data-stu-id="8c99e-108">if successful.</span></span> `E_FAIL` <span data-ttu-id="8c99e-109">Если переменная является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="8c99e-109">if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c99e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c99e-110">Remarks</span></span>  
 <span data-ttu-id="8c99e-111">Управляемый индекс слота можно использовать для получения информации о метаданных переменной.</span><span class="sxs-lookup"><span data-stu-id="8c99e-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c99e-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8c99e-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c99e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8c99e-113">Requirements</span></span>  
 <span data-ttu-id="8c99e-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c99e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c99e-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c99e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c99e-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c99e-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8c99e-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8c99e-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c99e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8c99e-118">See also</span></span>

- [<span data-ttu-id="8c99e-119">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="8c99e-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="8c99e-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c99e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
