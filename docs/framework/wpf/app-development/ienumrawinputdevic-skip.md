---
title: IEnumRAWINPUTDEVIC:SKIP
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: f7d7df77c54d4551025aa5a344c96083c263f455
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467172"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="a134f-102">IEnumRAWINPUTDEVIC:SKIP</span><span class="sxs-lookup"><span data-stu-id="a134f-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="a134f-103">Указывает перечислителю пропустить следующий `celt` элементов в перечислении, чтобы следующий вызов [IEnumRAWINPUTDEVIC: Next](ienumrawinputdevic-next.md) не возвращал эти элементы.</span><span class="sxs-lookup"><span data-stu-id="a134f-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a134f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a134f-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a134f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a134f-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="a134f-106">[in] Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="a134f-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a134f-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a134f-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="a134f-108">HRESULT: Значение S_OK, если число предоставленных элементов является `celt`; В противном случае значение S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="a134f-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
