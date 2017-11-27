---
title: IEnumRAWINPUTDEVIC:SKIP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 216be1bc48a140bdd326010a87899cc342feb41d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="b4e09-102">IEnumRAWINPUTDEVIC:SKIP</span><span class="sxs-lookup"><span data-stu-id="b4e09-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="b4e09-103">Указывает перечислителю пропустить следующий `celt` элементы в перечислении, чтобы при следующем вызове [IEnumRAWINPUTDEVIC: Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) не вернет эти элементы.</span><span class="sxs-lookup"><span data-stu-id="b4e09-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4e09-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4e09-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4e09-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4e09-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="b4e09-106">[in] Число элементов.</span><span class="sxs-lookup"><span data-stu-id="b4e09-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b4e09-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b4e09-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="b4e09-108">HRESULT: значение S_OK, если число предоставленных элементов составляет `celt`; в противном случае значение S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="b4e09-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
