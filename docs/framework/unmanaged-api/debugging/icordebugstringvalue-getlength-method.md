---
title: Метод ICorDebugStringValue::GetLength
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e62539304817432fcab8f3e0958e5a70b371b83d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416951"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="0f734-102">Метод ICorDebugStringValue::GetLength</span><span class="sxs-lookup"><span data-stu-id="0f734-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="0f734-103">Возвращает число символов в строке, который ссылается этот ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="0f734-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f734-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f734-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f734-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f734-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="0f734-106">[out] Указатель на значение, указывающее длину строки, упоминаемой в этом `ICorDebugStringValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="0f734-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f734-107">Требования</span><span class="sxs-lookup"><span data-stu-id="0f734-107">Requirements</span></span>  
 <span data-ttu-id="0f734-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f734-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f734-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f734-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f734-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f734-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f734-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f734-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
