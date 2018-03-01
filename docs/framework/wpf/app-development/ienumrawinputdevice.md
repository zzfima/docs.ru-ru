---
title: IEnumRAWINPUTDEVICE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a93458e97ef317c425f3b51b1e3abc20ade2931b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="b9102-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="b9102-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="b9102-103">Этот интерфейс перечисляет устройства необработанного ввода и используется только программой PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b9102-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9102-104">Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере</span><span class="sxs-lookup"><span data-stu-id="b9102-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="b9102-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b9102-105">Members</span></span>  
  
|<span data-ttu-id="b9102-106">Член</span><span class="sxs-lookup"><span data-stu-id="b9102-106">Member</span></span>|<span data-ttu-id="b9102-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b9102-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9102-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="b9102-108">IEnumRAWINPUTDEVIC:Next</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|<span data-ttu-id="b9102-109">Перечисляет следующие элементы `celt` (т. е. структуры RAWINPUTDEVICE) в списке перечислителя, затем возвращая их в `rgelt` наряду с фактическим количеством перечисляемых элементов в `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="b9102-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="b9102-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="b9102-110">IEnumRAWINPUTDEVIC:Skip</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|<span data-ttu-id="b9102-111">Указывает перечислителю пропустить следующий `celt` элементы в перечислении, чтобы при следующем вызове [IEnumRAWINPUTDEVIC: Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) не вернет эти элементы.</span><span class="sxs-lookup"><span data-stu-id="b9102-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="b9102-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="b9102-112">IEnumRAWINPUTDEVIC:Reset</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|<span data-ttu-id="b9102-113">Сбрасывает последовательность перечисления в начало.</span><span class="sxs-lookup"><span data-stu-id="b9102-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="b9102-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="b9102-114">IEnumRAWINPUTDEVIC:Clone</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|<span data-ttu-id="b9102-115">Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.</span><span class="sxs-lookup"><span data-stu-id="b9102-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9102-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b9102-116">See Also</span></span>  
 [<span data-ttu-id="b9102-117">О необработанные данные ввода</span><span class="sxs-lookup"><span data-stu-id="b9102-117">About Raw Input</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
