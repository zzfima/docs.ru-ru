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
ms.openlocfilehash: 7a2288eb84bd51795995032954e41525c2ce605a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137728"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="d8cce-102">Метод ICorDebugReferenceValue::GetValue</span><span class="sxs-lookup"><span data-stu-id="d8cce-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="d8cce-103">Возвращает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="d8cce-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8cce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8cce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8cce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8cce-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="d8cce-106">заполняет Указатель на `CORDB_ADDRESS` значение, указывающее адрес объекта, на который указывает объект ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="d8cce-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8cce-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d8cce-107">Requirements</span></span>  
 <span data-ttu-id="d8cce-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8cce-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8cce-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8cce-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8cce-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8cce-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8cce-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8cce-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
