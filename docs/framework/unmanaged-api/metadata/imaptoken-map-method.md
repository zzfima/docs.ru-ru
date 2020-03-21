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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176075"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="c4c66-102">Метод IMapToken::Map</span><span class="sxs-lookup"><span data-stu-id="c4c66-102">IMapToken::Map Method</span></span>
<span data-ttu-id="c4c66-103">Отображает связь между сборками с помощью подписей метаданных.</span><span class="sxs-lookup"><span data-stu-id="c4c66-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4c66-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4c66-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4c66-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="c4c66-106">(в) Токен метаданных, представляющий объект импортированного кода.</span><span class="sxs-lookup"><span data-stu-id="c4c66-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="c4c66-107">(в) Токен метаданных, представляющий испускаемый объект кода.</span><span class="sxs-lookup"><span data-stu-id="c4c66-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4c66-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4c66-108">Remarks</span></span>  
 <span data-ttu-id="c4c66-109">Когда повторная карта токенов происходит во время слияния, исходный маркер приобщен в области метаданных импортируемых (источников), а новый маркер — в области испускаемых (целевых) метаданных.</span><span class="sxs-lookup"><span data-stu-id="c4c66-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4c66-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c4c66-110">Requirements</span></span>  
 <span data-ttu-id="c4c66-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4c66-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4c66-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c4c66-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4c66-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4c66-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4c66-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4c66-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c66-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4c66-115">See also</span></span>

- [<span data-ttu-id="c4c66-116">Интерфейс IMapToken</span><span class="sxs-lookup"><span data-stu-id="c4c66-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
