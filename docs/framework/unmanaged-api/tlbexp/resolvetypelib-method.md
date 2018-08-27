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
ms.openlocfilehash: be2558e760be8519e528baeff438273c8871f320
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924473"
---
# <a name="resolvetypelib-method"></a>Метод ResolveTypeLib
Разрешает простое имя библиотеки типов путем возвращения ее полного пути.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a>Параметры  
 `bstrSimpleName`  
 [in] Объект [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащий простое имя библиотеки типов.  
  
 `tlbid`  
 [in] Идентификатор GUID, назначенный в библиотеку типов в реестре.  
  
 `lcid`  
 [in] Идентификатор локализации библиотеки типов.  
  
 `wMajorVersion`  
 [in] Основной номер версии библиотеки типов. Например, для версии *x.y*, основной номер версии — *x*.  
  
 `wMinorVersion`  
 [in] Дополнительный номер версии библиотеки типов. Например, для версии *x.y*, дополнительный номер версии — *y*.  
  
 `syskind`  
 [in] Объект [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) флаг, определяющий операционной среде. Обычные значения: SYS_WIN32 и SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Указатель на [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащее полный путь к библиотеке типов, с именем в `bstrSimpleName` параметра.  
  
## <a name="remarks"></a>Примечания  
 `ResolveTypeLib` Вызывается метод [функция LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) во время [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) обработки.  
  
 Пользовательские реализации этого интерфейса должны возвращать [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащее полный путь к библиотеке типов, с именем в `bstrSimpleName` параметра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** TlbRef.idl, TlbRef.h  
  
 **Библиотека:** TlbRef.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
