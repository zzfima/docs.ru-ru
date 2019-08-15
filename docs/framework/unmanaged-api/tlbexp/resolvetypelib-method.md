---
title: Метод ResolveTypeLib
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f274befe78e45be3e53335572fd9c1e0b401fd3
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040178"
---
# <a name="resolvetypelib-method"></a>Метод ResolveTypeLib
Разрешает простое имя библиотеки типов, возвращая полный путь.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a>Параметры  
 `bstrSimpleName`  
 окне Значение типа [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащее простое имя библиотеки типов.  
  
 `tlbid`  
 окне Идентификатор GUID, назначенный библиотеке типов в реестре.  
  
 `lcid`  
 окне ИДЕНТИФИКАТОР локализации библиотеки типов.  
  
 `wMajorVersion`  
 окне Основной номер версии библиотеки типов. Например, для версии *x. y*основной номер версии — *x*.  
  
 `wMinorVersion`  
 окне Дополнительный номер версии библиотеки типов. Например, для версии *x. y*дополнительный номер версии — *y*.  
  
 `syskind`  
 окне Флаг [Сискинд](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий операционную среду. Распространенные значения — SYS_WIN32 и SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 заполняет Указатель на [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащий полный путь к библиотеке типов с именем в `bstrSimpleName` параметре.  
  
## <a name="remarks"></a>Примечания  
 Метод вызывается [функцией LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) во время обработки программы [Tlbexp. exe (программа экспорта библиотек типов).](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) `ResolveTypeLib`  
  
 Пользовательские реализации этого интерфейса должны возвращать [строку BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащую полный путь к библиотеке типов с именем в `bstrSimpleName` параметре.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Тлбреф. idl, Тлбреф. h  
  
 **Библиотечная** Тлбреф. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [лоадтипелибекс](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
