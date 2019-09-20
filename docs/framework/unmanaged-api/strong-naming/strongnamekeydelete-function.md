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
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799022"
---
# <a name="strongnamekeydelete-function"></a>Функция StrongNameKeyDelete

Удаляет указанный контейнер ключей.

Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) .

## <a name="syntax"></a>Синтаксис

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Параметры

`wszKeyContainer`\
окне Имя удаляемого контейнера ключей.

## <a name="return-value"></a>Возвращаемое значение

`true`При успешном завершении; в противном случае —. `false`

## <a name="remarks"></a>Примечания

Используйте функцию [StrongNameKeyInstall](strongnamekeyinstall-function.md) для импорта пары открытого и закрытого ключей в контейнер.

Если функция `StrongNameKeyDelete` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** StrongName. h

**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Метод StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Метод StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
