---
title: IEnumRAWINPUTDEVIC:SKIP
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: fadf7b5526598f446eb7e49640bf4d43ec7395bf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354522"
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:SKIP
Указывает перечислителю пропустить следующий `celt` элементов в перечислении, чтобы следующий вызов [IEnumRAWINPUTDEVIC: Next](ienumrawinputdevic-next.md) не возвращал эти элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a>Параметры  
 `celt`  
  
 [in] Число элементов, которые нужно пропустить.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT: Значение S_OK, если число предоставленных элементов является `celt`; В противном случае значение S_FALSE.
