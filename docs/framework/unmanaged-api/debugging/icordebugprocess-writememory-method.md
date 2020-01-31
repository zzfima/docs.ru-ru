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
ms.openlocfilehash: fb3e0ccb57cf3b056bd25e643706e49b8bc75531
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792543"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="28fb4-102">Метод ICorDebugProcess::WriteMemory</span><span class="sxs-lookup"><span data-stu-id="28fb4-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="28fb4-103">Записывает данные в область памяти в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="28fb4-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28fb4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28fb4-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28fb4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28fb4-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="28fb4-106">окне `CORDB_ADDRESS` значение, являющееся базовым адресом области памяти, в которую записываются данные.</span><span class="sxs-lookup"><span data-stu-id="28fb4-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="28fb4-107">Перед передачей данных система проверяет, что область памяти указанного размера, начиная с базового адреса, доступна для записи.</span><span class="sxs-lookup"><span data-stu-id="28fb4-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="28fb4-108">Если он недоступен, метод завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="28fb4-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="28fb4-109">окне Число байтов, записываемых в область памяти.</span><span class="sxs-lookup"><span data-stu-id="28fb4-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="28fb4-110">окне Буфер, содержащий записываемые данные.</span><span class="sxs-lookup"><span data-stu-id="28fb4-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="28fb4-111">заполняет Указатель на переменную, которая получает число байтов, записанных в область памяти в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="28fb4-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="28fb4-112">Если `written` имеет значение NULL, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="28fb4-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28fb4-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="28fb4-113">Remarks</span></span>  
 <span data-ttu-id="28fb4-114">Данные автоматически записываются за любые точки останова.</span><span class="sxs-lookup"><span data-stu-id="28fb4-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="28fb4-115">В .NET Framework версии 2,0 отладчики машинного кода не должны использовать этот метод для вставки точек останова в поток инструкций.</span><span class="sxs-lookup"><span data-stu-id="28fb4-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="28fb4-116">Вместо этого используйте [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md) .</span><span class="sxs-lookup"><span data-stu-id="28fb4-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="28fb4-117">Метод `WriteMemory` следует использовать только за пределами управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="28fb4-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="28fb4-118">Этот метод может повредить среду выполнения при неправильном использовании.</span><span class="sxs-lookup"><span data-stu-id="28fb4-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28fb4-119">Требования</span><span class="sxs-lookup"><span data-stu-id="28fb4-119">Requirements</span></span>  
 <span data-ttu-id="28fb4-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28fb4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28fb4-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28fb4-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28fb4-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28fb4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28fb4-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28fb4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
