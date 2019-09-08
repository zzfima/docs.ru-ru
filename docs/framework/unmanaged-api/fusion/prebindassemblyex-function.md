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
ms.openlocfilehash: 8aa2d174200db76f5c7a6db43e14bb6904604226
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796328"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="ed737-102">Функция PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="ed737-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="ed737-103">Возвращает отображаемое имя после применения политики для сборки.</span><span class="sxs-lookup"><span data-stu-id="ed737-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="ed737-104">Эта функция поддерживает .NET Frameworkную инфраструктуру и не предназначена для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="ed737-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed737-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed737-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ed737-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed737-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="ed737-107">окне Определяет контекст приложения.</span><span class="sxs-lookup"><span data-stu-id="ed737-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="ed737-108">окне Определяет имя сборки.</span><span class="sxs-lookup"><span data-stu-id="ed737-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="ed737-109">окне Определяет родительскую сборку.</span><span class="sxs-lookup"><span data-stu-id="ed737-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="ed737-110">Этот параметр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="ed737-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="ed737-111">окне Определяет версию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed737-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="ed737-112">заполняет Содержит отображаемое имя после применения политики.</span><span class="sxs-lookup"><span data-stu-id="ed737-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ed737-113">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="ed737-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ed737-114">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="ed737-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed737-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed737-115">Remarks</span></span>  
 <span data-ttu-id="ed737-116">`ppNamePostPolicy` Выходной параметр задается только в том случае, если функция возвращает значение HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="ed737-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="ed737-117">В противном случае он имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="ed737-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed737-118">Требования</span><span class="sxs-lookup"><span data-stu-id="ed737-118">Requirements</span></span>  
 <span data-ttu-id="ed737-119">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed737-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed737-120">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ed737-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ed737-121">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ed737-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed737-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed737-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed737-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ed737-123">See also</span></span>

- [<span data-ttu-id="ed737-124">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="ed737-124">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
