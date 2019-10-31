---
title: Метод ICorDebugNativeFrame::GetLocalMemoryRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
ms.openlocfilehash: 788ce2d47769caa72518e0357a0affdff5862699
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137284"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="5729e-102">Метод ICorDebugNativeFrame::GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="5729e-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="5729e-103">Возвращает значение аргумента или локальной переменной, из которых младшее слово и верхнее слово хранятся в указанном регистре и расположении в памяти соответственно для этого кадра машинного кода.</span><span class="sxs-lookup"><span data-stu-id="5729e-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5729e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5729e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5729e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5729e-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="5729e-106">окне Значение `CORDB_ADDRESS`, указывающее место в памяти, содержащее старшее слово значения.</span><span class="sxs-lookup"><span data-stu-id="5729e-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="5729e-107">окне Значение перечисления "CorDebugRegister", указывающее регистр, содержащий нижнее слово значения.</span><span class="sxs-lookup"><span data-stu-id="5729e-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="5729e-108">окне Целое число, указывающее размер подписи двоичных метаданных, на которую ссылается параметр `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="5729e-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5729e-109">окне Значение `PCCOR_SIGNATURE`, которое указывает на сигнатуру двоичных метаданных для типа значения.</span><span class="sxs-lookup"><span data-stu-id="5729e-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="5729e-110">заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение, хранящееся в указанном регистре и расположении в памяти.</span><span class="sxs-lookup"><span data-stu-id="5729e-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5729e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5729e-111">Requirements</span></span>  
 <span data-ttu-id="5729e-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5729e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5729e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5729e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5729e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5729e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5729e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5729e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5729e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5729e-116">See also</span></span>
