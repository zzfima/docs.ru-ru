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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44f220f12f72ca8d0be6a9fc50b363c9bccb85fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417593"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="54b34-102">Метод ICorDebugNativeFrame::GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="54b34-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="54b34-103">Возвращает значение аргумента или локальной переменной, из которых младшее слово и старшее слово хранятся в указанном регистре и расположение в памяти, соответственно, для данного кадра машинного кода.</span><span class="sxs-lookup"><span data-stu-id="54b34-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54b34-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54b34-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="54b34-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="54b34-106">[in] Объект `CORDB_ADDRESS` значение, указывающее расположение памяти, содержащего и слово высокой значения.</span><span class="sxs-lookup"><span data-stu-id="54b34-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="54b34-107">[in] Значение перечисления «CorDebugRegister», указывающее регистр, содержащего и слово низкого значения.</span><span class="sxs-lookup"><span data-stu-id="54b34-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="54b34-108">[in] Целое число, указывающее размер двоичную подпись метаданных которой ссылается `pvSigBlob` параметра.</span><span class="sxs-lookup"><span data-stu-id="54b34-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="54b34-109">[in] Объект `PCCOR_SIGNATURE` значение, которое указывает на двоичную подпись метаданных типа значения.</span><span class="sxs-lookup"><span data-stu-id="54b34-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="54b34-110">[out] Указатель на адрес объекта «ICorDebugValue», представляющий возвращенного значения, хранящиеся в указанном расположении регистр и памяти.</span><span class="sxs-lookup"><span data-stu-id="54b34-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54b34-111">Требования</span><span class="sxs-lookup"><span data-stu-id="54b34-111">Requirements</span></span>  
 <span data-ttu-id="54b34-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54b34-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54b34-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54b34-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54b34-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54b34-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54b34-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54b34-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b34-116">См. также</span><span class="sxs-lookup"><span data-stu-id="54b34-116">See Also</span></span>  
 
