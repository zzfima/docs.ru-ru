---
title: Функция PreBindAssemblyEx
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b3b3a32796b5805dbf86449921518a77e95d6b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480537"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="a0d27-102">Функция PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="a0d27-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="a0d27-103">Возвращает после применения политики отображаемое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="a0d27-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="a0d27-104">Эта функция поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="a0d27-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0d27-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0d27-105">Syntax</span></span>  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0d27-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0d27-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="a0d27-107">[in] Определяет контекст приложения.</span><span class="sxs-lookup"><span data-stu-id="a0d27-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="a0d27-108">[in] Обозначает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="a0d27-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="a0d27-109">[in] Идентифицирует родительской сборки.</span><span class="sxs-lookup"><span data-stu-id="a0d27-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="a0d27-110">Этот параметр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="a0d27-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="a0d27-111">[in] Определяет версию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0d27-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="a0d27-112">[out] Содержит имя отображаемое после применения политики.</span><span class="sxs-lookup"><span data-stu-id="a0d27-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a0d27-113">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="a0d27-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a0d27-114">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="a0d27-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0d27-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0d27-115">Remarks</span></span>  
 <span data-ttu-id="a0d27-116">`ppNamePostPolicy` Выходной параметр имеет значение только в том случае, если функция возвращает значение HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="a0d27-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="a0d27-117">В противном случае — значение null.</span><span class="sxs-lookup"><span data-stu-id="a0d27-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0d27-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a0d27-118">Requirements</span></span>  
 <span data-ttu-id="a0d27-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0d27-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0d27-120">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a0d27-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a0d27-121">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0d27-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0d27-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0d27-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d27-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a0d27-123">See also</span></span>
- [<span data-ttu-id="a0d27-124">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="a0d27-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
