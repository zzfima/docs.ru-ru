---
title: 'Метод ICorDebugVariableHomeEnum:: Next'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 9c2c16789fb61099c9b7c58154810739d225af1f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121925"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="078f3-102">Метод ICorDebugVariableHomeEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="078f3-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="078f3-103">Возвращает указанное число экземпляров [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) , содержащих сведения о локальных переменных и аргументах в функции.</span><span class="sxs-lookup"><span data-stu-id="078f3-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="078f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="078f3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="078f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="078f3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="078f3-106">[in] Количество объектов, которые должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="078f3-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="078f3-107">Массив указателей, каждый из которых указывает на объект [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) , предоставляющий сведения о локальной переменной или аргументе функции.</span><span class="sxs-lookup"><span data-stu-id="078f3-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="078f3-108">заполняет Число экземпляров, фактически возвращаемых в объектах.</span><span class="sxs-lookup"><span data-stu-id="078f3-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="078f3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="078f3-109">Return Value</span></span>  
 <span data-ttu-id="078f3-110">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="078f3-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="078f3-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="078f3-111">HRESULT</span></span>|<span data-ttu-id="078f3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="078f3-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="078f3-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="078f3-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="078f3-114">Фактическое число полученных экземпляров, как отражается в `pceltFetched`, меньше, чем количество запрошенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="078f3-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="078f3-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="078f3-115">Remarks</span></span>  
 <span data-ttu-id="078f3-116">Метод [ICorDebugVariableHomeEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) извлекает не более `celt` объектов, начиная с текущей позиции перечислителя.</span><span class="sxs-lookup"><span data-stu-id="078f3-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="078f3-117">Когда метод возвращает значение, `pceltFetched` содержит фактическое число извлеченных объектов.</span><span class="sxs-lookup"><span data-stu-id="078f3-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="078f3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="078f3-118">Requirements</span></span>  
 <span data-ttu-id="078f3-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="078f3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="078f3-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="078f3-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="078f3-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="078f3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="078f3-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="078f3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="078f3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="078f3-123">See also</span></span>

- [<span data-ttu-id="078f3-124">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="078f3-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="078f3-125">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="078f3-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
