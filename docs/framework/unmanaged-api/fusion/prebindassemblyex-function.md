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
ms.openlocfilehash: a23d3c4fd8eef2e361abf1602157cb4fbb820b48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773856"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="10d21-102">Функция PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="10d21-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="10d21-103">Возвращает после применения политики отображаемое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="10d21-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="10d21-104">Эта функция поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="10d21-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10d21-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10d21-105">Syntax</span></span>  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="10d21-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="10d21-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="10d21-107">[in] Определяет контекст приложения.</span><span class="sxs-lookup"><span data-stu-id="10d21-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="10d21-108">[in] Обозначает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="10d21-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="10d21-109">[in] Идентифицирует родительской сборки.</span><span class="sxs-lookup"><span data-stu-id="10d21-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="10d21-110">Этот параметр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="10d21-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="10d21-111">[in] Определяет версию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="10d21-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="10d21-112">[out] Содержит имя отображаемое после применения политики.</span><span class="sxs-lookup"><span data-stu-id="10d21-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="10d21-113">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="10d21-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="10d21-114">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="10d21-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10d21-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="10d21-115">Remarks</span></span>  
 <span data-ttu-id="10d21-116">`ppNamePostPolicy` Выходной параметр имеет значение только в том случае, если функция возвращает значение HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="10d21-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="10d21-117">В противном случае — значение null.</span><span class="sxs-lookup"><span data-stu-id="10d21-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10d21-118">Требования</span><span class="sxs-lookup"><span data-stu-id="10d21-118">Requirements</span></span>  
 <span data-ttu-id="10d21-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10d21-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10d21-120">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="10d21-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="10d21-121">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10d21-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10d21-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10d21-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d21-123">См. также</span><span class="sxs-lookup"><span data-stu-id="10d21-123">See also</span></span>

- [<span data-ttu-id="10d21-124">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="10d21-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
