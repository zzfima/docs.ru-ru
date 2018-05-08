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
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Создает другой перечислитель устройств необработанного ввода с же состоянием, что и текущий перечислитель, для прохода по тому же списку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppenum`  
  
 [out] Выходная переменная, которая получает адрес [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) указатель на интерфейс. Если метод завершается неудачно, значение этой выходной переменной не определено.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 Значение HRESULT: Этот метод поддерживает стандартные возвращаемые значения E_INVALIDARG, E_UNEXPECTED и E_OUTOFMEMORY.  
  
## <a name="remarks"></a>Примечания  
 Этот метод позволяет записать позицию в последовательность перечисления для возврата к точке, в дальнейшем. Вызывающий объект должен освободить этот новый перечислитель отдельно от первого перечислителя.
