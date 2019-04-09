---
title: Метод ICorDebugObjectValue::IsValueClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71e32211e6ab16fb5e4e2c624dbad3af5fd6b09f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132027"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="30384-102">Метод ICorDebugObjectValue::IsValueClass</span><span class="sxs-lookup"><span data-stu-id="30384-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="30384-103">Получает значение, указывающее, является ли значение этого объекта является типом значения.</span><span class="sxs-lookup"><span data-stu-id="30384-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30384-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30384-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30384-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30384-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="30384-106">[out] Указатель на логическое значение, которое является `true` Если значение объекта, представленного этот «ICorDebugObjectValue» является типом значения, а не ссылочный тип; в противном случае `pbIsValueClass` является `false`.</span><span class="sxs-lookup"><span data-stu-id="30384-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30384-107">Требования</span><span class="sxs-lookup"><span data-stu-id="30384-107">Requirements</span></span>  
 <span data-ttu-id="30384-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30384-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30384-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30384-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30384-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30384-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="30384-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="30384-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30384-112">См. также</span><span class="sxs-lookup"><span data-stu-id="30384-112">See also</span></span>
