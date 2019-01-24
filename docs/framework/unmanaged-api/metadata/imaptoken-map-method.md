---
title: Метод IMapToken::Map
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31c18061ad5f21e26665cd0d6883b0eb26afd1d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557481"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="916dc-102">Метод IMapToken::Map</span><span class="sxs-lookup"><span data-stu-id="916dc-102">IMapToken::Map Method</span></span>
<span data-ttu-id="916dc-103">Сопоставляет связь между сборками, используя подписи метаданных.</span><span class="sxs-lookup"><span data-stu-id="916dc-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="916dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="916dc-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="916dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="916dc-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="916dc-106">[in] Токен метаданных, представляющий объект импортированном коде.</span><span class="sxs-lookup"><span data-stu-id="916dc-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="916dc-107">[in] Токен метаданных, представляющий объект порожденного кода.</span><span class="sxs-lookup"><span data-stu-id="916dc-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="916dc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="916dc-108">Remarks</span></span>  
 <span data-ttu-id="916dc-109">При выполнении повторного сопоставления маркеров во время слияния, исходный маркер действует в области метаданных исходную и в области метаданных целевую относится новый токен.</span><span class="sxs-lookup"><span data-stu-id="916dc-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="916dc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="916dc-110">Requirements</span></span>  
 <span data-ttu-id="916dc-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="916dc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="916dc-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="916dc-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="916dc-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="916dc-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="916dc-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="916dc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916dc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="916dc-115">See also</span></span>
- [<span data-ttu-id="916dc-116">Интерфейс IMapToken</span><span class="sxs-lookup"><span data-stu-id="916dc-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
