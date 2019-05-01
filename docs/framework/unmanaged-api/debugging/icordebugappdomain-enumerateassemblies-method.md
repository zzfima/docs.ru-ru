---
title: Метод ICorDebugAppDomain::EnumerateAssemblies
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ce95daaee3c74ac57b107ab8bcb23d41e42cabb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989546"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="18a1f-102">Метод ICorDebugAppDomain::EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="18a1f-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="18a1f-103">Получает перечислитель для сборок в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="18a1f-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18a1f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18a1f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18a1f-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="18a1f-106">[out] Указатель на адрес объекта ICorDebugAssemblyEnum, который является перечислителем для сборок в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="18a1f-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18a1f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="18a1f-107">Requirements</span></span>  
 <span data-ttu-id="18a1f-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18a1f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18a1f-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18a1f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18a1f-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18a1f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18a1f-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18a1f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
