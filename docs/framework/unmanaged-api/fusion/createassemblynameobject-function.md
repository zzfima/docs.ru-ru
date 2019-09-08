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
ms.openlocfilehash: fb53014a28fb291b8463535addfb61e62d32d7d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795352"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="76de6-102">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="76de6-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="76de6-103">Возвращает указатель интерфейса на экземпляр [IAssemblyName](iassemblyname-interface.md) , представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="76de6-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76de6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76de6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="76de6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76de6-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="76de6-106">заполняет Возвращаемое `IAssemblyName`значение.</span><span class="sxs-lookup"><span data-stu-id="76de6-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="76de6-107">окне Имя сборки, для которой создается новый `IAssemblyName` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="76de6-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="76de6-108">окне Флаги, передаваемые в конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="76de6-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="76de6-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="76de6-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="76de6-110">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="76de6-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76de6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="76de6-111">Requirements</span></span>  
 <span data-ttu-id="76de6-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76de6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76de6-113">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="76de6-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="76de6-114">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76de6-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76de6-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76de6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76de6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="76de6-116">See also</span></span>

- [<span data-ttu-id="76de6-117">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="76de6-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="76de6-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="76de6-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
