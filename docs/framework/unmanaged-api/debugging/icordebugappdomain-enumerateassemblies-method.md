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
ms.openlocfilehash: 13137dcf7c2edd96397916cc7db905c9e48a3d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401604"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="00a36-102">Метод ICorDebugAppDomain::EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="00a36-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="00a36-103">Получает перечислитель для сборок в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="00a36-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a36-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00a36-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00a36-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00a36-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="00a36-106">[out] Указатель на адрес объекта ICorDebugAssemblyEnum, который является перечислителем для сборок в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="00a36-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a36-107">Требования</span><span class="sxs-lookup"><span data-stu-id="00a36-107">Requirements</span></span>  
 <span data-ttu-id="00a36-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00a36-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a36-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00a36-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00a36-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00a36-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00a36-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a36-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
