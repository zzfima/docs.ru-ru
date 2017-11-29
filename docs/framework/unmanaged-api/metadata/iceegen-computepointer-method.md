---
title: "Метод ICeeGen::ComputePointer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.ComputePointer
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c1f5f1c0ea5672812fca387b34238ada2a109938
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="9254d-102">Метод ICeeGen::ComputePointer</span><span class="sxs-lookup"><span data-stu-id="9254d-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="9254d-103">Определяет буфер для заданного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="9254d-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="9254d-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="9254d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9254d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9254d-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9254d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9254d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="9254d-107">[in] Разделе кода, для которого необходимо вернуть буфера.</span><span class="sxs-lookup"><span data-stu-id="9254d-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="9254d-108">[in] Относительный виртуальный адрес метода, для которого необходимо получить указатель.</span><span class="sxs-lookup"><span data-stu-id="9254d-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="9254d-109">[out] Указатель на возвращаемый буфер.</span><span class="sxs-lookup"><span data-stu-id="9254d-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9254d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9254d-110">Requirements</span></span>  
 <span data-ttu-id="9254d-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9254d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9254d-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9254d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9254d-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9254d-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9254d-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9254d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9254d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9254d-115">See Also</span></span>  
 [<span data-ttu-id="9254d-116">ICeeGen-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9254d-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
