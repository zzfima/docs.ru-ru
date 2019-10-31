---
title: Метод ICorDebugManagedCallback::UpdateModuleSymbols
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
ms.openlocfilehash: 1f5b413ffbbc8fccbea38f23d8c87d40e010dd37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130613"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="9320c-102">Метод ICorDebugManagedCallback::UpdateModuleSymbols</span><span class="sxs-lookup"><span data-stu-id="9320c-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="9320c-103">Уведомляет отладчик о том, что символы для модуля среды CLR были изменены.</span><span class="sxs-lookup"><span data-stu-id="9320c-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9320c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9320c-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9320c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9320c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9320c-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий модуль, в котором были изменены символы.</span><span class="sxs-lookup"><span data-stu-id="9320c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="9320c-107">окне Указатель на объект ICorDebugModule, представляющий модуль, в котором были изменены символы.</span><span class="sxs-lookup"><span data-stu-id="9320c-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="9320c-108">окне Указатель на объект `IStream` Win32 COM, содержащий измененные символы.</span><span class="sxs-lookup"><span data-stu-id="9320c-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9320c-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="9320c-109">Remarks</span></span>  
 <span data-ttu-id="9320c-110">Этот метод предоставляет возможность обновить представление символов модуля отладчика путем вызова [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) или [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="9320c-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="9320c-111">Этот обратный вызов может происходить несколько раз для одного модуля.</span><span class="sxs-lookup"><span data-stu-id="9320c-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="9320c-112">Отладчик должен попытаться привязать несвязанные точки останова на уровне источника.</span><span class="sxs-lookup"><span data-stu-id="9320c-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9320c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9320c-113">Requirements</span></span>  
 <span data-ttu-id="9320c-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9320c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9320c-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9320c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9320c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9320c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9320c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9320c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9320c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9320c-118">See also</span></span>

- [<span data-ttu-id="9320c-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9320c-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
