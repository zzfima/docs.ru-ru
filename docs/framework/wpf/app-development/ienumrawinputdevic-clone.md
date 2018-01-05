---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db218ec824dfe163946b0c1bd412efd0f78f4ad8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="47bcb-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="47bcb-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="47bcb-103">Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.</span><span class="sxs-lookup"><span data-stu-id="47bcb-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47bcb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47bcb-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47bcb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47bcb-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="47bcb-106">[out] Выходная переменная, которая получает адрес [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) указатель на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="47bcb-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="47bcb-107">Если метод завершается неудачно, значение этой выходной переменной не определено.</span><span class="sxs-lookup"><span data-stu-id="47bcb-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="47bcb-108">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47bcb-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="47bcb-109">Значение HRESULT: Этот метод поддерживает стандартные возвращаемые значения E_INVALIDARG, E_UNEXPECTED и E_OUTOFMEMORY.</span><span class="sxs-lookup"><span data-stu-id="47bcb-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47bcb-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="47bcb-110">Remarks</span></span>  
 <span data-ttu-id="47bcb-111">Этот метод позволяет записать позицию в последовательность перечисления для возврата к точке, в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="47bcb-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="47bcb-112">Вызывающий объект должен освободить этот новый перечислитель отдельно от первого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="47bcb-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
