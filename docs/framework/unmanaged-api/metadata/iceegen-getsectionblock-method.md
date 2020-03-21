---
title: Метод ICeeGen::GetSectionBlock
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176088"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="7090b-102">Метод ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="7090b-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="7090b-103">Получает разделный блок базы кода.</span><span class="sxs-lookup"><span data-stu-id="7090b-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="7090b-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="7090b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7090b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7090b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="7090b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7090b-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7090b-107">(в) Раздел, из которого можно получить блок базы кода.</span><span class="sxs-lookup"><span data-stu-id="7090b-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="7090b-108">(в) Длина блока, который необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="7090b-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="7090b-109">(в) Байт, относительно начала раздела, с которым выровнять первый байт блока.</span><span class="sxs-lookup"><span data-stu-id="7090b-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="7090b-110">Это положение блока в разделе.</span><span class="sxs-lookup"><span data-stu-id="7090b-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="7090b-111">(ваут) Указатель на место, которое получает адрес извлеченного блока.</span><span class="sxs-lookup"><span data-stu-id="7090b-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7090b-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="7090b-112">Remarks</span></span>  
 <span data-ttu-id="7090b-113">Звоните `GetSectionBlock` только в том случае, если у вас есть специальные требования к разделу, которые не обрабатываются другими методами.</span><span class="sxs-lookup"><span data-stu-id="7090b-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7090b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7090b-114">Requirements</span></span>  
 <span data-ttu-id="7090b-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7090b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7090b-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7090b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7090b-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7090b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7090b-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7090b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7090b-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7090b-119">See also</span></span>

- [<span data-ttu-id="7090b-120">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="7090b-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
