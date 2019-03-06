---
title: Метод IXCLRDataProcess::GetAppDomainByUniqueId
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d4226bd73c7ae0c1faf510ed63b644116b064fb2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375081"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a>Метод IXCLRDataProcess::GetAppDomainByUniqueId

Получает `AppDomain` в процесс, основанный на свой уникальный идентификатор.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a>Параметры

`id`\
[in] Уникальный идентификатор домена приложения

`appDomain`\
[out] Домен приложения

## <a name="remarks"></a>Примечания

Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 20 слот в таблице виртуального метода. `IXCLRDataAppDomain*` Возвращается используется для взаимодействия с другими интерфейсами API.

## <a name="requirements"></a>Требования
**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также
- [Отладка](index.md)
- [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)
