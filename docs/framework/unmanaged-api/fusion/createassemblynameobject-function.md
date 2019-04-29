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
ms.openlocfilehash: cd8609bedcea28c1cb8559d378b5e171f3ad568e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669966"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="99d10-102">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="99d10-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="99d10-103">Получает указатель интерфейса на [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) экземпляр, представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="99d10-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99d10-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d10-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99d10-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="99d10-106">[out] Возвращенный `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="99d10-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="99d10-107">[in] Имя сборки, для которой нужно создать объект `IAssemblyName` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="99d10-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="99d10-108">[in] Флаги для передачи в конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="99d10-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="99d10-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="99d10-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="99d10-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="99d10-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d10-111">Требования</span><span class="sxs-lookup"><span data-stu-id="99d10-111">Requirements</span></span>  
 <span data-ttu-id="99d10-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99d10-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d10-113">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="99d10-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="99d10-114">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99d10-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99d10-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d10-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d10-116">См. также</span><span class="sxs-lookup"><span data-stu-id="99d10-116">See also</span></span>

- [<span data-ttu-id="99d10-117">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="99d10-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="99d10-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="99d10-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
