---
title: Метод ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 94882c67752705f9f13b858ae3b386a19dc103a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178559"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="8c8c8-102">Метод ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="8c8c8-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="8c8c8-103">Получает информацию об управляемом коде по адресу определенного кода.</span><span class="sxs-lookup"><span data-stu-id="8c8c8-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c8c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c8c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c8c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c8c8-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="8c8c8-106">(в) Значение [CORDB_ADDRESS,](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) окоторомявающие начальный адрес управляемого сегмента кода.</span><span class="sxs-lookup"><span data-stu-id="8c8c8-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="8c8c8-107">(ваут) Указатель на адрес объекта "ICorDebugCode", представляющий сегмент управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8c8c8-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c8c8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c8c8-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c8c8-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8c8c8-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c8c8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8c8c8-110">Requirements</span></span>  
 <span data-ttu-id="8c8c8-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c8c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c8c8-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c8c8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c8c8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c8c8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c8c8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c8c8-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8c8-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8c8c8-115">See also</span></span>

- [<span data-ttu-id="8c8c8-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="8c8c8-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="8c8c8-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c8c8-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
