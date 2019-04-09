---
title: Метод ICorDebugMutableDataTarget::WriteVirtual
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fba970de6e5882d3cbe9be17b5b49be5a3e81aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171656"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="f16f1-102">Метод ICorDebugMutableDataTarget::WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="f16f1-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="f16f1-103">Записывает память в адресное пространство целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="f16f1-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f16f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f16f1-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f16f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f16f1-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="f16f1-106">[in] Адрес для записи содержимого `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="f16f1-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="f16f1-107">[в] Указатель на массив байтов, содержащий байты для записи.</span><span class="sxs-lookup"><span data-stu-id="f16f1-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="f16f1-108">[in] Количество байтов в `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="f16f1-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f16f1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f16f1-109">Return Value</span></span>  
 `S_OK` <span data-ttu-id="f16f1-110">в случае успеха или любой другой `HRESULT` в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="f16f1-110">on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f16f1-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f16f1-111">Remarks</span></span>  
 <span data-ttu-id="f16f1-112">Если не удается записать все байты, вызов метода завершается ошибкой без изменения каких-либо байтов в целевом адресном пространстве.</span><span class="sxs-lookup"><span data-stu-id="f16f1-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="f16f1-113">(В противном случае целевое адресное пространство оказалось бы в несогласованном состоянии, что сделало бы ненадежной дальнейшую отладку.)</span><span class="sxs-lookup"><span data-stu-id="f16f1-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f16f1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f16f1-114">Requirements</span></span>  
 <span data-ttu-id="f16f1-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f16f1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f16f1-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f16f1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f16f1-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f16f1-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f16f1-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f16f1-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f16f1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f16f1-119">See also</span></span>

- [<span data-ttu-id="f16f1-120">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="f16f1-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="f16f1-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f16f1-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
