---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: da089e5342e641ffebe22ca6a4a593f97faeb89c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="af564-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="af564-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="af564-103">Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.</span><span class="sxs-lookup"><span data-stu-id="af564-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af564-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af564-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af564-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="af564-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="af564-106">[out] Выходная переменная, которая получает адрес [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) указатель на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="af564-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="af564-107">Если метод завершается неудачно, значение этой выходной переменной не определено.</span><span class="sxs-lookup"><span data-stu-id="af564-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="af564-108">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="af564-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="af564-109">Значение HRESULT: Этот метод поддерживает стандартные возвращаемые значения E_INVALIDARG, E_UNEXPECTED и E_OUTOFMEMORY.</span><span class="sxs-lookup"><span data-stu-id="af564-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af564-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="af564-110">Remarks</span></span>  
 <span data-ttu-id="af564-111">Этот метод позволяет записать позицию в последовательность перечисления для возврата к точке, в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="af564-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="af564-112">Вызывающий объект должен освободить этот новый перечислитель отдельно от первого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="af564-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
