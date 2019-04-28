---
title: Метод ICorDebugDataTarget::ReadVirtual
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4749bfee22e58ad7c3ca29ec992da88493ca2c5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763845"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="fe8ac-102">Метод ICorDebugDataTarget::ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="fe8ac-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="fe8ac-103">Получает блок непрерывной памяти, начиная с указанного адреса и возвращает его в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="fe8ac-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe8ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe8ac-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe8ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe8ac-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="fe8ac-106">[in] Начальный адрес требуемым объемом свободной памяти.</span><span class="sxs-lookup"><span data-stu-id="fe8ac-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="fe8ac-107">[out] Буфер, где будет храниться память.</span><span class="sxs-lookup"><span data-stu-id="fe8ac-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="fe8ac-108">[in] Число байтов для получения из целевой адрес.</span><span class="sxs-lookup"><span data-stu-id="fe8ac-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="fe8ac-109">[out] Число байтов, фактически считанных из целевой адрес.</span><span class="sxs-lookup"><span data-stu-id="fe8ac-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="fe8ac-110">Это может быть меньше, чем `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="fe8ac-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe8ac-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe8ac-111">Remarks</span></span>  
 <span data-ttu-id="fe8ac-112">Если первый байт (по адресу указанной начальной) могут считываться, вызов возвращает успех (для поддержки эффективного чтения структур данных с самоописанием длины, например, строки с завершающим нулем).</span><span class="sxs-lookup"><span data-stu-id="fe8ac-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe8ac-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fe8ac-113">Requirements</span></span>  
 <span data-ttu-id="fe8ac-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe8ac-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe8ac-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe8ac-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe8ac-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe8ac-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe8ac-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe8ac-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8ac-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fe8ac-118">See also</span></span>

- [<span data-ttu-id="fe8ac-119">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="fe8ac-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="fe8ac-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fe8ac-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fe8ac-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="fe8ac-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
