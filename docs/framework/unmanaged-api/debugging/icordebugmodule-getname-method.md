---
title: Метод ICorDebugModule::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bebee019595143d25e950719ad62d9e10b76a3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418910"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="e4160-102">Метод ICorDebugModule::GetName</span><span class="sxs-lookup"><span data-stu-id="e4160-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="e4160-103">Возвращает имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="e4160-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4160-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4160-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4160-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4160-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="e4160-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="e4160-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e4160-107">[in] Указатель на длину возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="e4160-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="e4160-108">[out] Массив, в котором хранится возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="e4160-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4160-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4160-109">Remarks</span></span>  
 <span data-ttu-id="e4160-110">`GetName` Метод возвращает значение HRESULT S_OK, если имя файла модуля соответствует имени на диске.</span><span class="sxs-lookup"><span data-stu-id="e4160-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="e4160-111">`GetName` Возвращает значение S_FALSE HRESULT, если оно создано, например в памяти или динамический модуль.</span><span class="sxs-lookup"><span data-stu-id="e4160-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4160-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e4160-112">Requirements</span></span>  
 <span data-ttu-id="e4160-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4160-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4160-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4160-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4160-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4160-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4160-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4160-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4160-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e4160-117">See Also</span></span>  
    
 
