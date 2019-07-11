---
title: Метод ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 810590f0d1f7f74b778d73d98a9f7f9b1988b75f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736438"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="efa15-102">Метод ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="efa15-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="efa15-103">Получает информацию об управляемом коде по адресу определенного кода.</span><span class="sxs-lookup"><span data-stu-id="efa15-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efa15-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efa15-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efa15-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="efa15-106">[in] Объект [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) значение, указывающее начальный адрес сегмента управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="efa15-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="efa15-107">[out] Указатель на адрес объекта «ICorDebugCode», представляющего сегмент управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="efa15-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efa15-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="efa15-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efa15-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="efa15-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efa15-110">Требования</span><span class="sxs-lookup"><span data-stu-id="efa15-110">Requirements</span></span>  
 <span data-ttu-id="efa15-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efa15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa15-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efa15-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efa15-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efa15-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efa15-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efa15-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa15-115">См. также</span><span class="sxs-lookup"><span data-stu-id="efa15-115">See also</span></span>

- [<span data-ttu-id="efa15-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="efa15-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="efa15-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="efa15-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
