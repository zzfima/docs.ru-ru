---
title: Метод ICorDebugValue::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0023b8ad815b9204ed56791698c7242dfe90bec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421662"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="05881-102">Метод ICorDebugValue::GetSize</span><span class="sxs-lookup"><span data-stu-id="05881-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="05881-103">Возвращает размер в байтах объекта «ICorDebugValue».</span><span class="sxs-lookup"><span data-stu-id="05881-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05881-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05881-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05881-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05881-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="05881-106">[out] Размер в байтах этого значения объекта.</span><span class="sxs-lookup"><span data-stu-id="05881-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05881-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="05881-107">Remarks</span></span>  
 <span data-ttu-id="05881-108">Если тип является ссылочным типом, этот метод возвращает размер указателя, а не размер объекта.</span><span class="sxs-lookup"><span data-stu-id="05881-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="05881-109">`ICorDebugValue::GetSize` Возвращает метод `COR_E_OVERFLOW` для объектов, размер которых превышает 4 ГБ на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="05881-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="05881-110">Используйте [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) метод вместо этого для объектов, которые больше 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="05881-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05881-111">Требования</span><span class="sxs-lookup"><span data-stu-id="05881-111">Requirements</span></span>  
 <span data-ttu-id="05881-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05881-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05881-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05881-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05881-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05881-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05881-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05881-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05881-116">См. также</span><span class="sxs-lookup"><span data-stu-id="05881-116">See Also</span></span>  
    
 [<span data-ttu-id="05881-117">Метод GetSize64</span><span class="sxs-lookup"><span data-stu-id="05881-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
