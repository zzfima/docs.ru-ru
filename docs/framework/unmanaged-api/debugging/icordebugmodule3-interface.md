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
ms.openlocfilehash: 58bad617eb91b7e529ff3d95edd06a5c73feee64
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111754"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="9ac6a-102">Интерфейс ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="9ac6a-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="9ac6a-103">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="9ac6a-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ac6a-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9ac6a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9ac6a-105">Methods</span></span>  
  
|<span data-ttu-id="9ac6a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9ac6a-106">Method</span></span>|<span data-ttu-id="9ac6a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9ac6a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ac6a-108">Метод ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="9ac6a-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="9ac6a-109">Создает средство чтения символов (обычно [интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="9ac6a-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ac6a-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ac6a-110">Remarks</span></span>  
 <span data-ttu-id="9ac6a-111">Этот интерфейс логически расширяет интерфейс «ICorDebugModule» и «ICorDebugModule2».</span><span class="sxs-lookup"><span data-stu-id="9ac6a-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ac6a-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9ac6a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ac6a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9ac6a-113">Requirements</span></span>  
 <span data-ttu-id="9ac6a-114">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ac6a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ac6a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ac6a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ac6a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ac6a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ac6a-117">**Версии платформы .NET framework:** 4.5, 4, 3.5 с пакетом обновления 1</span><span class="sxs-lookup"><span data-stu-id="9ac6a-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9ac6a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9ac6a-118">See Also</span></span>  
 [<span data-ttu-id="9ac6a-119">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="9ac6a-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="9ac6a-120">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="9ac6a-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="9ac6a-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9ac6a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
