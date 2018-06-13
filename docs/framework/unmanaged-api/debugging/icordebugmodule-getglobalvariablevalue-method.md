---
title: Метод ICorDebugModule::GetGlobalVariableValue
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa558bf58f3033cc39a2b52d99e3a5329d9e99bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413037"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="b0126-102">Метод ICorDebugModule::GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="b0126-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="b0126-103">Получает значение указанной глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="b0126-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0126-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0126-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0126-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0126-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="b0126-106">[in] `mdFieldDef` Маркер, который ссылается на метаданные, описывающие глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="b0126-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b0126-107">[out] Указатель на адрес объекта ICorDebugValue, который представляет значение заданной глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="b0126-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0126-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b0126-108">Requirements</span></span>  
 <span data-ttu-id="b0126-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0126-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0126-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0126-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0126-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0126-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0126-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0126-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
