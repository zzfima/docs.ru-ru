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
ms.openlocfilehash: 46cd8b5c22f48ba45c4da7fa8876d6807a21f2b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124144"
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
 заполняет Указатель на [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащий полный путь к библиотеке типов с именем в параметре `bstrSimpleName`.  
  
## <a name="remarks"></a>Заметки  
 Метод `ResolveTypeLib` вызывается [функцией LoadTypeLibWithResolver](loadtypelibwithresolver-function.md) во время обработки программы [Tlbexp. exe (программа экспорта библиотек типов)](../../tools/tlbexp-exe-type-library-exporter.md) .  
  
 Пользовательские реализации этого интерфейса должны возвращать [строку BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащую полный путь к библиотеке типов с именем в параметре `bstrSimpleName`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Тлбреф. idl, Тлбреф. h  
  
 **Библиотека:** Тлбреф. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Вспомогательные функции Tlbexp](index.md)
- [лоадтипелибекс](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
