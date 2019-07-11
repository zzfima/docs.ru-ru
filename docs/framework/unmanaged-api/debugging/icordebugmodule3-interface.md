---
title: Интерфейс ICorDebugModule3
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37041764ad37221ea80cefa12adfb214287d8248
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764004"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="bf5b9-102">Интерфейс ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="bf5b9-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="bf5b9-103">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="bf5b9-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf5b9-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bf5b9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bf5b9-105">Methods</span></span>  
  
|<span data-ttu-id="bf5b9-106">Метод</span><span class="sxs-lookup"><span data-stu-id="bf5b9-106">Method</span></span>|<span data-ttu-id="bf5b9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bf5b9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf5b9-108">Метод ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="bf5b9-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="bf5b9-109">Создает средство чтения символов (обычно [интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="bf5b9-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf5b9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf5b9-110">Remarks</span></span>  
 <span data-ttu-id="bf5b9-111">Этот интерфейс логически расширяет интерфейс «ICorDebugModule» и «ICorDebugModule2».</span><span class="sxs-lookup"><span data-stu-id="bf5b9-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf5b9-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="bf5b9-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf5b9-113">Требования</span><span class="sxs-lookup"><span data-stu-id="bf5b9-113">Requirements</span></span>  
 <span data-ttu-id="bf5b9-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf5b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf5b9-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf5b9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf5b9-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf5b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf5b9-117">**Версии платформы .NET framework:** 4.5, 4, 3.5 С ПАКЕТОМ ОБНОВЛЕНИЯ 1</span><span class="sxs-lookup"><span data-stu-id="bf5b9-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bf5b9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="bf5b9-118">See also</span></span>

- [<span data-ttu-id="bf5b9-119">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="bf5b9-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="bf5b9-120">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="bf5b9-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="bf5b9-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bf5b9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
