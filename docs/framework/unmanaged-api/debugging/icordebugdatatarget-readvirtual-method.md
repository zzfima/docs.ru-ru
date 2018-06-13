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
ms.openlocfilehash: 2d9e619e4176633074242521133d42f191f140ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412195"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="174c1-102">Метод ICorDebugDataTarget::ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="174c1-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="174c1-103">Получает блок непрерывной памяти, начиная с указанного адреса и возвращает его в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="174c1-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="174c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="174c1-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="174c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="174c1-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="174c1-106">[in] Начальный адрес запрошенный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="174c1-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="174c1-107">[out] Буфер, где будет храниться в памяти.</span><span class="sxs-lookup"><span data-stu-id="174c1-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="174c1-108">[in] Число байтов для получения из целевой адрес.</span><span class="sxs-lookup"><span data-stu-id="174c1-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="174c1-109">[out] Число фактически считанных байтов из целевой адрес.</span><span class="sxs-lookup"><span data-stu-id="174c1-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="174c1-110">Это может быть меньше, чем `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="174c1-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="174c1-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="174c1-111">Remarks</span></span>  
 <span data-ttu-id="174c1-112">Если можно прочитать первый байт (по указанному начальному адресу), вызов возвращает успешный результат (для поддержки эффективного чтения структур данных с самоописанием длину, например строки с завершающим нулем).</span><span class="sxs-lookup"><span data-stu-id="174c1-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="174c1-113">Требования</span><span class="sxs-lookup"><span data-stu-id="174c1-113">Requirements</span></span>  
 <span data-ttu-id="174c1-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="174c1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="174c1-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="174c1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="174c1-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="174c1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="174c1-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="174c1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174c1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="174c1-118">See Also</span></span>  
 [<span data-ttu-id="174c1-119">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="174c1-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="174c1-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="174c1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="174c1-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="174c1-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
