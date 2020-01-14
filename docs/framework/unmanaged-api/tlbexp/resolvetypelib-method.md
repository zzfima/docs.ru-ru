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
ms.openlocfilehash: f0f6fe321f4d38129b6d70ce94a7ea8de8fff6c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935671"
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
 окне Флаг [Сискинд](/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий операционную среду. Распространенные значения: SYS_WIN32 и SYS_WIN64.  
  
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
  
## <a name="see-also"></a>См. также:

- [Вспомогательные функции Tlbexp](index.md)
- [лоадтипелибекс](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
