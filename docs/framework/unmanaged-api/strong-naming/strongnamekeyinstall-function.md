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
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125201"
---
# <a name="strongnamekeyinstall-function"></a>Функция StrongNameKeyInstall

Импортирует пару открытого и закрытого ключей в контейнер.

Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) .

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
окне Имя контейнера ключей. `wszKeyContainer` должен быть непустой строкой.

`pbKeyBlob`\
окне Пара двоичных ключей.

`cbKeyBlob`\
окне Размер `pbKeyBlob`в байтах.

## <a name="return-value"></a>Возвращаемое значение

`true` при успешном завершении; в противном случае `false`.

## <a name="remarks"></a>Заметки

Чтобы удалить контейнер ключей, используйте функцию [StrongNameKeyDelete](strongnamekeydelete-function.md) .

Если функция `StrongNameKeyInstall` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** StrongName. h

**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Метод StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Метод StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
