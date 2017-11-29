---
title: "Метод ResolveTypeLib"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ResolveTypeLib
api_location: tlbref.dll
f1_keywords: ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b430b050117243ced9d764045075071278841da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 [in] Объект [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , содержащий простое имя библиотеки типов.  
  
 `tlbid`  
 [in] Идентификатор GUID, назначенный в библиотеку типов в реестре.  
  
 `lcid`  
 [in] Локализация идентификатор библиотеки типов.  
  
 `wMajorVersion`  
 [in] Основной номер версии библиотеки типов. Например, для версии *x.y*, основной номер версии — *x*.  
  
 `wMinorVersion`  
 [in] Дополнительный номер версии библиотеки типов. Например, для версии *x.y*, дополнительный номер версии — *y*.  
  
 `syskind`  
 [in] Объект [SYSKIND](http://msdn.microsoft.com/en-us/662048b2-59a8-48ca-9e4f-2f9a5306faa1) флаг, определяющий операционная среда. Общие значения: SYS_WIN32 и SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Указатель на [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , содержащее полный путь к библиотеке типов в `bstrSimpleName` параметра.  
  
## <a name="remarks"></a>Примечания  
 `ResolveTypeLib` Метод вызывается методом [функция LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) во время [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) обработки.  
  
 Пользовательские реализации этого интерфейса должны возвращать [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , содержащее полный путь к библиотеке типов в `bstrSimpleName` параметра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** TlbRef.idl, TlbRef.h  
  
 **Библиотека:** TlbRef.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx](http://msdn.microsoft.com/en-us/56a7f9e1-810b-4a42-aa4d-691f4304f5ef)
