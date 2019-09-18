---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053409"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="1e51f-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="1e51f-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="1e51f-103">Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.</span><span class="sxs-lookup"><span data-stu-id="1e51f-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e51f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e51f-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e51f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e51f-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="1e51f-106">заполняет Адрес выходной переменной, получающей указатель интерфейса [иенумравинпутдевице](ienumrawinputdevice.md) .</span><span class="sxs-lookup"><span data-stu-id="1e51f-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="1e51f-107">Если метод завершился неудачно, значение этой выходной переменной не определено.</span><span class="sxs-lookup"><span data-stu-id="1e51f-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1e51f-108">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1e51f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="1e51f-109">HRESULT: Этот метод поддерживает стандартные возвращаемые значения E_INVALIDARG, E_OUTOFMEMORY и E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="1e51f-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e51f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e51f-110">Remarks</span></span>  
 <span data-ttu-id="1e51f-111">Этот метод делает возможным запись точки в последовательности перечисления, чтобы вернуться к этому моменту позже.</span><span class="sxs-lookup"><span data-stu-id="1e51f-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="1e51f-112">Вызывающий объект должен освободить этот новый перечислитель отдельно от первого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="1e51f-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
