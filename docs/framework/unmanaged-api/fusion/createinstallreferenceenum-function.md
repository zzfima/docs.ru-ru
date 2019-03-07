---
title: Функция CreateInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6296a5c80587a6fd1a7b03e20ffdf7fd1316e9d2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502273"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="78e30-102">Функция CreateInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="78e30-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="78e30-103">Возвращает указатель на [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) экземпляр, который представляет список ссылок на приложения для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="78e30-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78e30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78e30-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="78e30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78e30-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="78e30-106">[out] Возвращенный `IInstallReferenceEnum` указатель.</span><span class="sxs-lookup"><span data-stu-id="78e30-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="78e30-107">[in] [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) , определяющий сборку, для которого необходимо перечислить ссылки.</span><span class="sxs-lookup"><span data-stu-id="78e30-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="78e30-108">[in] Флаги, которые влияют на поведение перечислителя.</span><span class="sxs-lookup"><span data-stu-id="78e30-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="78e30-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="78e30-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="78e30-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="78e30-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78e30-111">Требования</span><span class="sxs-lookup"><span data-stu-id="78e30-111">Requirements</span></span>  
 <span data-ttu-id="78e30-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78e30-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78e30-113">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="78e30-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="78e30-114">**Библиотека:** Fusion.dll и "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="78e30-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="78e30-115">Используйте Fusion.dll вместо "Mscorwks.dll", чтобы обеспечить целевых правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78e30-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="78e30-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78e30-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e30-117">См. также</span><span class="sxs-lookup"><span data-stu-id="78e30-117">See also</span></span>
- [<span data-ttu-id="78e30-118">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="78e30-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
- [<span data-ttu-id="78e30-119">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="78e30-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="78e30-120">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="78e30-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
