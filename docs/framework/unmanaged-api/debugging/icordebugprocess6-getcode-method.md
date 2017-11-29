---
title: "Метод ICorDebugProcess6::GetCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c69ce290a486960978ddaf87203328df4f392b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="bef8e-102">Метод ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="bef8e-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="bef8e-103">Получает информацию об управляемом коде по адресу определенного кода.</span><span class="sxs-lookup"><span data-stu-id="bef8e-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bef8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bef8e-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bef8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bef8e-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="bef8e-106">[in] Объект [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) значение, которое определяет начальный адрес сегмента управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bef8e-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="bef8e-107">[out] Указатель на адрес объекта «ICorDebugCode», представляющего сегмент управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bef8e-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bef8e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bef8e-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bef8e-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="bef8e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bef8e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bef8e-110">Requirements</span></span>  
 <span data-ttu-id="bef8e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bef8e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bef8e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bef8e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bef8e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bef8e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bef8e-114">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bef8e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef8e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bef8e-115">See Also</span></span>  
 [<span data-ttu-id="bef8e-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="bef8e-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="bef8e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bef8e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
