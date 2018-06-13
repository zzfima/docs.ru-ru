---
title: Функция CreateAssemblyNameObject
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5433c49db8e507c6026ab0e87040dd5634ad0808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430442"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="4a41d-102">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="4a41d-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="4a41d-103">Возвращает указатель интерфейса [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) экземпляр, представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="4a41d-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a41d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a41d-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a41d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a41d-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="4a41d-106">[out] Возвращаемый `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="4a41d-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="4a41d-107">[in] Имя сборки, для которого необходимо создать новый `IAssemblyName` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4a41d-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4a41d-108">[in] Флаги для передачи в конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="4a41d-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="4a41d-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="4a41d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4a41d-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="4a41d-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a41d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4a41d-111">Requirements</span></span>  
 <span data-ttu-id="4a41d-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a41d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a41d-113">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4a41d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4a41d-114">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a41d-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a41d-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a41d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a41d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4a41d-116">See Also</span></span>  
 [<span data-ttu-id="4a41d-117">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="4a41d-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="4a41d-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="4a41d-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
