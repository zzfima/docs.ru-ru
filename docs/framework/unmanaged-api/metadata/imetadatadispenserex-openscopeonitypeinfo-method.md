---
title: Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: deecd9ed4161bbd72e97a6320188961ae76d1e7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044269"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a>Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo
Этот метод не реализован. При вызове, он возвращает E_NOTIMPL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pITI`  
 [in] Указатель на [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) интерфейс, который предоставляет сведения о типе, в котором требуется открыть область.  
  
 `dwOpenFlags`  
 [in] Флаги для режима открытия.  
  
 `riid`  
 [in] Необходимый интерфейс.  
  
 `ppIUnk`  
 [out] Указатель на указатель на возвращенный интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
