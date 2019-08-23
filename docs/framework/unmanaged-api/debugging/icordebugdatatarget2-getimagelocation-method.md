---
title: Метод ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b046a5fcd514dde84e2f0f8c22ee23529ee906e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911457"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="2648b-102">Метод ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="2648b-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="2648b-103">Возвращает путь для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="2648b-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2648b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2648b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2648b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2648b-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="2648b-106">окне Значение [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="2648b-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2648b-107">[входной] Число символов в буфере, которые должен получить путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="2648b-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2648b-108">[выходной] Указатель на число символов, записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="2648b-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="2648b-109">[выходной] Путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="2648b-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2648b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2648b-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2648b-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="2648b-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2648b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2648b-112">Requirements</span></span>  
 <span data-ttu-id="2648b-113">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2648b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2648b-114">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2648b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2648b-115">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="2648b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2648b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2648b-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2648b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2648b-117">See also</span></span>

- [<span data-ttu-id="2648b-118">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="2648b-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="2648b-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2648b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
