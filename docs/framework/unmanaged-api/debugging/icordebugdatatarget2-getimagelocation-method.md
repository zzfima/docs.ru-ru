---
title: Метод ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: 8b873e28bfab31ea18924f471f916475efd345d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122129"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="6e3cc-102">Метод ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="6e3cc-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="6e3cc-103">Возвращает путь для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="6e3cc-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e3cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e3cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e3cc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e3cc-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="6e3cc-106">окне Значение [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="6e3cc-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6e3cc-107">[входной] Число символов в буфере, которые должен получить путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="6e3cc-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6e3cc-108">[выходной] Указатель на число символов, записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="6e3cc-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="6e3cc-109">[выходной] Путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="6e3cc-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e3cc-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="6e3cc-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e3cc-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6e3cc-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e3cc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6e3cc-112">Requirements</span></span>  
 <span data-ttu-id="6e3cc-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e3cc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e3cc-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e3cc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e3cc-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e3cc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e3cc-116">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e3cc-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3cc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6e3cc-117">See also</span></span>

- [<span data-ttu-id="6e3cc-118">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="6e3cc-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="6e3cc-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6e3cc-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
