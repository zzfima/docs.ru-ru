---
title: Метод ICeeGen::EmitString
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f51ce9a4b45bd674f53cf7b4c4d6cedb8d46858d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586427"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="c397a-102">Метод ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="c397a-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="c397a-103">Создает указанную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="c397a-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="c397a-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="c397a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c397a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c397a-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c397a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c397a-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="c397a-107">[in] Строка для выпуска.</span><span class="sxs-lookup"><span data-stu-id="c397a-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="c397a-108">[out] Относительный виртуальный адрес порожденную строки.</span><span class="sxs-lookup"><span data-stu-id="c397a-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c397a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c397a-109">Requirements</span></span>  
 <span data-ttu-id="c397a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c397a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c397a-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c397a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c397a-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c397a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c397a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c397a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c397a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c397a-114">See also</span></span>
- [<span data-ttu-id="c397a-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="c397a-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
