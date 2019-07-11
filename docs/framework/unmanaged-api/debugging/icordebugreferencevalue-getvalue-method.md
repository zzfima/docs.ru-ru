---
title: Метод ICorDebugReferenceValue::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5542cf5895bc60c5880f2f082a9c14d722e02478
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744921"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="4255b-102">Метод ICorDebugReferenceValue::GetValue</span><span class="sxs-lookup"><span data-stu-id="4255b-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="4255b-103">Получает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="4255b-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4255b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4255b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4255b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4255b-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="4255b-106">[out] Указатель на `CORDB_ADDRESS` значение, указывающее адрес объекта, на который указывает этот объект ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="4255b-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4255b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4255b-107">Requirements</span></span>  
 <span data-ttu-id="4255b-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4255b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4255b-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4255b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4255b-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4255b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4255b-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4255b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
