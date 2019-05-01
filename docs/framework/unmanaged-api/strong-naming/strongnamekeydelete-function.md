---
title: Функция StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040772"
---
# <a name="strongnamekeydelete-function"></a>Функция StrongNameKeyDelete

Удаляет указанный контейнер ключей.

Эта функция является устаревшей. Используйте [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) метод вместо этого.

## <a name="syntax"></a>Синтаксис

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Параметры

`wszKeyContainer`\
[in] Имя контейнера ключа для удаления.

## <a name="return-value"></a>Возвращаемое значение

`true` После успешного выполнения; в противном случае `false`.

## <a name="remarks"></a>Примечания

Используйте [StrongNameKeyInstall](strongnamekeyinstall-function.md) для импорта пару открытого и закрытого ключей в контейнер.

Если `StrongNameKeyDelete` функция не завершена, вызвать [StrongNameErrorInfo](strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** StrongName.h

**Библиотека:** Включена как ресурс в MsCorEE.dll

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Метод StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Метод StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)