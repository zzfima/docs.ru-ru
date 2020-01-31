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
ms.openlocfilehash: 33acc4d9a0819c43d17c362fcbea2e7636521fd3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792936"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="e0ddc-102">Интерфейс ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="e0ddc-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="e0ddc-103">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="e0ddc-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ddc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0ddc-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e0ddc-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e0ddc-105">Methods</span></span>  
  
|<span data-ttu-id="e0ddc-106">Метод</span><span class="sxs-lookup"><span data-stu-id="e0ddc-106">Method</span></span>|<span data-ttu-id="e0ddc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e0ddc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0ddc-108">Метод ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="e0ddc-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="e0ddc-109">Создает средство чтения символов (обычно [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="e0ddc-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0ddc-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="e0ddc-110">Remarks</span></span>  
 <span data-ttu-id="e0ddc-111">Этот интерфейс логически расширяет интерфейсы "ICorDebugModule" и "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="e0ddc-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0ddc-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e0ddc-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ddc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e0ddc-113">Requirements</span></span>  
 <span data-ttu-id="e0ddc-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0ddc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0ddc-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0ddc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0ddc-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0ddc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0ddc-117">**.NET Framework версии:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="e0ddc-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e0ddc-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0ddc-118">See also</span></span>

- [<span data-ttu-id="e0ddc-119">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="e0ddc-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="e0ddc-120">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e0ddc-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="e0ddc-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e0ddc-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
