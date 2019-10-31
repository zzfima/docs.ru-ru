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
ms.openlocfilehash: 00345f6c95c67f0494aa721c662f56a9e98cdd7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108714"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="50858-102">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="50858-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="50858-103">Возвращает указатель интерфейса на экземпляр [IAssemblyName](iassemblyname-interface.md) , представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="50858-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50858-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50858-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="50858-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50858-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="50858-106">заполняет Возвращаемый `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="50858-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="50858-107">окне Имя сборки, для которой создается новый экземпляр `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="50858-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="50858-108">окне Флаги, передаваемые в конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="50858-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="50858-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="50858-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="50858-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="50858-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50858-111">Требования</span><span class="sxs-lookup"><span data-stu-id="50858-111">Requirements</span></span>  
 <span data-ttu-id="50858-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50858-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50858-113">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="50858-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="50858-114">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50858-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50858-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50858-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50858-116">См. также</span><span class="sxs-lookup"><span data-stu-id="50858-116">See also</span></span>

- [<span data-ttu-id="50858-117">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="50858-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="50858-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="50858-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
