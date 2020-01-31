---
title: Метод ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: f207cd1c612b6444a9512adaa356ac2d01de7b9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788465"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="04290-102">Метод ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="04290-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="04290-103">Возвращает размер в байтах загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="04290-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04290-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04290-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04290-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04290-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="04290-106">[out] Указатель на число байтов в загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="04290-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04290-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="04290-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04290-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="04290-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04290-109">Требования</span><span class="sxs-lookup"><span data-stu-id="04290-109">Requirements</span></span>  
 <span data-ttu-id="04290-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04290-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04290-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04290-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04290-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04290-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04290-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04290-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04290-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="04290-114">See also</span></span>

- [<span data-ttu-id="04290-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="04290-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="04290-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="04290-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
