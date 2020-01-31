---
title: Метод ICorDebugManagedCallback::UnloadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: f2f19987d22502acbe06bd5e5c14b0d6c17cbe24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781584"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="fcc6b-102">Метод ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="fcc6b-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="fcc6b-103">Уведомляет отладчик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="fcc6b-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcc6b-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcc6b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fcc6b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fcc6b-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий класс.</span><span class="sxs-lookup"><span data-stu-id="fcc6b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="fcc6b-107">окне Указатель на объект ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="fcc6b-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcc6b-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="fcc6b-108">Remarks</span></span>  
 <span data-ttu-id="fcc6b-109">После этого вызова не следует ссылаться на класс.</span><span class="sxs-lookup"><span data-stu-id="fcc6b-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcc6b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fcc6b-110">Requirements</span></span>  
 <span data-ttu-id="fcc6b-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcc6b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc6b-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcc6b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcc6b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcc6b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcc6b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc6b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc6b-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcc6b-115">See also</span></span>

- [<span data-ttu-id="fcc6b-116">Метод LoadClass</span><span class="sxs-lookup"><span data-stu-id="fcc6b-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="fcc6b-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fcc6b-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
