---
title: Метод ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 4cf2c5c099de3d66878f09ff702a1cad6ddb8f57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122623"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="64469-102">Метод ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="64469-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="64469-103">Получает имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="64469-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64469-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64469-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64469-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64469-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="64469-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="64469-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="64469-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="64469-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="64469-108">[out] Массив символов, содержащий имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="64469-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64469-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="64469-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64469-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="64469-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64469-111">Требования</span><span class="sxs-lookup"><span data-stu-id="64469-111">Requirements</span></span>  
 <span data-ttu-id="64469-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64469-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64469-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64469-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64469-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64469-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64469-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64469-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64469-116">См. также</span><span class="sxs-lookup"><span data-stu-id="64469-116">See also</span></span>

- [<span data-ttu-id="64469-117">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="64469-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="64469-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="64469-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
