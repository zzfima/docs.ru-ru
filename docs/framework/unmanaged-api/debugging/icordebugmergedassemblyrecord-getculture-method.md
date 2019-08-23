---
title: 'Метод Икордебугмержедассемблирекорд:: DataCulture'
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0f3ecee5a003587771871a178356d6dbfd8a636
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936846"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a>Метод Икордебугмержедассемблирекорд:: DataCulture
Возвращает строку с названием языка и региональных параметров сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cchCulture`  
 [in] Число символов в буфере `szCulture`.  
  
 `pcchCulture`  
 [выходной] Число символов, фактически записанных в буфер `szCulture`.  
  
 `szCulture`  
 [выходной] Массив символов, содержащий название языка и региональных параметров.  
  
## <a name="remarks"></a>Примечания  
 Название языка и региональных параметров — это уникальная строка, определяющая язык и региональные параметры, например "en-US" (для английского языка (США)) или "neutral" (для нейтрального языка и региональных параметров).  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
