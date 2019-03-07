---
title: Функция CreateApplicationContext
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6b5aa78efcc19f1fc50c8e9bfc5105f9afd7d50
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495212"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="46dda-102">Функция CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="46dda-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="46dda-103">Эта функция поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="46dda-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46dda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46dda-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="46dda-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46dda-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="46dda-106">[in] Указатель на понятное имя.</span><span class="sxs-lookup"><span data-stu-id="46dda-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="46dda-107">[out] Указатель на контекст приложений.</span><span class="sxs-lookup"><span data-stu-id="46dda-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46dda-108">Требования</span><span class="sxs-lookup"><span data-stu-id="46dda-108">Requirements</span></span>  
 <span data-ttu-id="46dda-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46dda-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46dda-110">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="46dda-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="46dda-111">**Библиотека:** Включена как ресурс в Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="46dda-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="46dda-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46dda-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dda-113">См. также</span><span class="sxs-lookup"><span data-stu-id="46dda-113">See also</span></span>
- [<span data-ttu-id="46dda-114">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="46dda-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="46dda-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="46dda-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="46dda-116">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="46dda-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
