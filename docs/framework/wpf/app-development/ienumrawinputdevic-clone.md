---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: abc8a6e4780c8fe50afcf1b04f7e14aeb6452704
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949595"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="5741a-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="5741a-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="5741a-103">Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.</span><span class="sxs-lookup"><span data-stu-id="5741a-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5741a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5741a-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5741a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5741a-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="5741a-106">[out] Адрес выходной переменной, которая получает [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) указатель на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5741a-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="5741a-107">Если метод выполняется неудачно, значение этой переменной выходных данных не определено.</span><span class="sxs-lookup"><span data-stu-id="5741a-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5741a-108">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5741a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="5741a-109">HRESULT: Этот метод поддерживает стандартные возвращаемые значения E_INVALIDARG, E_UNEXPECTED и E_OUTOFMEMORY.</span><span class="sxs-lookup"><span data-stu-id="5741a-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5741a-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5741a-110">Remarks</span></span>  
 <span data-ttu-id="5741a-111">Этот метод дает возможность записать позицию в последовательности перечисления для возврата в эту точку в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="5741a-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="5741a-112">Вызывающий объект должен освободить этот новый перечислитель отдельно от первого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="5741a-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
