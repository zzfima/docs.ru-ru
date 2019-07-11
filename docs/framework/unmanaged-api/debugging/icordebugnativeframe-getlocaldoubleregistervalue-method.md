---
title: Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed7436ff73fa9cc19790859581930875f39e499e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746280"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="fbe07-102">Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="fbe07-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="fbe07-103">Получает значение аргумента или локальной переменной, которая хранится в двух заданных регистрах для данного кадра машинного кода.</span><span class="sxs-lookup"><span data-stu-id="fbe07-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbe07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbe07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbe07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbe07-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="fbe07-106">[in] Значение, указывающее регистр, содержащий старшее слово значение перечисления «CorDebugRegister».</span><span class="sxs-lookup"><span data-stu-id="fbe07-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="fbe07-107">[in] Значение `CorDebugRegister` перечисление, указывающее регистр, содержащий значение младшее слово.</span><span class="sxs-lookup"><span data-stu-id="fbe07-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="fbe07-108">[in] Целое число, указывающее размер двоичную подпись метаданных которого ссылается `pvSigBlob` параметра.</span><span class="sxs-lookup"><span data-stu-id="fbe07-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="fbe07-109">[in] Объект `PCCOR_SIGNATURE` значение, которое указывает на двоичную подпись метаданных типа значения.</span><span class="sxs-lookup"><span data-stu-id="fbe07-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="fbe07-110">[out] Указатель на адрес объекта «ICorDebugValue», представляющего извлеченное значение, которое хранится в регистрах, указанного.</span><span class="sxs-lookup"><span data-stu-id="fbe07-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbe07-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fbe07-111">Remarks</span></span>  
 <span data-ttu-id="fbe07-112">`GetLocalDoubleRegisterValue` Метод может использоваться в кадре машинного кода или just-in-time (JIT)-компиляции кадра.</span><span class="sxs-lookup"><span data-stu-id="fbe07-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbe07-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fbe07-113">Requirements</span></span>  
 <span data-ttu-id="fbe07-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbe07-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbe07-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbe07-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbe07-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbe07-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbe07-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbe07-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbe07-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fbe07-118">See also</span></span>
