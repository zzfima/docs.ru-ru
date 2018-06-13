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
ms.openlocfilehash: 92df7bbcc2c391dd28f4075a97595762403d8def
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416319"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="e4c80-102">Метод ICorDebugReferenceValue::GetValue</span><span class="sxs-lookup"><span data-stu-id="e4c80-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="e4c80-103">Получает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="e4c80-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4c80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4c80-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4c80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4c80-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="e4c80-106">[out] Указатель на `CORDB_ADDRESS` значение, указывающее адрес объекта, на который указывает этот объект ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="e4c80-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4c80-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e4c80-107">Requirements</span></span>  
 <span data-ttu-id="e4c80-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4c80-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4c80-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4c80-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4c80-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4c80-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4c80-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4c80-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
