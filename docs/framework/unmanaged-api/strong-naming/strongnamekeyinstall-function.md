---
title: Функция StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3fc69b2edf611383402b13555cf33be10dbad3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366586"
---
# <a name="strongnamekeyinstall-function"></a>Функция StrongNameKeyInstall

Импортирует пару открытого и закрытого ключей в контейнер.

Эта функция является устаревшей. Используйте [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) метод вместо этого.

## <a name="syntax"></a>Синтаксис

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a>Параметры

`wszKeyContainer`\
[in] Имя контейнера ключа. `wszKeyContainer` должен быть непустой строкой.

`pbKeyBlob`\
[in] Двоичный пару ключей.

`cbKeyBlob`\
[in] Размер в байтах из `pbKeyBlob`.

## <a name="return-value"></a>Возвращаемое значение

`true` После успешного выполнения; в противном случае `false`.

## <a name="remarks"></a>Примечания

Используйте [StrongNameKeyDelete](strongnamekeydelete-function.md) функции, чтобы удалить контейнер ключей.

Если `StrongNameKeyInstall` функция не завершена, вызвать [StrongNameErrorInfo](strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** StrongName.h

**Библиотека:** Включена как ресурс в MsCorEE.dll

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Метод StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Метод StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)