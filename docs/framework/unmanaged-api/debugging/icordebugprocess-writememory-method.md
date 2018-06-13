---
title: Метод ICorDebugProcess::WriteMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6da4c282c7f969a406a657d1e30dd6120a32b4e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420912"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="3de2a-102">Метод ICorDebugProcess::WriteMemory</span><span class="sxs-lookup"><span data-stu-id="3de2a-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="3de2a-103">Записывает данные в область памяти в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="3de2a-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3de2a-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3de2a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3de2a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="3de2a-106">[in] Объект `CORDB_ADDRESS` записывается значение, базовый адрес области памяти для данных.</span><span class="sxs-lookup"><span data-stu-id="3de2a-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="3de2a-107">Прежде чем произойдет передача данных, система проверяет, область памяти указанного размера, начиная с базового адреса, доступен для записи.</span><span class="sxs-lookup"><span data-stu-id="3de2a-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="3de2a-108">Если он недоступен, произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="3de2a-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="3de2a-109">[in] Число байтов для записи в область памяти.</span><span class="sxs-lookup"><span data-stu-id="3de2a-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="3de2a-110">[in] Буфер, содержащий записываемые данные.</span><span class="sxs-lookup"><span data-stu-id="3de2a-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="3de2a-111">[out] Указатель на переменную, которая получает число байтов, записанных в область памяти, в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="3de2a-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="3de2a-112">Если `written` имеет значение NULL, этот параметр учитывается.</span><span class="sxs-lookup"><span data-stu-id="3de2a-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3de2a-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="3de2a-113">Remarks</span></span>  
 <span data-ttu-id="3de2a-114">Данные автоматически записываются за любыми точками останова.</span><span class="sxs-lookup"><span data-stu-id="3de2a-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="3de2a-115">В платформе .NET Framework версии 2.0 машинные отладчики не следует использовать этот метод для вставки точки останова в поток инструкций.</span><span class="sxs-lookup"><span data-stu-id="3de2a-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="3de2a-116">Используйте [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) вместо него.</span><span class="sxs-lookup"><span data-stu-id="3de2a-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="3de2a-117">`WriteMemory` Метод должен использоваться только за пределами управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="3de2a-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="3de2a-118">Этот метод может привести к повреждению среды выполнения при неправильном.</span><span class="sxs-lookup"><span data-stu-id="3de2a-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de2a-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3de2a-119">Requirements</span></span>  
 <span data-ttu-id="3de2a-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3de2a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de2a-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3de2a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3de2a-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3de2a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3de2a-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de2a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
