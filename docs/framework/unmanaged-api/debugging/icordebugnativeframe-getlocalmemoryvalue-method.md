---
title: Метод ICorDebugNativeFrame::GetLocalMemoryValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
ms.openlocfilehash: cee095003c136142052b8f946fa8227927c80ee2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096871"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="d3b56-102">Метод ICorDebugNativeFrame::GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="d3b56-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="d3b56-103">Возвращает значение аргумента или локальной переменной, которая хранится в указанном месте в памяти для этого машинного кадра.</span><span class="sxs-lookup"><span data-stu-id="d3b56-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b56-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3b56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3b56-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3b56-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d3b56-106">окне Значение `CORDB_ADDRESS`, указывающее место в памяти, содержащее значение.</span><span class="sxs-lookup"><span data-stu-id="d3b56-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d3b56-107">окне Целое число, указывающее размер подписи двоичных метаданных, на которую ссылается параметр `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="d3b56-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d3b56-108">окне Значение `PCCOR_SIGNATURE`, которое указывает на сигнатуру двоичных метаданных для типа значения.</span><span class="sxs-lookup"><span data-stu-id="d3b56-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d3b56-109">заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение, хранящееся в указанном расположении в памяти.</span><span class="sxs-lookup"><span data-stu-id="d3b56-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3b56-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d3b56-110">Requirements</span></span>  
 <span data-ttu-id="d3b56-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3b56-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3b56-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3b56-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3b56-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3b56-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3b56-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3b56-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b56-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d3b56-115">See also</span></span>
