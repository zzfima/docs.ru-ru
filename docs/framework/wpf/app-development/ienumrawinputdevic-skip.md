---
title: IEnumRAWINPUTDEVIC:SKIP
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: a74f71345a22f6d766c2d5966ca5d2cb33ab756e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053380"
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:SKIP
Указывает перечислителю пропустить следующие `celt` элементы в перечислении, чтобы следующий вызов [иенумравинпутдевик: Next](ienumrawinputdevic-next.md) не возвращал эти элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
  
 окне Число пропущенных элементов.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT: S_OK, если число представленных элементов равно `celt`; S_FALSE в противном случае.
