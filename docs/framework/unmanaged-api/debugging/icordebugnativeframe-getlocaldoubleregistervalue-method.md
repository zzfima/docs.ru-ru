---
title: "Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75b8c4d5551c9624852f1e0f730d1215236608de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="286d6-102">Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="286d6-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="286d6-103">Возвращает значение аргумента или локальной переменной, которая хранится в двух заданных регистрах этого кадра машинного кода.</span><span class="sxs-lookup"><span data-stu-id="286d6-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="286d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="286d6-104">Syntax</span></span>  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="286d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="286d6-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="286d6-106">[in] Значение, указывающее регистр, содержащего и слово высокой значения перечисления «CorDebugRegister».</span><span class="sxs-lookup"><span data-stu-id="286d6-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="286d6-107">[in] Значение `CorDebugRegister` перечисление, указывающее регистр, содержащего и слово низкого значения.</span><span class="sxs-lookup"><span data-stu-id="286d6-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="286d6-108">[in] Целое число, указывающее размер двоичную подпись метаданных которой ссылается `pvSigBlob` параметра.</span><span class="sxs-lookup"><span data-stu-id="286d6-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="286d6-109">[in] Объект `PCCOR_SIGNATURE` значение, которое указывает на двоичную подпись метаданных типа значения.</span><span class="sxs-lookup"><span data-stu-id="286d6-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="286d6-110">[out] Указатель на адрес объекта «ICorDebugValue», представляющий возвращенного значения, которые хранятся в регистрах, указанного.</span><span class="sxs-lookup"><span data-stu-id="286d6-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="286d6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="286d6-111">Remarks</span></span>  
 <span data-ttu-id="286d6-112">`GetLocalDoubleRegisterValue` Метод может использоваться в фрейм машинного кода или just-in-time (JIT)-компиляции кадра.</span><span class="sxs-lookup"><span data-stu-id="286d6-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="286d6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="286d6-113">Requirements</span></span>  
 <span data-ttu-id="286d6-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="286d6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="286d6-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="286d6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="286d6-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="286d6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="286d6-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="286d6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="286d6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="286d6-118">See Also</span></span>  
 
