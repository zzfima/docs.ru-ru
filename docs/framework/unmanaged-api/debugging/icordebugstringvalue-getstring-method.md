---
title: Метод ICorDebugStringValue::GetString
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d3df561a3b48a4b26426235455ef1a074512f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="12502-102">Метод ICorDebugStringValue::GetString</span><span class="sxs-lookup"><span data-stu-id="12502-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="12502-103">Возвращает строку, ссылается этот ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="12502-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12502-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12502-104">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12502-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12502-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="12502-106">[in] Размер массива `szString`.</span><span class="sxs-lookup"><span data-stu-id="12502-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="12502-107">[out] Указатель на число символов, возвращаемых в `szString` массива.</span><span class="sxs-lookup"><span data-stu-id="12502-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="12502-108">[out] Массив, который сохраняет полученные строки.</span><span class="sxs-lookup"><span data-stu-id="12502-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12502-109">Требования</span><span class="sxs-lookup"><span data-stu-id="12502-109">Requirements</span></span>  
 <span data-ttu-id="12502-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12502-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12502-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12502-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12502-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12502-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12502-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12502-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
