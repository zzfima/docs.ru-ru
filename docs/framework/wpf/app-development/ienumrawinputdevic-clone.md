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
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppenum`  
  
 заполняет Адрес выходной переменной, получающей указатель интерфейса [иенумравинпутдевице](ienumrawinputdevice.md) . Если метод завершился неудачно, значение этой выходной переменной не определено.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT: Этот метод поддерживает стандартные возвращаемые значения E_INVALIDARG, E_OUTOFMEMORY и E_UNEXPECTED.  
  
## <a name="remarks"></a>Примечания  
 Этот метод делает возможным запись точки в последовательности перечисления, чтобы вернуться к этому моменту позже. Вызывающий объект должен освободить этот новый перечислитель отдельно от первого перечислителя.
