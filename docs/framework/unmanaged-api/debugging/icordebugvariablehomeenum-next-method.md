---
title: "Метод ICorDebugVariableHomeEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHomeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bab158cbbe2eaf6e52ae0df6a0eed86d3d0b8ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="77db1-102">Метод ICorDebugVariableHomeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="77db1-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="77db1-103">Возвращает заданное число [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляров, которые содержат сведения о локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="77db1-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77db1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77db1-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77db1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77db1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="77db1-106">[in] Количество объектов, которые должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="77db1-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="77db1-107">Массив указателей, каждый из которых указывает на [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объект, предоставляющий сведения о локальной переменной или аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="77db1-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="77db1-108">[out] Количество экземпляров, фактически извлеченных в объекты.</span><span class="sxs-lookup"><span data-stu-id="77db1-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77db1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="77db1-109">Return Value</span></span>  
 <span data-ttu-id="77db1-110">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="77db1-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="77db1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77db1-111">HRESULT</span></span>|<span data-ttu-id="77db1-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="77db1-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="77db1-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="77db1-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="77db1-114">Получить фактическое количество экземпляров, как отражено в `pceltFetched`, меньше, чем количество экземпляров, запрошенных.</span><span class="sxs-lookup"><span data-stu-id="77db1-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77db1-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="77db1-115">Remarks</span></span>  
 <span data-ttu-id="77db1-116">[ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) метод позволяет получить более `celt` объектов, начиная с текущей позиции перечислителя.</span><span class="sxs-lookup"><span data-stu-id="77db1-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="77db1-117">При возвращении метода `pceltFetched` содержит фактическое число объектов, полученных.</span><span class="sxs-lookup"><span data-stu-id="77db1-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77db1-118">Требования</span><span class="sxs-lookup"><span data-stu-id="77db1-118">Requirements</span></span>  
 <span data-ttu-id="77db1-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77db1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77db1-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77db1-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77db1-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77db1-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77db1-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77db1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77db1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="77db1-123">See Also</span></span>  
 [<span data-ttu-id="77db1-124">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="77db1-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 [<span data-ttu-id="77db1-125">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="77db1-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
