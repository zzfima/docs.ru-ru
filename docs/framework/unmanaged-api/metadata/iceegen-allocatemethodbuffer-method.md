---
title: Метод ICeeGen::AllocateMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f56376d4400f4e24aefe2d1e5d4ad504b1d281cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446008"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="ee6a2-102">Метод ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="ee6a2-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="ee6a2-103">Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="ee6a2-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="ee6a2-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="ee6a2-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee6a2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee6a2-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee6a2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee6a2-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="ee6a2-107">[in] Длина буфера для создания.</span><span class="sxs-lookup"><span data-stu-id="ee6a2-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="ee6a2-108">[out] Возвращаемый буфер.</span><span class="sxs-lookup"><span data-stu-id="ee6a2-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="ee6a2-109">[out] Относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="ee6a2-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee6a2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ee6a2-110">Requirements</span></span>  
 <span data-ttu-id="ee6a2-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee6a2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee6a2-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee6a2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee6a2-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee6a2-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee6a2-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee6a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6a2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ee6a2-115">See Also</span></span>  
 [<span data-ttu-id="ee6a2-116">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="ee6a2-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
