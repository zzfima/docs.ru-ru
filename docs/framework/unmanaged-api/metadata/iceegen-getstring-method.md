---
title: Метод ICeeGen::GetString
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: ada126b41f1c634f7d8daa58480406ac26f92377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177909"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="3c9eb-102">Метод ICeeGen::GetString</span><span class="sxs-lookup"><span data-stu-id="3c9eb-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="3c9eb-103">Сохраняет строку, хранящуюся по указанному относительному виртуальному адресу.</span><span class="sxs-lookup"><span data-stu-id="3c9eb-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="3c9eb-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="3c9eb-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c9eb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c9eb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c9eb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c9eb-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="3c9eb-107">(в) Относительный виртуальный адрес строки для возврата.</span><span class="sxs-lookup"><span data-stu-id="3c9eb-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="3c9eb-108">(ваут) Возвращается строка.</span><span class="sxs-lookup"><span data-stu-id="3c9eb-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c9eb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3c9eb-109">Requirements</span></span>  
 <span data-ttu-id="3c9eb-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c9eb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c9eb-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c9eb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c9eb-112">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c9eb-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c9eb-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c9eb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9eb-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3c9eb-114">See also</span></span>

- [<span data-ttu-id="3c9eb-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="3c9eb-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
