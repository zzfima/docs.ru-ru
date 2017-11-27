---
title: "Функция CreateApplicationContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateApplicationContext
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateApplicationContext
helpviewer_keywords: CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c089c32d4bc8474168274186a9303d39976abfca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="b9ae1-102">Функция CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="b9ae1-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="b9ae1-103">Эта функция поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="b9ae1-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ae1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9ae1-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9ae1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9ae1-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="b9ae1-106">[in] Указатель с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="b9ae1-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="b9ae1-107">[out] Указатель на контекст приложений.</span><span class="sxs-lookup"><span data-stu-id="b9ae1-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ae1-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b9ae1-108">Requirements</span></span>  
 <span data-ttu-id="b9ae1-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9ae1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ae1-110">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b9ae1-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b9ae1-111">**Библиотека:** включена как ресурс в Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="b9ae1-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="b9ae1-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ae1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ae1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b9ae1-113">See Also</span></span>  
 [<span data-ttu-id="b9ae1-114">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="b9ae1-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="b9ae1-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="b9ae1-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="b9ae1-116">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="b9ae1-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
