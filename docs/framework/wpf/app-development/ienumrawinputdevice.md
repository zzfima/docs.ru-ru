---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 2030ad0ac00419280b45555ff11495c74e4274e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
Этот интерфейс перечисляет устройства необработанного ввода и используется только программой PresentationHost.exe.  
  
> [!NOTE]
>  Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|Перечисляет следующие элементы `celt` (т. е. структуры RAWINPUTDEVICE) в списке перечислителя, затем возвращая их в `rgelt` наряду с фактическим количеством перечисляемых элементов в `pceltFetched`.|  
|[IEnumRAWINPUTDEVIC:Skip](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|Указывает перечислителю пропустить следующий `celt` элементы в перечислении, чтобы при следующем вызове [IEnumRAWINPUTDEVIC: Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) не вернет эти элементы.|  
|[IEnumRAWINPUTDEVIC:Reset](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|Сбрасывает последовательность перечисления в начало.|  
|[IEnumRAWINPUTDEVIC:Clone](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.|  
  
## <a name="see-also"></a>См. также  
 [О необработанные данные ввода](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
