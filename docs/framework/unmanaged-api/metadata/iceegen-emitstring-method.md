---
title: "Метод ICeeGen::EmitString"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.EmitString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f988e54a37212beeeebfbef15e6b148021e0b759
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="a7ffb-102">Метод ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="a7ffb-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="a7ffb-103">Выдает заданную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="a7ffb-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="a7ffb-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="a7ffb-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ffb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7ffb-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7ffb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7ffb-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="a7ffb-107">[in] Строка для выпуска.</span><span class="sxs-lookup"><span data-stu-id="a7ffb-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="a7ffb-108">[out] Относительный виртуальный адрес порожденную строки.</span><span class="sxs-lookup"><span data-stu-id="a7ffb-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ffb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a7ffb-109">Requirements</span></span>  
 <span data-ttu-id="a7ffb-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7ffb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ffb-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7ffb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7ffb-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7ffb-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7ffb-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ffb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ffb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a7ffb-114">See Also</span></span>  
 [<span data-ttu-id="a7ffb-115">ICeeGen-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a7ffb-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
