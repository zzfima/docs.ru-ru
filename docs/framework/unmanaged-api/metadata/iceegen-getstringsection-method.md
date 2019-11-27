---
title: Метод ICeeGen::GetStringSection
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
ms.openlocfilehash: ba8da686d1834c81111828e9856525b96f575b93
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443263"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="95226-102">Метод ICeeGen::GetStringSection</span><span class="sxs-lookup"><span data-stu-id="95226-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="95226-103">Возвращает строковое представление раздела кода, на который ссылается указанный маркер.</span><span class="sxs-lookup"><span data-stu-id="95226-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="95226-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="95226-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95226-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95226-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95226-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="95226-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="95226-107">[вход, выход] Маркер раздела кода.</span><span class="sxs-lookup"><span data-stu-id="95226-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95226-108">Требования</span><span class="sxs-lookup"><span data-stu-id="95226-108">Requirements</span></span>  
 <span data-ttu-id="95226-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95226-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95226-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="95226-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95226-111">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="95226-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95226-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95226-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95226-113">См. также</span><span class="sxs-lookup"><span data-stu-id="95226-113">See also</span></span>

- [<span data-ttu-id="95226-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="95226-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
