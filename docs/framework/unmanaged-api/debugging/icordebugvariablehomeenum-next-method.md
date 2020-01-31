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
ms.openlocfilehash: 2bb6fee00bb99555bc19f35e1250880cc3985f7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790927"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="3c23d-102">Метод ICorDebugVariableHomeEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="3c23d-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="3c23d-103">Возвращает указанное число экземпляров [ICorDebugVariableHome](icordebugvariablehome-interface.md) , содержащих сведения о локальных переменных и аргументах в функции.</span><span class="sxs-lookup"><span data-stu-id="3c23d-103">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c23d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c23d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c23d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c23d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3c23d-106">[in] Количество объектов, которые должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="3c23d-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="3c23d-107">Массив указателей, каждый из которых указывает на объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) , предоставляющий сведения о локальной переменной или аргументе функции.</span><span class="sxs-lookup"><span data-stu-id="3c23d-107">An array of pointers, each of which points to a [ICorDebugVariableHome](icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3c23d-108">заполняет Число экземпляров, фактически возвращаемых в объектах.</span><span class="sxs-lookup"><span data-stu-id="3c23d-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c23d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c23d-109">Return Value</span></span>  
 <span data-ttu-id="3c23d-110">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="3c23d-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="3c23d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c23d-111">HRESULT</span></span>|<span data-ttu-id="3c23d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3c23d-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3c23d-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="3c23d-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3c23d-114">Фактическое число полученных экземпляров, как отражается в `pceltFetched`, меньше, чем количество запрошенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="3c23d-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c23d-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="3c23d-115">Remarks</span></span>  
 <span data-ttu-id="3c23d-116">Метод [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) извлекает не более `celt` объектов, начиная с текущей позиции перечислителя.</span><span class="sxs-lookup"><span data-stu-id="3c23d-116">The [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="3c23d-117">Когда метод возвращает значение, `pceltFetched` содержит фактическое число извлеченных объектов.</span><span class="sxs-lookup"><span data-stu-id="3c23d-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c23d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3c23d-118">Requirements</span></span>  
 <span data-ttu-id="3c23d-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c23d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c23d-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c23d-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c23d-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c23d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c23d-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c23d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c23d-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c23d-123">See also</span></span>

- [<span data-ttu-id="3c23d-124">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="3c23d-124">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="3c23d-125">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="3c23d-125">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
