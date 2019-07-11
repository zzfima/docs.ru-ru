---
title: Метод ICorDebugHandleValue::GetHandleType
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0bc65cdeada059f6e9b41dc8eb4d7589a232143d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756821"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="66692-102">Метод ICorDebugHandleValue::GetHandleType</span><span class="sxs-lookup"><span data-stu-id="66692-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="66692-103">Получает значение, указывающее тип токена, на которые ссылается этот объект ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="66692-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66692-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66692-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66692-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66692-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="66692-106">[out] Указатель на значение CorDebugHandleType перечисления, указывающее тип этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="66692-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66692-107">Требования</span><span class="sxs-lookup"><span data-stu-id="66692-107">Requirements</span></span>  
 <span data-ttu-id="66692-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66692-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66692-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66692-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66692-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66692-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66692-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66692-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
