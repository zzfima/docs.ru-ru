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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225005"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="6fd32-102">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="6fd32-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="6fd32-103">Получает указатель интерфейса на [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) экземпляр, представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="6fd32-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fd32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fd32-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fd32-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6fd32-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="6fd32-106">[out] Возвращенный `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="6fd32-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="6fd32-107">[in] Имя сборки, для которой нужно создать объект `IAssemblyName` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6fd32-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6fd32-108">[in] Флаги для передачи в конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="6fd32-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6fd32-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="6fd32-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="6fd32-110">должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="6fd32-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fd32-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6fd32-111">Requirements</span></span>  
 <span data-ttu-id="6fd32-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fd32-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd32-113">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="6fd32-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6fd32-114">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6fd32-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6fd32-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6fd32-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6fd32-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6fd32-116">See also</span></span>

- [<span data-ttu-id="6fd32-117">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="6fd32-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="6fd32-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="6fd32-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
