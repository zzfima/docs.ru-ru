---
title: "Функция PreBindAssemblyEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PreBindAssemblyEx
api_location: fusion.dll
api_type: DLLExport
f1_keywords: PreBindAssemblyEx
helpviewer_keywords: PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c9bd5cb6be2ccfd25d61a8a2f4347b384e1b2567
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="51274-102">Функция PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="51274-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="51274-103">Возвращает после применения политики отображаемое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="51274-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="51274-104">Эта функция поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="51274-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51274-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51274-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="51274-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="51274-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="51274-107">[in] Определяет контекст приложения.</span><span class="sxs-lookup"><span data-stu-id="51274-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="51274-108">[in] Указывает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="51274-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="51274-109">[in] Идентификатор родительской сборки.</span><span class="sxs-lookup"><span data-stu-id="51274-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="51274-110">Этот параметр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="51274-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="51274-111">[in] Определяет версию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="51274-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="51274-112">[out] Содержит имя отображения после применения политики.</span><span class="sxs-lookup"><span data-stu-id="51274-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="51274-113">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="51274-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="51274-114">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="51274-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51274-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="51274-115">Remarks</span></span>  
 <span data-ttu-id="51274-116">`ppNamePostPolicy` Выходной параметр имеет значение только в том случае, если функция возвращает значение HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="51274-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="51274-117">В противном случае — значение null.</span><span class="sxs-lookup"><span data-stu-id="51274-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51274-118">Требования</span><span class="sxs-lookup"><span data-stu-id="51274-118">Requirements</span></span>  
 <span data-ttu-id="51274-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51274-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51274-120">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="51274-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="51274-121">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51274-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51274-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51274-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51274-123">См. также</span><span class="sxs-lookup"><span data-stu-id="51274-123">See Also</span></span>  
 [<span data-ttu-id="51274-124">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="51274-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
