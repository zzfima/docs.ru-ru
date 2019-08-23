---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 5249d7ea359db5d5c58ae87600f61048b465b4c1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964769"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="d3e2d-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="d3e2d-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="d3e2d-103">Этот интерфейс перечисляет устройства необработанного ввода и используется только программой PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="d3e2d-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3e2d-104">Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере</span><span class="sxs-lookup"><span data-stu-id="d3e2d-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="d3e2d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d3e2d-105">Members</span></span>  
  
|<span data-ttu-id="d3e2d-106">Член</span><span class="sxs-lookup"><span data-stu-id="d3e2d-106">Member</span></span>|<span data-ttu-id="d3e2d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d3e2d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3e2d-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="d3e2d-108">IEnumRAWINPUTDEVIC:Next</span></span>](ienumrawinputdevic-next.md)|<span data-ttu-id="d3e2d-109">Перечисляет следующие элементы `celt` (т. е. структуры RAWINPUTDEVICE) в списке перечислителя, затем возвращая их в `rgelt` наряду с фактическим количеством перечисляемых элементов в `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="d3e2d-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="d3e2d-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="d3e2d-110">IEnumRAWINPUTDEVIC:Skip</span></span>](ienumrawinputdevic-skip.md)|<span data-ttu-id="d3e2d-111">Указывает перечислителю пропустить следующие `celt` элементы в перечислении, чтобы следующий вызов [иенумравинпутдевик: Next](ienumrawinputdevic-next.md) не возвращал эти элементы.</span><span class="sxs-lookup"><span data-stu-id="d3e2d-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="d3e2d-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="d3e2d-112">IEnumRAWINPUTDEVIC:Reset</span></span>](ienumrawinputdevic-reset.md)|<span data-ttu-id="d3e2d-113">Сбрасывает последовательность перечисления в начало.</span><span class="sxs-lookup"><span data-stu-id="d3e2d-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="d3e2d-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="d3e2d-114">IEnumRAWINPUTDEVIC:Clone</span></span>](ienumrawinputdevic-clone.md)|<span data-ttu-id="d3e2d-115">Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.</span><span class="sxs-lookup"><span data-stu-id="d3e2d-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3e2d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d3e2d-116">See also</span></span>

- [<span data-ttu-id="d3e2d-117">О необработанном вводе</span><span class="sxs-lookup"><span data-stu-id="d3e2d-117">About Raw Input</span></span>](/windows/desktop/inputdev/about-raw-input)
