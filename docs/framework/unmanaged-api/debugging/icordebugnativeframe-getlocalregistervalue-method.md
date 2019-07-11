---
title: Метод ICorDebugNativeFrame::GetLocalRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d287305934c7884d5474935e50de3d26e225975
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746161"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="cd6bd-102">Метод ICorDebugNativeFrame::GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="cd6bd-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="cd6bd-103">Получает значение аргумента или локальной переменной, которая хранится в регистре, заданном для данного кадра машинного кода.</span><span class="sxs-lookup"><span data-stu-id="cd6bd-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd6bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd6bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd6bd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd6bd-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="cd6bd-106">[in] Значение, указывающее регистр, содержащий значение перечисления «CorDebugRegister».</span><span class="sxs-lookup"><span data-stu-id="cd6bd-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="cd6bd-107">[in] Целое число, указывающее размер двоичную подпись метаданных которого ссылается `pvSigBlob` параметра.</span><span class="sxs-lookup"><span data-stu-id="cd6bd-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="cd6bd-108">[in] Объект `PCCOR_SIGNATURE` значение, которое указывает на двоичную подпись метаданных типа значения.</span><span class="sxs-lookup"><span data-stu-id="cd6bd-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="cd6bd-109">[out] Указатель на адрес объекта «ICorDebugValue», представляющего извлеченное значение, которое хранится в указанном регистре.</span><span class="sxs-lookup"><span data-stu-id="cd6bd-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd6bd-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd6bd-110">Remarks</span></span>  
 <span data-ttu-id="cd6bd-111">`GetLocalRegisterValue` Метод может использоваться в кадре машинного кода или just-in-time (JIT)-компиляции кадра.</span><span class="sxs-lookup"><span data-stu-id="cd6bd-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd6bd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="cd6bd-112">Requirements</span></span>  
 <span data-ttu-id="cd6bd-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd6bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd6bd-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd6bd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd6bd-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd6bd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd6bd-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd6bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd6bd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cd6bd-117">See also</span></span>
