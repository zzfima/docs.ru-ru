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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225005"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="b880a-102">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="b880a-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="b880a-103">Получает указатель интерфейса на [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) экземпляр, представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b880a-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b880a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b880a-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b880a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b880a-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="b880a-106">[out] Возвращенный `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b880a-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="b880a-107">[in] Имя сборки, для которой нужно создать объект `IAssemblyName` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b880a-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b880a-108">[in] Флаги для передачи в конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="b880a-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b880a-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="b880a-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b880a-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="b880a-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b880a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b880a-111">Requirements</span></span>  
 <span data-ttu-id="b880a-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b880a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b880a-113">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b880a-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b880a-114">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b880a-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b880a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b880a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b880a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b880a-116">See also</span></span>

- [<span data-ttu-id="b880a-117">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="b880a-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="b880a-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="b880a-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
