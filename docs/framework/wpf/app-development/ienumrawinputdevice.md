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
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
Этот интерфейс перечисляет устройства необработанного ввода и используется только программой PresentationHost.exe.  
  
> [!NOTE]
> Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md)|Перечисляет следующие элементы `celt` (т. е. структуры RAWINPUTDEVICE) в списке перечислителя, затем возвращая их в `rgelt` наряду с фактическим количеством перечисляемых элементов в `pceltFetched`.|  
|[IEnumRAWINPUTDEVIC:Skip](ienumrawinputdevic-skip.md)|Указывает перечислителю пропустить следующие `celt` элементы в перечислении, чтобы следующий вызов [иенумравинпутдевик: Next](ienumrawinputdevic-next.md) не возвращал эти элементы.|  
|[IEnumRAWINPUTDEVIC:Reset](ienumrawinputdevic-reset.md)|Сбрасывает последовательность перечисления в начало.|  
|[IEnumRAWINPUTDEVIC:Clone](ienumrawinputdevic-clone.md)|Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.|  
  
## <a name="see-also"></a>См. также

- [О необработанном вводе](/windows/desktop/inputdev/about-raw-input)
