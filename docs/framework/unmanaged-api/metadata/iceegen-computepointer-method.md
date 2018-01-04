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
ms.workload: dotnet
ms.openlocfilehash: 0b027615f7697b9ea103d44bea0ec44834fe3f04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="62df4-102">Метод ICeeGen::ComputePointer</span><span class="sxs-lookup"><span data-stu-id="62df4-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="62df4-103">Определяет буфер для заданного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="62df4-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="62df4-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="62df4-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62df4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62df4-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62df4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="62df4-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="62df4-107">[in] Разделе кода, для которого необходимо вернуть буфера.</span><span class="sxs-lookup"><span data-stu-id="62df4-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="62df4-108">[in] Относительный виртуальный адрес метода, для которого необходимо получить указатель.</span><span class="sxs-lookup"><span data-stu-id="62df4-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="62df4-109">[out] Указатель на возвращаемый буфер.</span><span class="sxs-lookup"><span data-stu-id="62df4-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62df4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="62df4-110">Requirements</span></span>  
 <span data-ttu-id="62df4-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62df4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62df4-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="62df4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62df4-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62df4-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62df4-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62df4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62df4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="62df4-115">See Also</span></span>  
 [<span data-ttu-id="62df4-116">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="62df4-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
