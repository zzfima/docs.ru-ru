---
title: Метод ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9768fb91749158bf3193919b2106bde1c618468a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413235"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="4ec9e-102">Метод ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="4ec9e-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="4ec9e-103">Возвращает размер загруженного модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="4ec9e-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ec9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ec9e-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ec9e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ec9e-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="4ec9e-106">[out] Указатель на число байтов в загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="4ec9e-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ec9e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ec9e-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ec9e-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="4ec9e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ec9e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4ec9e-109">Requirements</span></span>  
 <span data-ttu-id="4ec9e-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ec9e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ec9e-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ec9e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ec9e-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ec9e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ec9e-113">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ec9e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec9e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4ec9e-114">See Also</span></span>  
 [<span data-ttu-id="4ec9e-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="4ec9e-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="4ec9e-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4ec9e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
